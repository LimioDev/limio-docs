# ADR-0001: Arquitetura Modular por Domínio — Backend (limio-api) e Frontend (limio-app)

> Cópia da ADR aceita em 15/09/2026, como foi registrada. Depois dela, o código passou a usar `EMPREGADOR` no lugar de `CONTRATANTE` e ganhou mais módulos (`notificacao`, `moderacao`, `financeiro` etc.); a comunicação entre módulos foi detalhada na [ADR-0003](0003-comunicacao-entre-modulos-eventos-e-portas.md). O estado atual está no [system design](../system-design.md).

## Status

Aceito — 2026-09-15 (revisão 2: `auth` movido pra dentro de `modulos/`, detalhamento de camadas internas do módulo — entity, enums, records, exceções — e fluxo de requisição ponta a ponta)

## Contexto

O projeto Limio é composto por dois repositórios independentes que evoluem juntos:

- **limio-api**: backend Spring Boot (JPA, Flyway, Security, WebSocket, Testcontainers).
- **limio-app**: frontend Expo/React Native (Expo Router, React Query, Zustand, NativeWind, React Hook Form).

Ambos crescem por adição de entidades de domínio (`servico`, `contratante`, `prestador`, `chat`, `perfil`, `conta`, `anuncio`, ...). Sem uma convenção explícita, três problemas apareciam:

1. **Código comum sem lugar definido.** Config, exceptions, base classes, utils (back) e lib/hooks/tipos genéricos (front) tendiam a se espalhar dentro dos próprios módulos de domínio, criando acoplamento cruzado entre entidades que não deveriam se conhecer.
2. **Falta de rastreabilidade da decisão de negócio.** Regras de negócio e o "porquê" de cada decisão técnica ficavam apenas na cabeça de quem escreveu, sem histórico navegável por entidade.
3. **Camada interna do módulo mal definida.** `actions/{controller,service,usecase,mapper,helper}` diz onde fica o *comportamento*, mas não diz onde ficam entidade JPA, enums de domínio, DTOs (records) e exceções específicas — sem essa definição, cada módulo novo inventa sua própria variação.

O backend já tinha um esqueleto do padrão em `auth` (`src/main/java/com/limio/api/auth/`), com `actions/{controller,service,usecase,mapper,helper}` + `docs/{history,features,funcionalidade}`, mas sem implementação de entidade/enum/record ainda — é puro `package-info.java`. Esta revisão usa esse esqueleto como baseline, completa as camadas que faltavam, e reposiciona `auth` como **módulo comum dentro de `modulos/`** — autenticação é só mais um bounded context, não um caso especial. Módulos que precisam saber "quem é o usuário logado" acessam isso via contrato em `comum/`, nunca importando classe interna de `auth`.

## Decisão

Adotar organização **modular por domínio** nos dois repositórios, com uma pasta explícita para código compartilhado (`comum/`) separada da pasta que agrupa todos os módulos de domínio, **incluindo `auth`** (`modulos/`). Backend usa uma variação enxuta de **Ports & Adapters (Hexagonal) por módulo**; frontend usa **MVVM via Container-Presenter com custom hooks**, com o front mapeando esse mesmo espírito em TypeScript (union types no lugar de enum, `type` derivado de schema Zod no lugar de record).

---

### Decisão 1 — Backend (limio-api)

#### 1.1 Princípio de camadas dentro de um módulo

Cada módulo é um bounded context isolado. Dentro dele, a dependência flui numa única direção — de fora pra dentro:

```
controller (adapter de entrada, HTTP)
     │  chama
     ▼
usecase (aplicação — orquestra regra de negócio, não conhece HTTP nem JPA diretamente)
     │  usa portas (interfaces)
     ▼
repository (porta de persistência) ──▶ entity (domínio/persistência)
service (porta de integração externa: e-mail, storage, gateway de pagamento, fila)
     │
mapper (anti-corruption layer: entity ⇄ record, chamado só pelo controller)
```

