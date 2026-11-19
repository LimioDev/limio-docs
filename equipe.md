# Equipe — LIMIO

> Cards, status e responsáveis do Jira (projeto ETI) em **19/11/2026**. Horas por pessoa medidas pelo **Clockify** de cada integrante até **19/11/2026**, com cerimônias e dailies: o time soma 838,62 h. Cerimônias e decisões completas na página [Gestão de Equipe](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/2981889) do Confluence.

## Integrantes e papéis

| Integrante | Papel oficial | GitHub |
| --- | --- | --- |
| Kauê | Product Owner e Frontend | [@KaueAmaral](https://github.com/KaueAmaral) |
| Augusto | Backend e Tech Lead | [@Agkso](https://github.com/Agkso) |
| Andrey | Backend | [@andreyindras](https://github.com/andreyindras) |
| Gabriel | Backend | [@gabrielssena](https://github.com/gabrielssena) |
| Victor | Frontend | [@VictorHugoRod](https://github.com/VictorHugoRod) |

A composição oficial do time não muda até o fim do período letivo. As funções podem rotacionar para destravar tarefas:

- **Sprint 5:** Augusto passou a acumular o papel de Tech Lead; Gabriel assumiu o back-end do painel do Empregador, no módulo `anuncio` (ETI-52).
- **Sprint 7:** Augusto assumiu o deploy de produção e a publicação na Play Store (ETI-123 e ETI-124), a remoção do SMS (ETI-134 e ETI-135) e o back-end da assinatura GOLD (ETI-81, ETI-83 e ETI-85); Kauê desenhou a área do admin no Figma (ETI-137) e ficou com o front-end das notificações, da moderação e do admin.
- **Documentação (agosto e setembro):** quem é de código também trabalhou nos documentos. Exemplos: Andrey no diagrama de atividade (ETI-18), Gabriel no diagrama de classes (ETI-9) e nos Termos de Uso (ETI-21), Victor nos casos de uso (ETI-8, ETI-17).

## Como ligar uma issue ao código

| Onde | Como identificar |
| --- | --- |
| Jira | Cada tarefa é um card `ETI-<número>`, com responsável e critérios de aceitação. Cards de código vêm em pares `[BACK-END]` e `[FRONT-END]`, com a tag do módulo no título (ex.: `[anuncio]`). |
| Branch | `feature/<número do card>` (ex.: `feature/60` para o ETI-60). |
| Pull request | Aberto da branch para a `develop`, com aprovação obrigatória de um dono do código (`.github/CODEOWNERS`). |
| Documentação no código | Cada módulo da API tem `docs/features/TICKET-<número>-<descrição>.md`, com a regra pedida e a decisão técnica tomada. |

## Horas por pessoa

Soma do Clockify de cada integrante até 19/11: horas nos cards, lançamentos sem card e horas de cerimônias e dailies. Detalhe card a card em [`estimativa/horas-por-pessoa.csv`](estimativa/horas-por-pessoa.csv).

| Integrante | Cards com horas | Em cards | Sem card | Cerimônias e dailies | Total | % do total |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Augusto | 28 | 144,87 h | 12,91 h | 34,33 h | 192,11 h | 22,9% |
| Victor | 28 | 137,04 h | 0 h | 34,34 h | 171,37 h | 20,4% |
| Kauê | 39 | 133,52 h | 0 h | 34,34 h | 167,86 h | 20,0% |
| Andrey | 20 | 122,86 h | 0 h | 34,34 h | 157,2 h | 18,7% |
| Gabriel | 22 | 115,75 h | 0 h | 34,34 h | 150,08 h | 17,9% |
| **Total** | | **654,03 h** | **12,91 h** | **171,68 h** | **838,62 h** | 100% |

> O Andrey usou dois workspaces no Clockify; as horas dele juntam os dois, contando uma vez só as entradas repetidas. O relatório do Augusto traz só o total de cada dia: as horas dele por card foram estimadas dividindo o dia entre os lançamentos, e as horas de outro projeto (UniDB1) foram excluídas. A cerimônia de 09/11 e as dailies a partir de 08/11 estão incluídas como lançadas. Detalhes em [`estimativa/estimativa-horas.md`](estimativa/estimativa-horas.md).

## O que cada um entregou

Cards em que a pessoa é a responsável no Jira, por situação. A lista completa de cards, com status e horas, está em [`estimativa/estimativa-horas.md`](estimativa/estimativa-horas.md).

### Kauê — Product Owner e Frontend

21 cards como responsável: 17 concluídos, 4 em andamento e 0 a fazer.

**Concluídos**

- [ETI-3](https://kaueamaral96.atlassian.net/browse/ETI-3) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-19](https://kaueamaral96.atlassian.net/browse/ETI-19) [GESTÃO] Estruturar base de Gestão, Cerimônias e Auditoria de Não-Conformidades
- [ETI-20](https://kaueamaral96.atlassian.net/browse/ETI-20) [DESIGN] Prototipação de alta fidelidade das interfaces do aplicativo LIMIO
- [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel
- [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha
- [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) [conta] [FRONT-END] Toggles de notificação em Ajustes
- [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) [conta] [FRONT-END] Tela "Encerrar conta"
- [ETI-53](https://kaueamaral96.atlassian.net/browse/ETI-53) [empregador] [FRONT-END] Tela "Início" do Empregador e barra de navegação
- [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?"
- [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar
- [ETI-70](https://kaueamaral96.atlassian.net/browse/ETI-70) [anuncio] [FRONT-END] Confirmar escolha e "Não foi possível escolher"
- [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio"
- [ETI-89](https://kaueamaral96.atlassian.net/browse/ETI-89) [anuncio] [FRONT-END] Botão "Iniciar serviço" e tela "Serviço em andamento"
- [ETI-108](https://kaueamaral96.atlassian.net/browse/ETI-108) [moderacao] [FRONT-END] Tela "Avaliação"
- [ETI-111](https://kaueamaral96.atlassian.net/browse/ETI-111) [notificacao] [FRONT-END] Tela "Notificações"
- [ETI-113](https://kaueamaral96.atlassian.net/browse/ETI-113) [notificacao] [FRONT-END] Registrar o aparelho para push e abrir a tela certa ao tocar no aviso
- [ETI-137](https://kaueamaral96.atlassian.net/browse/ETI-137) desenho de tela admin figma

**Em andamento**

- [ETI-104](https://kaueamaral96.atlassian.net/browse/ETI-104) [chat] [FRONT-END] Tela "Conversas" (Empregador e Prestador) — À TESTAR
- [ETI-106](https://kaueamaral96.atlassian.net/browse/ETI-106) [perfil] [FRONT-END] Telas "Perfil público" (candidato e consulta) — AJUSTANDO
- [ETI-115](https://kaueamaral96.atlassian.net/browse/ETI-115) [moderacao] [FRONT-END] Tela "Abrir denúncia" — EM PROGRESSO
- [ETI-118](https://kaueamaral96.atlassian.net/browse/ETI-118) [administracao] [FRONT-END] Área do admin: fila de denúncias, análise, sanção e dashboard — EM PROGRESSO

**Onde trabalhou mais horas (até 19/11):** ETI-20 (24,82 h); ETI-106 (9,78 h); ETI-89 (8,88 h); ETI-111 (7,84 h); ETI-39 (7,46 h)

### Augusto — Backend e Tech Lead

32 cards como responsável: 26 concluídos, 4 em andamento e 2 a fazer.

**Concluídos**

- [ETI-5](https://kaueamaral96.atlassian.net/browse/ETI-5) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) [DOCS] Criação de Diagrama Entidade-Relacionamento
- [ETI-23](https://kaueamaral96.atlassian.net/browse/ETI-23) [DEV] Criação de Repositório para o projeto LIMIO
- [ETI-25](https://kaueamaral96.atlassian.net/browse/ETI-25) Criacao do DIAGRAMA DE ENTIDADE E RELACIONAMENTO 
- [ETI-28](https://kaueamaral96.atlassian.net/browse/ETI-28) [DEV] Setup Inicial dos Repositórios limio-api e limio-app
- [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail
- [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada
- [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) [DOCS] Criacão de ADR's
- [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria
- [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod)
- [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) [auth] [FRONT-END] Fluxo de cadastro em 3 passos
- [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ
- [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails
- [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada
- [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha"
- [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) [anuncio] [BACK-END] Cancelar anúncio antes da escolha
- [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) [anuncio] [BACK-END] Candidatar-se a um anúncio
- [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente
- [ETI-81](https://kaueamaral96.atlassian.net/browse/ETI-81) [financeiro] [BACK-END] Assinar o GOLD pelo gateway de pagamento
- [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados
- [ETI-92](https://kaueamaral96.atlassian.net/browse/ETI-92) [anuncio] [BACK-END] Validar o serviço (presencial ou pela foto)
- [ETI-105](https://kaueamaral96.atlassian.net/browse/ETI-105) [perfil] [BACK-END] Consultar o perfil público e a reputação
- [ETI-119](https://kaueamaral96.atlassian.net/browse/ETI-119) Remover .env do front end
- [ETI-120](https://kaueamaral96.atlassian.net/browse/ETI-120) atualizar secure e cors do projeto para teste local
- [ETI-134](https://kaueamaral96.atlassian.net/browse/ETI-134) [auth] [BACK-END] Trocar a confirmação por SMS pela confirmação só por e-mail
- [ETI-135](https://kaueamaral96.atlassian.net/browse/ETI-135) [auth] [FRONT-END] Busca por CEP e remoção do SMS do app

**Em andamento**

- [ETI-83](https://kaueamaral96.atlassian.net/browse/ETI-83) [financeiro] [BACK-END] Gerenciar a assinatura GOLD: consultar, trocar cartão e cancelar renovação — À TESTAR
- [ETI-85](https://kaueamaral96.atlassian.net/browse/ETI-85) [financeiro] [BACK-END] Renovação mensal do GOLD: cobrança, falha, novas tentativas e volta ao FREE — EM PROGRESSO
- [ETI-123](https://kaueamaral96.atlassian.net/browse/ETI-123) [INFRA] Publicação do app na Play Store — EM PROGRESSO
- [ETI-124](https://kaueamaral96.atlassian.net/browse/ETI-124) [INFRA] Deploy de produção: develop para main, migrations, variáveis e smoke test — EM PROGRESSO

**A fazer**

- [ETI-126](https://kaueamaral96.atlassian.net/browse/ETI-126) [DOCS] Emenda ao ADR-0001: convenção de pastas por módulo (v2)
- [ETI-127](https://kaueamaral96.atlassian.net/browse/ETI-127) [DEBT] Aplicar convenção de pastas — entidade, repository/, modelos/

**Onde trabalhou mais horas (até 19/11):** ETI-124 (16,86 h); ETI-123 (10,07 h); ETI-37 (8,71 h); ETI-47 (7,84 h); ETI-10 (7,75 h)

### Andrey — Backend

18 cards como responsável: 12 concluídos, 4 em andamento e 2 a fazer.

**Concluídos**

- [ETI-4](https://kaueamaral96.atlassian.net/browse/ETI-4) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) [DOCS] Criação de Diagrama de Atividade
- [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) [conta] [BACK-END] Consultar e atualizar preferências de notificação
- [ETI-48](https://kaueamaral96.atlassian.net/browse/ETI-48) [empregador] [BACK-END] Consultar e editar o perfil de Empregador
- [ETI-50](https://kaueamaral96.atlassian.net/browse/ETI-50) [empregador] [BACK-END] Cadastrar, editar, remover e marcar endereço padrão
- [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) [anuncio] [BACK-END] Editar anúncio antes da escolha
- [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato
- [ETI-69](https://kaueamaral96.atlassian.net/browse/ETI-69) [anuncio] [BACK-END] Escolher o prestador: transação atômica, cota e liberação do contato
- [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador
- [ETI-90](https://kaueamaral96.atlassian.net/browse/ETI-90) [anuncio] [BACK-END] Fazer o check-out com foto
- [ETI-94](https://kaueamaral96.atlassian.net/browse/ETI-94) [anuncio] [BACK-END] Empregador cancelar o serviço combinado (24h ou mais)
- [ETI-109](https://kaueamaral96.atlassian.net/browse/ETI-109) [auth] [BACK-END] Rotina diária de limpeza de dados vencidos (LGPD)

**Em andamento**

- [ETI-66](https://kaueamaral96.atlassian.net/browse/ETI-66) [anuncio] [BACK-END] Rotina de expiração de anúncios sem candidatos — AJUSTANDO
- [ETI-96](https://kaueamaral96.atlassian.net/browse/ETI-96) [anuncio] [BACK-END] Prestador cancelar depois de escolhido — À TESTAR
- [ETI-99](https://kaueamaral96.atlassian.net/browse/ETI-99) [anuncio] [BACK-END] Reagendar: propor, cancelar proposta, responder e expirar — EM PROGRESSO
- [ETI-103](https://kaueamaral96.atlassian.net/browse/ETI-103) [chat] [BACK-END] Listar minhas conversas por papel — À TESTAR

**A fazer**

- [ETI-71](https://kaueamaral96.atlassian.net/browse/ETI-71) [anuncio] [BACK-END] Consultar histórico de anúncios e serviços com filtros
- [ETI-98](https://kaueamaral96.atlassian.net/browse/ETI-98) [anuncio] [BACK-END] Rotina de conclusão automática por silêncio

**Onde trabalhou mais horas (até 19/11):** ETI-18 (12,72 h); ETI-50 (12,26 h); ETI-48 (10,71 h); ETI-94 (9,71 h); ETI-34 (8,95 h)

### Gabriel — Backend

20 cards como responsável: 14 concluídos, 6 em andamento e 0 a fazer.

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
- [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) [anuncio] [BACK-END] Iniciar o serviço
- [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida
- [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) [moderacao] [BACK-END] Avaliar a outra parte ou pular
- [ETI-136](https://kaueamaral96.atlassian.net/browse/ETI-136) [anuncio/chat] [BACK-END] Devolver o id do usuário nas telas que abrem o perfil público
- [ETI-138](https://kaueamaral96.atlassian.net/browse/ETI-138) [BACK-END] devolver o id da candidatura no servico combinado

**Em andamento**

- [ETI-65](https://kaueamaral96.atlassian.net/browse/ETI-65) [anuncio] [BACK-END] Avisar os prestadores compatíveis quando um anúncio é publicado — PARA AJUSTE
- [ETI-110](https://kaueamaral96.atlassian.net/browse/ETI-110) [notificacao] [BACK-END] Listar minhas notificações e marcar como lidas — PARA AJUSTE
- [ETI-112](https://kaueamaral96.atlassian.net/browse/ETI-112) [notificacao] [BACK-END] Serviço único de envio de notificações, respeitando as preferências — PARA AJUSTE
- [ETI-114](https://kaueamaral96.atlassian.net/browse/ETI-114) [moderacao] [BACK-END] Registrar denúncia — EM PROGRESSO
- [ETI-116](https://kaueamaral96.atlassian.net/browse/ETI-116) [moderacao] [BACK-END] Admin analisar denúncia e aplicar sanção — EM PROGRESSO
- [ETI-117](https://kaueamaral96.atlassian.net/browse/ETI-117) [administracao] [BACK-END] Dashboard administrativo com os números da operação — EM PROGRESSO

**Onde trabalhou mais horas (até 19/11):** ETI-65 (11,33 h); ETI-101 (9,92 h); ETI-59 (9,66 h); ETI-9 (8,93 h); ETI-110 (7,98 h)

### Victor — Frontend

21 cards como responsável: 14 concluídos, 3 em andamento e 4 a fazer.

**Concluídos**

- [ETI-2](https://kaueamaral96.atlassian.net/browse/ETI-2) [REUNIÃO] Alinhamento de Regras de Negócio
- [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17) [DOCS] Criação do Diagrama de Casos de Uso
- [ETI-49](https://kaueamaral96.atlassian.net/browse/ETI-49) [empregador] [FRONT-END] Telas "Meu perfil" e "Dados de contato"
- [ETI-51](https://kaueamaral96.atlassian.net/browse/ETI-51) [empregador] [FRONT-END] Telas "Endereços salvos" e "Novo endereço"
- [ETI-55](https://kaueamaral96.atlassian.net/browse/ETI-55) [prestador] [FRONT-END] Telas "Perfil de atuação" e "Especialidades"
- [ETI-57](https://kaueamaral96.atlassian.net/browse/ETI-57) [perfil] [FRONT-END] Trocar a foto em "Meu perfil"
- [ETI-60](https://kaueamaral96.atlassian.net/browse/ETI-60) [anuncio] [FRONT-END] Telas "Novo anúncio", "Categoria" e "Anúncio publicado"
- [ETI-62](https://kaueamaral96.atlassian.net/browse/ETI-62) [anuncio] [FRONT-END] Tela "Editar anúncio"
- [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?"
- [ETI-78](https://kaueamaral96.atlassian.net/browse/ETI-78) [anuncio] [FRONT-END] Tela "Aplicações" (pendentes, combinadas e histórico), com desistir
- [ETI-80](https://kaueamaral96.atlassian.net/browse/ETI-80) [perfil] [FRONT-END] Faixa de cota no mural e tela "Cota do mês"
- [ETI-87](https://kaueamaral96.atlassian.net/browse/ETI-87) [anuncio] [FRONT-END] Telas "Serviço combinado" (Empregador) e "Seu serviço" (Prestador)
- [ETI-91](https://kaueamaral96.atlassian.net/browse/ETI-91) [anuncio] [FRONT-END] Tela "Checkout"
- [ETI-102](https://kaueamaral96.atlassian.net/browse/ETI-102) [chat] [FRONT-END] Telas "Chat" e "Chat somente leitura"

**Em andamento**

- [ETI-82](https://kaueamaral96.atlassian.net/browse/ETI-82) [financeiro] [FRONT-END] Tela "Assinatura" (assinar GOLD) — EM PROGRESSO
- [ETI-93](https://kaueamaral96.atlassian.net/browse/ETI-93) [anuncio] [FRONT-END] Tela "Validar serviço" — AJUSTANDO
- [ETI-95](https://kaueamaral96.atlassian.net/browse/ETI-95) [anuncio] [FRONT-END] Confirmação "Cancelar o serviço combinado" — EM PROGRESSO

**A fazer**

- [ETI-72](https://kaueamaral96.atlassian.net/browse/ETI-72) [anuncio] [FRONT-END] Tela "Histórico" do Empregador
- [ETI-84](https://kaueamaral96.atlassian.net/browse/ETI-84) [financeiro] [FRONT-END] Tela "Assinatura GOLD" (gerenciar)
- [ETI-97](https://kaueamaral96.atlassian.net/browse/ETI-97) [anuncio] [FRONT-END] Confirmação "Cancelar este serviço?" (Prestador)
- [ETI-100](https://kaueamaral96.atlassian.net/browse/ETI-100) [anuncio] [FRONT-END] Telas "Propor reagendamento" e "Proposta recebida"

**Onde trabalhou mais horas (até 19/11):** ETI-20 (42,62 h); ETI-17 (11,18 h); ETI-8 (9,69 h); ETI-82 (5,74 h); ETI-40 (5,43 h)

### Cards sem responsável

10 cards não têm responsável no Jira: ETI-7, ETI-8, ETI-24, ETI-26, ETI-27, ETI-29, ETI-58, ETI-121, ETI-122, ETI-125. São reuniões, documentação e a AEP, feitas em conjunto, e as atividades finais da Sprint 7 que envolvem a equipe toda (homologação, correção de bugs e apresentação).

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
| Retrospective & Review — fim da Sprint 6 | 09/11/2026 | Sprint 6 fechada com 18 cards; os demais passaram para a Sprint 7, planejada na mesma noite |

Todos os cinco integrantes estiveram presentes em todas as cerimônias registradas.

**Horas no Clockify:** cada fim de sprint teve a Retrospective e Review (2,5 h) seguida da Planning da sprint seguinte (1,5 h). Somando a Planning da Sprint Inicial, são 24 h por integrante até a Planning da Sprint 7 (09/11). As dailies, de 10 minutos às 12:00 toda terça, quarta, quinta e domingo, somam 10,33 h por integrante até 19/11 (62 dailies). A Retrospective & Review da Sprint 7 será em 21/11. Datas e horários em [`estimativa/estimativa-horas.md`](estimativa/estimativa-horas.md#cerimônias-e-dailies).
