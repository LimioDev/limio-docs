# Equipe — LIMIO

> Horas medidas pelo **Clockify** de cada integrante (copiado em **01/11/2026**); cards, status e responsáveis do Jira (projeto ETI) na mesma data. Cerimônias e decisões completas na página [Gestão de Equipe](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/2981889) do Confluence.

## Integrantes e papéis

| Integrante | Papel oficial | GitHub |
| --- | --- | --- |
| Kauê | Product Owner e Frontend | [@KaueAmaral](https://github.com/KaueAmaral) |
| Augusto | Backend e Tech Lead | [@Agkso](https://github.com/Agkso) |
| Andrey | Backend | [@andreyindras](https://github.com/andreyindras) |
| Gabriel | Backend | [@gabrielssena](https://github.com/gabrielssena) |
| Victor | Frontend | [@VictorHugoRod](https://github.com/VictorHugoRod) |

A composição oficial do time não muda até o fim do período letivo. As funções podem rotacionar para destravar tarefas:

- **Sprints 4 e 5:** o front-end do fluxo de cadastro (ETI-40) está com o Augusto no Jira; quem registrou horas no card foi o Victor.
- **Sprint 5:** Augusto passou a acumular o papel de Tech Lead; Gabriel assumiu o back-end do painel do Empregador, no módulo `anuncio` (ETI-52).
- **Documentação (agosto e setembro):** quem é de código também trabalhou nos documentos. Exemplos: Andrey no diagrama de atividade (ETI-18), Gabriel no diagrama de classes (ETI-9) e nos Termos de Uso (ETI-21), Victor nos casos de uso (ETI-8, ETI-17).

## Como ligar uma issue ao código

| Onde | Como identificar |
| --- | --- |
| Jira | Cada tarefa é um card `ETI-<número>`, com responsável e critérios de aceitação. Cards de código vêm em pares `[BACK-END]` e `[FRONT-END]`, com a tag do módulo no título (ex.: `[anuncio]`). |
| Branch | `feature/<número do card>` (ex.: `feature/60` para o ETI-60). |
| Pull request | Aberto da branch para a `develop`, com aprovação obrigatória de um dono do código (`.github/CODEOWNERS`). |
| Documentação no código | Cada módulo da API tem `docs/features/TICKET-<número>-<descrição>.md`, com a regra pedida e a decisão técnica tomada. |

## Horas por pessoa

Soma do Clockify de cada integrante, o cronômetro que cada um usa ao trabalhar em um card. Detalhe card a card em [`estimativa/horas-por-pessoa.csv`](estimativa/horas-por-pessoa.csv).

| Integrante | Cards com horas | Horas | % do total |
| --- | ---: | ---: | ---: |
| Victor | 20 | 103,07 h | 25,4% |
| Augusto | 20 | 85,92 h | 21,2% |
| Gabriel | 13 | 72,76 h | 17,9% |
| Andrey | 12 | 72,56 h | 17,9% |
| Kauê | 24 | 71,43 h | 17,6% |
| **Total** | | **405,74 h** | 100% |

> O Andrey usou dois workspaces no Clockify; as horas dele juntam os dois, contando uma vez só as entradas repetidas. No Clockify do Augusto, quatro dias com dois cards tiveram o total do dia dividido igualmente entre eles. Detalhes em [`estimativa/estimativa-horas.md`](estimativa/estimativa-horas.md).

## O que cada um entregou

Cards em que a pessoa é a responsável no Jira, por situação. A lista completa de cards, com status e horas, está em [`estimativa/estimativa-horas.md`](estimativa/estimativa-horas.md).

### Kauê — Product Owner e Frontend

14 cards como responsável: 9 concluídos, 3 em andamento e 2 a fazer.

**Concluídos**

- [ETI-3](https://kaueamaral96.atlassian.net/browse/ETI-3) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-19](https://kaueamaral96.atlassian.net/browse/ETI-19) [GESTÃO] Estruturar base de Gestão, Cerimônias e Auditoria de Não-Conformidades
- [ETI-20](https://kaueamaral96.atlassian.net/browse/ETI-20) [DESIGN] Prototipação de alta fidelidade das interfaces do aplicativo LIMIO
- [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel
- [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha
- [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) [conta] [FRONT-END] Toggles de notificação em Ajustes
- [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) [conta] [FRONT-END] Tela "Encerrar conta"
- [ETI-53](https://kaueamaral96.atlassian.net/browse/ETI-53) [empregador] [FRONT-END] Tela "Início" do Empregador e barra de navegação
- [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio"

**Em andamento**

- [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?" — À TESTAR
- [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar — À TESTAR
- [ETI-108](https://kaueamaral96.atlassian.net/browse/ETI-108) [moderacao] [FRONT-END] Tela "Avaliação" — EM PROGRESSO

**Onde trabalhou mais horas:** ETI-20 (20,74 h); ETI-39 (7,46 h); ETI-42 (6,6 h); ETI-64 (5,09 h); ETI-68 (4,96 h)

### Augusto — Backend e Tech Lead

22 cards como responsável: 12 concluídos, 10 em andamento e 0 a fazer.

**Concluídos**

- [ETI-5](https://kaueamaral96.atlassian.net/browse/ETI-5) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) [DOCS] Criação de Diagrama Entidade-Relacionamento
- [ETI-23](https://kaueamaral96.atlassian.net/browse/ETI-23) [DEV] Criação de Repositório para o projeto LIMIO
- [ETI-25](https://kaueamaral96.atlassian.net/browse/ETI-25) Criacao do DIAGRAMA DE ENTIDADE E RELACIONAMENTO
- [ETI-28](https://kaueamaral96.atlassian.net/browse/ETI-28) [DEV] Setup Inicial dos Repositórios limio-api e limio-app
- [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) [DOCS] Criacão de ADR's
- [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod)
- [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) [auth] [FRONT-END] Fluxo de cadastro em 3 passos
- [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ
- [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails
- [ETI-119](https://kaueamaral96.atlassian.net/browse/ETI-119) Remover .env do front end
- [ETI-120](https://kaueamaral96.atlassian.net/browse/ETI-120) atualizar secure e cors do projeto para teste local

**Em andamento**

- [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail — AJUSTANDO
- [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada — AJUSTANDO
- [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria — AJUSTANDO
- [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada — AJUSTANDO
- [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha" — PARA AJUSTE
- [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) [anuncio] [BACK-END] Cancelar anúncio antes da escolha — À TESTAR
- [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) [anuncio] [BACK-END] Candidatar-se a um anúncio — PARA AJUSTE
- [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente — EM PROGRESSO
- [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados — EM PROGRESSO
- [ETI-92](https://kaueamaral96.atlassian.net/browse/ETI-92) [anuncio] [BACK-END] Validar o serviço (presencial ou pela foto) — EM PROGRESSO

**Onde trabalhou mais horas:** ETI-37 (8,71 h); ETI-47 (7,82 h); ETI-30 (6,87 h); ETI-46 (6,09 h); ETI-27 (5,96 h)

### Andrey — Backend

10 cards como responsável: 5 concluídos, 3 em andamento e 2 a fazer.

**Concluídos**

- [ETI-4](https://kaueamaral96.atlassian.net/browse/ETI-4) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) [DOCS] Criação de Diagrama de Atividade
- [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) [conta] [BACK-END] Consultar e atualizar preferências de notificação
- [ETI-48](https://kaueamaral96.atlassian.net/browse/ETI-48) [empregador] [BACK-END] Consultar e editar o perfil de Empregador
- [ETI-50](https://kaueamaral96.atlassian.net/browse/ETI-50) [empregador] [BACK-END] Cadastrar, editar, remover e marcar endereço padrão

**Em andamento**

- [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) [anuncio] [BACK-END] Editar anúncio antes da escolha — À TESTAR
- [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato — À TESTAR
- [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador — AJUSTANDO

**Onde trabalhou mais horas:** ETI-18 (12,72 h); ETI-50 (12,29 h); ETI-48 (10,71 h); ETI-34 (8,95 h); ETI-73 (8,22 h)

### Gabriel — Backend

12 cards como responsável: 10 concluídos, 2 em andamento e 0 a fazer.

**Concluídos**

- [ETI-6](https://kaueamaral96.atlassian.net/browse/ETI-6) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-9](https://kaueamaral96.atlassian.net/browse/ETI-9) [DOCS] Criação de Diagrama de Classes
- [ETI-21](https://kaueamaral96.atlassian.net/browse/ETI-21) [DOCS] Escrever Termos de Aceite e Politica de Privacidade da LIMIO
- [ETI-32](https://kaueamaral96.atlassian.net/browse/ETI-32) [auth] [BACK-END] Autenticar, renovar sessão, encerrar sessão e trocar papel ativo
- [ETI-52](https://kaueamaral96.atlassian.net/browse/ETI-52) [anuncio] [BACK-END] Listar os anúncios do Empregador para o painel
- [ETI-54](https://kaueamaral96.atlassian.net/browse/ETI-54) [prestador] [BACK-END] Salvar o perfil de atuação e calcular "perfil completo"
- [ETI-56](https://kaueamaral96.atlassian.net/browse/ETI-56) [perfil] [BACK-END] Enviar e trocar a foto de perfil
- [ETI-59](https://kaueamaral96.atlassian.net/browse/ETI-59) [anuncio] [BACK-END] Criar e publicar anúncio, com fotos
- [ETI-79](https://kaueamaral96.atlassian.net/browse/ETI-79) [perfil] [BACK-END] Consultar a cota do mês e zerar na virada do mês
- [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida

**Em andamento**

- [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) [anuncio] [BACK-END] Iniciar o serviço — À TESTAR
- [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) [moderacao] [BACK-END] Avaliar a outra parte ou pular — EM PROGRESSO

**Onde trabalhou mais horas:** ETI-101 (10,1 h); ETI-59 (9,67 h); ETI-9 (8,93 h); ETI-32 (7,66 h); ETI-52 (7,35 h)

### Victor — Frontend

15 cards como responsável: 8 concluídos, 0 em andamento e 7 a fazer.

**Concluídos**

- [ETI-2](https://kaueamaral96.atlassian.net/browse/ETI-2) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17) [DOCS] Criação do Diagrama de Casos de Uso
- [ETI-49](https://kaueamaral96.atlassian.net/browse/ETI-49) [empregador] [FRONT-END] Telas "Meu perfil" e "Dados de contato"
- [ETI-51](https://kaueamaral96.atlassian.net/browse/ETI-51) [empregador] [FRONT-END] Telas "Endereços salvos" e "Novo endereço"
- [ETI-55](https://kaueamaral96.atlassian.net/browse/ETI-55) [prestador] [FRONT-END] Telas "Perfil de atuação" e "Especialidades"
- [ETI-57](https://kaueamaral96.atlassian.net/browse/ETI-57) [perfil] [FRONT-END] Trocar a foto em "Meu perfil"
- [ETI-60](https://kaueamaral96.atlassian.net/browse/ETI-60) [anuncio] [FRONT-END] Telas "Novo anúncio", "Categoria" e "Anúncio publicado"
- [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?"

**Onde trabalhou mais horas:** ETI-20 (42,64 h); ETI-17 (11,18 h); ETI-8 (9,69 h); ETI-40 (5,43 h); ETI-55 (4,16 h)

### Cards sem responsável

42 cards ainda não têm responsável no Jira. Quase todos são da Sprint 7, que será distribuída no planejamento dela; os demais são tarefas antigas de documentação e reunião feitas em conjunto.

## Cerimônias

| Cerimônia | Data | O que saiu |
| --- | --- | --- |
| Reunião de alinhamento | 05/08/2026 | Retomada pós-férias e reestruturação da equipe |
| Retrospective & Review | 19/08/2026 | Documento de requisitos e regras de negócio validado |
| Retrospective & Review | 31/08/2026 | DER, Termos de Uso e Política de Privacidade, base de gestão no Confluence |
| Reunião de alinhamento | 01/09/2026 | Orientação do professor: documentação no GitHub; definição do agente de validação de código (AEP) |
| Retrospective & Review — fim da Sprint 3 | 15/09/2026 | Repositórios criados; diagramas de classes e de atividade levados para a Sprint 4 |
| Retrospective & Review — fim da Sprint 4 | 12/10/2026 | Arquitetura (ADR-0001) e infraestrutura na Railway; cards separados em BACK-END e FRONT-END |
| Retrospective & Review — fim da Sprint 5 | 26/10/2026 | 14 cards concluídos; título obrigatório no anúncio; Sprints 6 e 7 planejadas |

Todos os cinco integrantes estiveram presentes em todas as cerimônias registradas.