Regras fixas:
- `entity`, `enums` e `excecao` de um módulo **não importam Spring** (sem `@Service`, sem `@RestController`) — são POJOs/records puros, testáveis sem contexto Spring.
- `usecase` depende só de interfaces (`XRepository`, portas de `service`) do próprio módulo + de `comum/`. Nunca depende de `record` — trabalha com `entity`/tipos de domínio; conversão pra `record` é responsabilidade do `mapper`, chamado pelo `controller`.
- `mapper` nunca é chamado de dentro do `usecase`. Isso mantém o `usecase` livre do contrato HTTP (o mesmo `usecase` pode ser reaproveitado por um job assíncrono ou por WebSocket sem reescrever nada).

#### 1.2 Árvore de pacotes completa

```
src/main/java/com/limio/api/
├── comum/                                     <-- Compartilhado entre módulos
│   ├── config/
│   │   ├── SecurityConfig.java
│   │   ├── OpenApiConfig.java
│   │   ├── WebSocketConfig.java
│   │   └── CorsConfig.java
│   ├── excecao/
│   │   ├── GlobalExceptionHandler.java        @RestControllerAdvice — único ponto que traduz exception → HTTP
│   │   ├── NegocioException.java              classe base abstrata p/ exceções de regra de negócio
│   │   └── enums/
│   │       └── CodigoErro.java                enum estável (código + mensagem), é o contrato de erro com o front
│   ├── seguranca/
│   │   ├── JwtAuthFilter.java                 lê o token, popula o SecurityContext
│   │   └── UsuarioAutenticado.java            record (id, papel) — é ISSO que outros módulos importam,
│   │                                          nunca uma classe interna de modulos/auth
│   ├── base/
│   │   ├── BaseEntity.java                    @MappedSuperclass: id (UUID), criadoEm, atualizadoEm
│   │   └── BaseMapper.java                    interface genérica <E, REQ, RES>: toEntity(REQ), toResponse(E)
│   └── records/
│       ├── PageResponse.java                  record genérico: conteudo, pagina, totalPaginas, totalItens
│       └── ErroResponse.java                  record: codigo (CodigoErro), mensagem, timestamp, path
│
└── modulos/                                   <-- TODO domínio vive aqui, sem exceção — inclusive auth
    │
    ├── auth/                                  <-- módulo como qualquer outro (bounded context de autenticação)
    │   ├── Usuario.java                       @Entity — id, email, senhaHash, papel, status
    │   ├── UsuarioRepository.java             interface JpaRepository<Usuario, UUID> (porta de persistência)
    │   ├── enums/
    │   │   ├── PapelUsuario.java              enum: CONTRATANTE, PRESTADOR, ADMIN
    │   │   └── StatusConta.java               enum: ATIVA, PENDENTE_VERIFICACAO, BLOQUEADA
    │   ├── records/
    │   │   ├── LoginRequest.java              record(String email, String senha) — validação Bean Validation
    │   │   ├── LoginResponse.java             record(String token, Instant expiraEm, PapelUsuario papel)
    │   │   ├── CadastroRequest.java           record
    │   │   └── UsuarioResponse.java           record
    │   ├── excecao/
    │   │   ├── CredenciaisInvalidasException.java   extends NegocioException
    │   │   └── ContaBloqueadaException.java         extends NegocioException
    │   ├── actions/
    │   │   ├── controller/
    │   │   │   └── AuthController.java        @RestController — POST /auth/login, /auth/cadastro
    │   │   ├── usecase/
    │   │   │   ├── AutenticarUsuarioUseCase.java
    │   │   │   └── CadastrarUsuarioUseCase.java
    │   │   ├── service/
    │   │   │   ├── TokenService.java           geração/validação de JWT (porta de saída)
    │   │   │   └── EmailVerificacaoService.java integração externa (envio de e-mail)
    │   │   ├── mapper/
    │   │   │   └── UsuarioMapper.java          implements BaseMapper<Usuario, CadastroRequest, UsuarioResponse>
    │   │   └── helper/
    │   │       └── SenhaHasher.java             util específico do módulo (BCrypt) — não sobe pra comum/
    │   └── docs/
    │       ├── history/CHANGELOG.md
    │       ├── features/TICKET-xxxx-descricao.md
    │       └── funcionalidade/EXPLICACAO_CLASSES.md
    │
    ├── entidade1/
    │   ├── Entidade1.java                     @Entity extends BaseEntity
    │   ├── Entidade1Repository.java
    │   ├── enums/
    │   │   └── StatusEntidade1.java            enum: valores fechados de status/tipo do domínio
    │   ├── records/
    │   │   ├── Entidade1Request.java
    │   │   ├── Entidade1Response.java
    │   │   └── Entidade1Filtro.java            record usado em query params (busca/paginação)
    │   ├── excecao/
    │   │   └── Entidade1NaoEncontradaException.java
    │   ├── actions/
    │   │   ├── controller/
    │   │   ├── service/
    │   │   ├── usecase/
    │   │   ├── mapper/
    │   │   └── helper/
    │   ├── subentidade/                        <-- entidade filha, vive dentro do agregado do pai
    │   │   ├── Subentidade.java
    │   │   ├── enums/
    │   │   ├── records/
    │   │   └── actions/{controller,service,usecase,mapper,helper}/
    │   └── docs/{history,features,funcionalidade}/
    │
    └── entidade2/
        └── ... (mesmo padrão completo: entity, enums/, records/, excecao/, actions/, docs/)

src/test/java/com/limio/api/modulos/
├── auth/{spec,story}/
├── entidade1/{spec,story}/
└── entidade2/{spec,story}/
```

`spec/` = teste de unidade (usecase isolado com mocks de repository/service — sem Spring context). `story/` = teste de comportamento/BDD (sobe contexto Spring + Testcontainers, exercita o fluxo controller → banco real via um cenário dado-quando-então).

#### 1.3 Por que `record` para DTOs, e não classe com Lombok

- Imutabilidade por padrão: um `LoginRequest` não deveria poder ser mutado depois de desserializado.
- `equals`/`hashCode`/`toString` de graça — sem `@EqualsAndHashCode` do Lombok.
- Compact constructor valida invariante no ponto de criação:
  ```java
  public record CadastroRequest(String email, String senha, PapelUsuario papel) {
      public CadastroRequest {
          if (senha == null || senha.length() < 8)
              throw new IllegalArgumentException("senha deve ter ao menos 8 caracteres");
      }
  }
  ```
- Lombok (`@Getter`/`@Setter`/`@Builder`) fica reservado pra `Entity` JPA, que **precisa** ser mutável (Hibernate exige construtor vazio + setters em muitos cenários de proxy/lazy loading) — `record` não serve como `@Entity`.

#### 1.4 Por que `enum` para valores fechados de domínio

- Nunca usar `String` solta pra status/papel/tipo (`"ATIVA"` digitado errado só quebra em runtime).
- Persistido com `@Enumerated(EnumType.STRING)` — legível direto na tabela, migração Flyway usa `CHECK` constraint com os mesmos valores.
- Dentro do `usecase`, `switch` sobre enum **sem `default`** força o compilador a acusar erro quando alguém adiciona um novo valor e esquece de tratar em algum lugar:
  ```java
  String proximaAcao = switch (usuario.getStatus()) {
      case ATIVA -> "liberar";
      case PENDENTE_VERIFICACAO -> "reenviar-email";
      case BLOQUEADA -> "notificar-suporte";
      // sem default: novo valor no enum = erro de compilação até tratar aqui
  };
  ```

#### 1.5 Fluxo de uma requisição ponta a ponta — `POST /auth/login`

1. `AuthController` recebe o corpo HTTP e desserializa direto em `LoginRequest` (record) — Bean Validation roda nas anotações do record.
2. `Controller` chama `AutenticarUsuarioUseCase.executar(request)`. O `usecase` não conhece `HttpServletRequest`.
3. `UseCase` busca `Usuario` via `UsuarioRepository` (porta), confere `StatusConta` (enum — se `BLOQUEADA`, lança `ContaBloqueadaException`), valida a senha via `SenhaHasher` (helper do módulo, BCrypt).
4. `UseCase` chama `TokenService` (adapter de saída) pra gerar o JWT.
5. `UseCase` devolve o resultado interno (`Usuario` entity + token) pro `Controller` — ainda sem virar contrato HTTP.
6. `Controller` usa `UsuarioMapper` pra converter `Usuario` + token em `LoginResponse` (record) e retorna 200.
7. Se qualquer exceção de negócio foi lançada no caminho, `GlobalExceptionHandler` (em `comum/excecao/`) intercepta, mapeia pro `CodigoErro` enum correspondente e devolve `ErroResponse` record com status HTTP apropriado — o `Controller` do módulo nunca escreve `try/catch` pra isso.

#### 1.6 Regra de dependência entre módulos

- `modulos/*` pode depender de `comum/`. Nunca de outro `modulo` diretamente — nem `auth`.
- Precisa saber quem é o usuário logado dentro de `entidade1`? O `Controller` recebe `UsuarioAutenticado` (record em `comum/seguranca/`, populado pelo `JwtAuthFilter`) via `@AuthenticationPrincipal` — nunca importa `com.limio.api.modulos.auth.Usuario`.
- Precisa emitir um evento pra outro módulo reagir (ex.: `entidade1` conclui algo e `chat` precisa notificar)? Passa por evento de domínio (Spring `ApplicationEventPublisher`) ou fila — nunca por import cruzado de `usecase` de outro módulo.

**Critério pra algo ir em `comum/` vs. ficar no módulo:** só sobe pra `comum/` quando usado por 2+ módulos **hoje** (não "pode vir a ser usado"). Regra de negócio de uma entidade específica fica na própria entidade, mesmo que pareça genérica.

#### 1.7 Glossário de pastas — Backend

| Pasta | Conceito | Contém | Nunca contém |
|---|---|---|---|
| `comum/config/` | Configuração de infraestrutura do Spring, transversal a todo o app. | `@Configuration`/`@Bean` — Security, CORS, OpenAPI, WebSocket. | Regra de negócio de qualquer módulo. |
| `comum/excecao/` | Contrato único de erro do sistema. | `GlobalExceptionHandler` (`@RestControllerAdvice`), `NegocioException` base, `enums/CodigoErro`. | Exceção específica de um módulo (essa fica em `modulos/<x>/excecao/`, só estende `NegocioException`). |
| `comum/seguranca/` | Infraestrutura de autenticação/autorização usada por todo módulo, sem expor o módulo `auth` em si. | `JwtAuthFilter`, `UsuarioAutenticado` (record — o único jeito de outro módulo saber "quem está logado"). | Regra de cadastro/login (isso é `modulos/auth`). |
| `comum/base/` | Abstrações técnicas reaproveitadas por toda `entity`/`mapper`. | `BaseEntity` (`@MappedSuperclass`: id, criadoEm, atualizadoEm), `BaseMapper<E,REQ,RES>`. | Campo ou método específico de uma entidade de negócio. |
| `comum/records/` | DTOs genéricos, sem dono de domínio. | `PageResponse<T>`, `ErroResponse`. | DTO com campo específico de uma entidade (esse vai em `modulos/<x>/records/`). |
| `modulos/<x>/` (raiz do módulo) | A própria entidade de domínio, mapeada pro banco. | `<X>.java` — classe `@Entity` (mutável, Lombok permitido aqui). | Lógica de apresentação HTTP ou validação de request (isso é `records`/`controller`). |
| `modulos/<x>/enums/` | Conjunto fechado de valores válidos do domínio (status, papel, tipo). | `enum` puro, sem dependência de Spring. | Comportamento (método com lógica de negócio) além de helpers triviais tipo `isTerminal()`. |
| `modulos/<x>/records/` | Contrato de entrada/saída HTTP do módulo — o que trafega na rede. | `record` imutável: `<X>Request`, `<X>Response`, `<X>Filtro`, com Bean Validation e compact constructor. | Campo que não existe no payload HTTP; lógica de persistência. |
| `modulos/<x>/excecao/` | Erros de regra de negócio específicos do módulo. | Classes `extends NegocioException`, uma por cenário de falha (`<X>NaoEncontradaException`). | Exceção técnica genérica (essa é de `comum/excecao/`). |
| `modulos/<x>/actions/controller/` | Adapter de entrada — traduz HTTP em chamada de `usecase`. | `@RestController`, mapeamento de rota, `@Valid` no `record` de entrada, chamada ao `mapper` pra devolver `record` de saída. | `if` de regra de negócio; acesso direto a `repository`. |
| `modulos/<x>/actions/usecase/` | Aplicação — orquestra a regra de negócio pura do módulo. | Classe que recebe `entity`/tipos de domínio, chama `repository`/`service`, decide fluxo. | Anotação HTTP (`@RequestBody` etc.), chamada a `mapper`. |
| `modulos/<x>/actions/service/` | Adapter de saída — integração com o mundo externo ao módulo (não é o banco). | Cliente de e-mail, storage, gateway de pagamento, geração de token, publish em fila. | Regra de negócio de decisão (isso é `usecase`). |
| `modulos/<x>/actions/mapper/` | Anti-corruption layer — converte `entity` ⇄ `record`. | `implements BaseMapper<E,REQ,RES>`, chamado só pelo `controller`. | Chamada a `repository` ou `service`; lógica de negócio. |
| `modulos/<x>/actions/helper/` | Utilitário específico do módulo, sem uso fora dele. | Função pura de apoio (ex.: `SenhaHasher`). | Qualquer coisa usada por 2+ módulos — aí sobe pra `comum/`. |
| `modulos/<x>/subentidade/` | Entidade filha do agregado — mesmo padrão completo (`entity`, `enums`, `records`, `actions`) só que aninhado. | Réplica da estrutura do módulo pai, em escala menor. | Existência independente do agregado pai (se precisa existir sozinha, é módulo, não subentidade). |
| `modulos/<x>/docs/history/` | Linha do tempo de decisões e mudanças de regra que não ficam óbvias só lendo código. | `CHANGELOG.md` + um `.md` datado por mudança relevante. | Documentação de "como chamar a API" (isso é `funcionalidade/`). |
| `modulos/<x>/docs/features/` | Registro por ticket: regra de negócio pedida + decisão técnica tomada pra atender. | Um `.md` por `TICKET-xxxx`. | Changelog cronológico solto (isso é `history/`). |
| `modulos/<x>/docs/funcionalidade/` | Manual de leitura do módulo — do request até o método interno. | `EXPLICACAO_CLASSES.md` mapeando request → classes envolvidas. | Decisão de negócio/porquê (isso é `history/` ou `features/`). |
| `src/test/.../<x>/spec/` | Teste de unidade — `usecase`/`mapper`/`helper` isolado, com mocks, sem subir Spring context. | Testes rápidos, um por classe de `actions/`. | Teste que precisa de banco real ou HTTP de verdade. |
| `src/test/.../<x>/story/` | Teste de comportamento (BDD) — fluxo dado/quando/então de ponta a ponta. | Sobe Spring context + Testcontainers, exercita `controller` → banco real. | Teste de detalhe interno de uma classe isolada (isso é `spec/`). |

---

### Decisão 2 — Frontend (limio-app)

Padrão: **MVVM (Model-View-ViewModel)** via **Container-Presenter com custom hooks**, com equivalentes TypeScript aos conceitos Java do backend — union type/const object no lugar de `enum`, `type` inferido de schema Zod no lugar de `record`.

| Camada MVVM | Onde mora | Responsabilidade | Equivalente backend |
|---|---|---|---|
| **View** (Presenter) | `modulos/<entidade>/view/` | Componente "burro": só recebe props e renderiza. Sem `fetch`, sem `useState` de negócio, sem acesso a store. | `controller` (sem lógica, só tradução) |
| **ViewModel** | `modulos/<entidade>/viewmodel/` | Custom hook (`use<Entidade>ViewModel`) que concentra estado, chama `servico/`, e expõe `{ dados, carregando, erro, handlers }`. | `usecase` |
| **Model** | `modulos/<entidade>/servico/` + `modulos/<entidade>/tipos/` | Chamadas de API, hooks de React Query, tipos/schemas da entidade. | `repository` + `entity`/`records` |
| **Container** | rota em `app/` (Expo Router) | Arquivo fino: `const vm = useXViewModel(); return <XView {...vm} />`. Não tem JSX de UI além disso. | `controller` (fiação HTTP) |

#### 2.1 Árvore de pastas completa

```
limio-app/
├── app/                                       <-- Expo Router: SÓ rotas finas (containers)
│   ├── (auth)/
│   │   ├── login.tsx                          import { useLoginViewModel } from "@/modulos/auth/viewmodel/..."
│   │   └── cadastro.tsx
│   └── (app)/
│       ├── (contratante)/anuncio/[id].tsx
│       ├── (prestador)/...
│       ├── servico/[id].tsx
│       ├── chat/[id].tsx
│       ├── perfil/index.tsx
│       └── conta/index.tsx
│
└── src/
    ├── comum/                                 <-- Compartilhado entre módulos (renomeia o `src/*` solto atual)
    │   ├── componentes/ui/                    Botao, Campo, Card, Badge, Carregando, Vazio
    │   ├── lib/                               api.ts (axios instance), datas.ts, query.ts (QueryClient)
    │   ├── store/                             sessao.ts (zustand — token, usuário logado, papel)
    │   ├── hooks/                             hooks reaproveitáveis entre módulos (ex: useDebounce)
    │   └── tipos/
    │       ├── api.ts                         tipos genéricos: PaginaResponse<T>, ErroResponse
    │       └── erros.ts                       CodigoErro — espelha 1:1 o enum comum/excecao/enums/CodigoErro.java
    │
    └── modulos/                               <-- Um módulo por entidade/domínio, inclusive auth
        ├── auth/
        │   ├── tipos/
        │   │   ├── auth.enums.ts              PapelUsuario, StatusConta — espelham os enums do backend
        │   │   └── auth.types.ts              LoginRequest/Response — espelham os records do backend
        │   ├── servico/
        │   │   ├── auth.api.ts                chamadas axios cruas (POST /auth/login)
        │   │   └── auth.queries.ts            useLoginMutation (React Query)
        │   ├── viewmodel/
        │   │   └── useLoginViewModel.ts
        │   └── view/
        │       └── LoginView.tsx
        ├── servico/
        │   ├── tipos/servico.enums.ts         StatusServico
        │   ├── tipos/servico.types.ts
        │   ├── servico/servico.api.ts
        │   ├── servico/servico.queries.ts     useServicoQuery, useAtualizarServicoMutation
        │   ├── viewmodel/useServicoDetalheViewModel.ts
        │   └── view/
        │       ├── ServicoDetalheView.tsx
        │       └── componentes/               subcomponentes só usados dentro do módulo servico
        ├── chat/
        │   └── {tipos,servico,viewmodel,view}/
        ├── anuncio/
        │   └── {tipos,servico,viewmodel,view}/
        └── conta/
            └── {tipos,servico,viewmodel,view}/
```

#### 2.2 Equivalente de `enum` em TypeScript

Evitar `enum` nativo do TS (gera código extra no bundle, comportamento estranho com `--isolatedModules`). Usar union de string literal + `const object`, que é exhaustive-checkable pelo compilador igual o `switch` sem `default` do Java:

```ts
// modulos/servico/tipos/servico.enums.ts
export const StatusServico = {
  PENDENTE: "PENDENTE",
  EM_ANDAMENTO: "EM_ANDAMENTO",
  CONCLUIDO: "CONCLUIDO",
} as const;

export type StatusServico = (typeof StatusServico)[keyof typeof StatusServico];

function rotuloStatus(status: StatusServico): string {
  switch (status) {
    case StatusServico.PENDENTE: return "Pendente";
    case StatusServico.EM_ANDAMENTO: return "Em andamento";
    case StatusServico.CONCLUIDO: return "Concluído";
    // sem default: novo valor no union = erro de compilação (com `noImplicitReturns`/checagem exaustiva)
  }
}
```

#### 2.3 Equivalente de `record` em TypeScript — Zod no limite do módulo

`record` do Java valida invariante na criação (compact constructor) e é imutável. Em TS, o par disso é **schema Zod + `z.infer`**, aplicado exatamente no ponto em que a resposta da API entra no app (dentro de `servico/`, nunca dentro da `view`):

```ts
// modulos/servico/tipos/servico.types.ts
import { z } from "zod";
import { StatusServico } from "./servico.enums";

export const ServicoResponseSchema = z.object({
  id: z.string().uuid(),
  titulo: z.string(),
  status: z.nativeEnum(StatusServico),
  criadoEm: z.string().datetime(),
});

export type ServicoResponse = z.infer<typeof ServicoResponseSchema>;
```

```ts
// modulos/servico/servico/servico.api.ts
export async function buscarServico(id: string): Promise<ServicoResponse> {
  const { data } = await api.get(`/servicos/${id}`);
  return ServicoResponseSchema.parse(data); // fronteira: payload inválido explode aqui, não na View
}
```

> `zod` ainda não é dependência do projeto (`package.json` hoje não tem). Adoção deste padrão exige adicionar `zod` — tratado como custo desta ADR, não como dado já disponível.

#### 2.4 Fluxo de uma tela ponta a ponta — detalhe de serviço

1. `app/(app)/servico/[id].tsx` (Container) lê `id` da rota e chama `const vm = useServicoDetalheViewModel(id)`.
2. `useServicoDetalheViewModel` (ViewModel, em `modulos/servico/viewmodel/`) chama `useServicoQuery(id)` de `servico.queries.ts` (React Query).
3. `useServicoQuery` chama `buscarServico(id)` (`servico.api.ts`) — resposta passa pelo `ServicoResponseSchema.parse`, garantindo que o `ViewModel` só recebe dado no formato esperado.
4. `ViewModel` deriva estado de apresentação (`carregando`, `erro`, `podeEditar` calculado a partir de `StatusServico` + `sessao` do Zustand) e retorna um objeto plano.
5. Container passa esse objeto pra `ServicoDetalheView` (Presenter) — a View só teste unitário de renderização, sem mock de rede.

#### 2.5 Regra de dependência entre módulos

- `modulos/*` só importa de `comum/`. Nunca de outro `modulo` — inclusive `auth`: quem precisa saber "usuário logado" lê de `comum/store/sessao.ts` (populado pelo módulo `auth` no login), nunca importa arquivo de dentro de `modulos/auth/`.
- `app/*` só importa `viewmodel` + `view` de `modulos/*` (e componentes de `comum/`) — zero lógica de negócio dentro de `app/`.

**Por que Container-Presenter + hooks e não Context/Redux, nem classes ViewModel:** o projeto já resolve estado global com Zustand (`sessao.ts`) e estado de servidor com React Query — um "ViewModel" como hook é idiomático em RN, testável isolado via `renderHook` (sem montar árvore de componentes) e não exige biblioteca nova.

#### 2.6 Glossário de pastas — Frontend

| Pasta | Conceito | Contém | Nunca contém |
|---|---|---|---|
| `app/` | Expo Router — define rota por estrutura de arquivo, e faz o papel de Container. | Arquivo fino por rota: `const vm = useXViewModel(); return <XView {...vm} />`. | `useState` de negócio, chamada de API direta, JSX de UI além da composição da View. |
| `comum/componentes/ui/` | Design system — componentes visuais puros, sem noção de nenhuma entidade. | `Botao`, `Campo`, `Card`, `Badge`, `Carregando`, `Vazio`. | Import de `tipos`/`servico` de um módulo específico (`servico`, `chat`, etc.). |
| `comum/lib/` | Infraestrutura técnica compartilhada, sem regra de negócio. | `api.ts` (instância axios), `datas.ts`, `query.ts` (QueryClient). | Chamada de endpoint específico de uma entidade (isso é `modulos/<x>/servico/`). |
| `comum/store/` | Estado global do app, usado por mais de um módulo. | `sessao.ts` (Zustand — token, usuário logado, papel). | Estado local de uma tela (isso é `viewmodel`). |
| `comum/hooks/` | Hook técnico reaproveitável, sem regra de negócio de entidade. | Ex.: `useDebounce`, `useKeyboardVisible`. | `useXViewModel` de um módulo (esse mora dentro do próprio módulo). |
| `comum/tipos/` | Contrato genérico de dado, sem dono de domínio. | `PaginaResponse<T>`, `ErroResponse`, `erros.ts` (`CodigoErro`, espelho do enum do backend). | Tipo com campo específico de uma entidade. |
| `modulos/<x>/tipos/` | Contrato de dado da entidade — equivalente TS de `enum`/`record` do backend. | `<x>.enums.ts` (union + const object), `<x>.types.ts` (schema Zod + `z.infer`). | Lógica (função) — pasta é só tipo/schema. |
| `modulos/<x>/servico/` | Camada Model — acesso a dado, equivalente ao `repository`/`mapper` do backend. | `<x>.api.ts` (chamada axios crua + `schema.parse` na fronteira), `<x>.queries.ts` (hooks React Query). | JSX; estado de UI; lógica de decisão de tela (isso é `viewmodel`). |
| `modulos/<x>/viewmodel/` | Aplicação — orquestra estado e regra de apresentação da tela, equivalente ao `usecase` do backend. | `use<X>ViewModel.ts`: chama `servico/`, deriva estado (`carregando`, `erro`, flags calculadas), expõe objeto plano. | JSX; chamada de API crua sem passar por `servico/`. |
| `modulos/<x>/view/` | Apresentação — Presenter puro, equivalente ao `controller` do backend (só traduz dado em UI). | Componente que só recebe props e renderiza; subcomponentes internos do módulo em `view/componentes/`. | `useState` de negócio, chamada a `servico/` ou ao `store` global diretamente. |

---

## Consequências

**Positivas**
- Módulo de domínio = unidade de trabalho: dá pra abrir uma feature inteira (back + front) sabendo exatamente onde cada peça mora — inclusive `auth`, que deixa de ser caso especial.
- `comum/` explícito impede que uma entidade vire dependência oculta de outra; contrato de erro (`CodigoErro`) espelhado 1:1 entre back e front reduz "erro genérico" no app.
- `enum`/`record` no back e union-type/Zod no front fecham o conjunto de valores válidos em tempo de compilação (ou na fronteira de rede), pegando bug de valor inválido antes de virar incidente em produção.
- Backend ganha rastreabilidade de decisão de negócio por módulo (`docs/history`, `docs/features`).
- `usecase` e `viewmodel` isolados são testáveis sem infraestrutura pesada (`usecase` sem Spring context em `spec/`; `viewmodel` via `renderHook` sem montar UI).

**Negativas / custos**
- Migração do backend: mover `auth` de contexto solto pra dentro de `modulos/`, criar `entity`/`enums`/`records`/`excecao` que hoje não existem (só há `package-info.java`), e mover módulos de domínio existentes fora de `auth` pra dentro de `modulos/`. Fazer incrementalmente, um módulo por vez — `auth` como primeiro, por já ter o esqueleto.
- Migração do frontend: `src/componentes`, `src/lib`, `src/store`, `src/tipos` viram `src/comum/*` (rename simples); telas atuais em `app/` precisam ser quebradas em `view+viewmodel+servico+tipos` por módulo — maior esforço que o back porque não há módulo de referência implementado ainda.
- Adoção de Zod no front é dependência nova, não decisão de graça — precisa entrar no `package.json` e ganhar convenção de uso (schema só em `servico/`, nunca em `view`).
- Overhead de boilerplate pra entidades muito simples (CRUD trivial) — aceito conscientemente em troca de consistência; não abrir exceção "só essa entidade não segue o padrão".

## Alternativas consideradas

- **Backend em camadas técnicas (controller/service/repository globais)**: rejeitado — dificultava saber o que pertencia a qual entidade e escalava mal com o crescimento de domínios.
- **`auth` como contexto especial fora de `modulos/`**: era a decisão original desta ADR, revertida aqui — tratar `auth` como um módulo comum (mais um bounded context) elimina a exceção "esse aqui não segue a regra geral" e simplifica onboarding (a regra é sempre "todo domínio vive em `modulos/`"). Acesso a dado de usuário autenticado passa por contrato em `comum/`, não por import direto do módulo.
- **DTO como classe com Lombok (`@Data`) em vez de `record`**: rejeitado — perde imutabilidade e validação no ponto de criação; `record` cobre o caso de uso de DTO com menos código e menos risco de setter esquecido.
- **`String` solta em vez de `enum`/union type pra status/papel/tipo**: rejeitado — sem checagem em tempo de compilação, erro de digitação em valor de domínio só aparece em runtime (ou pior, em produção).
- **Frontend com Redux/Context centralizado pro app inteiro**: rejeitado — projeto já usa Zustand + React Query, que cobrem estado global e de servidor; um ViewModel por módulo evita um store gigante compartilhado por telas não relacionadas.
- **Frontend sem separação view/viewmodel (lógica direto no componente de rota)**: é o estado atual implícito; rejeitado porque mistura fetch, estado e JSX no mesmo arquivo, dificultando teste e reuso entre telas parecidas (ex.: fluxo contratante vs. prestador).
