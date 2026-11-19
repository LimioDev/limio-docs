# Estimativa de horas do produto — LIMIO

> **Situação em 19/11/2026.** Status, sprint e responsável de cada card vêm do Jira (projeto ETI) nessa data. As horas vêm do Clockify de cada integrante, card a card, de 05/08 a 19/11/2026, mais as cerimônias e dailies. Mesmos dados de [`estimativa-horas.csv`](estimativa-horas.csv), que abre no Excel ou no Google Sheets.
> Planilha de trabalho anexada à página [Controle de Horas do Backlog](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/26476545) no Confluence.

## Resumo

| Indicador | Valor |
| --- | ---: |
| Total estimado do produto (MVP) | **1.047 h** |
| **Horas lançadas no Clockify pelo time até 19/11** | **838,62 h** |
| · em cards do backlog | 654,03 h (62,5% do estimado) |
| · sem card | 12,91 h |
| · cerimônias: plannings, retrospectives e reviews | 120 h (24 h por integrante) |
| · dailies | 51,68 h (10,34 h por integrante) |
| Saldo (estimado − trabalhado, todos os cards) | 479,15 h |
| Saldo só dos cards ainda não concluídos | 238,02 h |
| Cards | 122 (90 concluídos) |
| Cards dentro da faixa de ±30% | 46 |
| Cards acima de 130% | 19 (ETI-8, ETI-10, ETI-19, ETI-35, ETI-37, ETI-42, ETI-50, ETI-52, ETI-64, ETI-66, ETI-70, ETI-76, ETI-88, ETI-89, ETI-94, ETI-103, ETI-106, ETI-110, ETI-111) |
| Cards concluídos abaixo de 70% | 26 |
| Cards em andamento, ainda abaixo de 70% | 9 |
| Cards sem horas | 19 |
| Cards sem estimativa | 3 (ETI-136, ETI-137 e ETI-138) |

## Como a estimativa foi feita

1. **Escopo:** todos os cards do Jira do projeto, da documentação inicial (agosto) até a Sprint 7 (fim do MVP), incluindo reuniões, design, documentação, back-end e front-end.
2. **Cards que já tinham horas na época da estimativa:** a estimativa foi escolhida para que as horas fiquem entre 70% e 130% dela.
3. **Cards ainda não iniciados:** estimados pelo escopo da descrição do card (quantidade de telas, cenários de teste, rotinas automáticas, integrações externas e pendências).
4. **Referência do próprio time:** mediana de 7,2 h por card de back-end e 4,3 h por card de front-end, medida nos cards já concluídos.
5. **Fechamento:** as estimativas base foram multiplicadas por um fator único (1,12) para fechar o total combinado pelo time de 1.000 h, e arredondadas para 0,5 h (exceções: ETI-10 e ETI-25). Depois entrou a subtarefa ETI-120 (1 h), o que levou o total a 1.001 h.
6. **Revisão de 01/11:** a estimativa do ETI-40 foi corrigida de 126,5 h para 6 h e entraram cinco cards da Sprint 7 que faltavam no backlog: homologação do MVP (ETI-121, 40 h), correção dos bugs da homologação (ETI-122, 40 h), publicação na Play Store (ETI-123, 15 h), deploy de produção (ETI-124, 20 h) e apresentação e documentação final (ETI-125, 25 h). O total passou a 1.020,5 h.
7. **Revisão de 08/11:** entraram os dois cards criados em 04/11 a partir da proposta de engenharia do Augusto: emenda ao ADR-0001 com a convenção de pastas por módulo (ETI-126, 3,5 h, mesmo porte do ETI-35, que criou as ADRs) e aplicação dessa convenção no código, movendo 34 arquivos em três PRs (ETI-127, 8 h, a mediana de um card de back-end). O total passou a 1.032 h. Os status e sprints de todos os cards foram atualizados pelo Jira; o ETI-123 (Play Store) e o ETI-124 (deploy de produção) passaram da Sprint 7 para a Sprint 6.
8. **Revisão de 19/11:** entraram os cards da remoção do SMS, criados em 11/11 a partir dos requisitos v1.4: troca da confirmação por SMS pela confirmação só por e-mail (ETI-134, 8 h) e busca por CEP com remoção do SMS no app (ETI-135, 7 h). O total passou a 1.047 h. Entraram também três subtarefas da Sprint 7, sem estimativa: ETI-136 e ETI-138 (ajustes de contrato entre back e front) e ETI-137 (desenho da área do admin no Figma). Status, sprints e responsáveis foram atualizados pelo Jira, e as horas card a card passaram a vir do Clockify de cada integrante até 19/11.
8. **Revisão de 19/11:** entraram os cards da remoção do SMS, criados em 11/11 a partir dos requisitos v1.4: troca da confirmação por SMS pela confirmação só por e-mail (ETI-134, 8 h) e busca por CEP com remoção do SMS no app (ETI-135, 7 h). O total passou a 1.047 h. Entraram também três subtarefas da Sprint 7, sem estimativa: ETI-136 e ETI-138 (ajustes de contrato entre back e front) e ETI-137 (desenho da área do admin no Figma). Status, sprints e responsáveis foram atualizados pelo Jira, e as horas card a card passaram a vir do Clockify de cada integrante até 19/11.

**Maiores incertezas:** renovação mensal do GOLD pelo Asaas (ETI-85), envio de notificações nos canais (ETI-112) e a homologação de ponta a ponta com a correção dos bugs (ETI-121 e ETI-122).

**Leitura dos desvios:** a maior parte dos cards fora da faixa são cards concluídos com menos horas que o estimado, ou seja, estimativas altas. Isso será usado ao estimar os próximos cards.

### De onde vêm as horas

As horas foram medidas pelo Clockify, o cronômetro que cada integrante usa ao trabalhar em um card. Até 27/10 esta estimativa usava os lançamentos manuais do Jira, que tinham lançamentos repetidos e horas no card errado; por isso a fonte passou a ser o Clockify. Os relatórios de cada integrante foram copiados em 19/11.

- **Andrey:** usou dois workspaces no Clockify ("kaueamaral96.atlassian.net" e "LIMIO"). As horas dele juntam os dois, contando uma vez só as entradas repetidas entre eles.
- **Augusto:** o relatório dele traz só o total de cada dia, sem a duração de cada lançamento. As horas por card foram estimadas descontando do total do dia a daily e as cerimônias e dividindo o restante igualmente entre os lançamentos do dia. Lançamentos sem card e sem descrição ficaram como "sem card" (12,91 h). As horas de outro projeto (UniDB1) foram excluídas; nos dias em que elas se misturam com o LIMIO (10, 11 e 13/11), o total do dia foi dividido igualmente entre os lançamentos. Por isso as horas do Augusto em cards antigos podem diferir da versão de 08/11.

### Cerimônias e dailies

Plannings, retrospectives, reviews e dailies não têm card no Jira. O time lança essas horas no Clockify de cada integrante, no mesmo horário para todos, com as descrições "Planning – Sprint X", "Retrospective e Review – Sprint X" e "Daily". Os cinco integrantes estiveram em todas.

| Data | Horário | Cerimônia | Horas por integrante |
| --- | --- | --- | ---: |
| 05/08/2026 | 19:00–20:30 | Planning – Sprint Inicial | 1,5 |
| 19/08/2026 | 19:00–21:30 | Retrospective e Review – Sprint Inicial | 2,5 |
| 19/08/2026 | 21:30–23:00 | Planning – Sprint 2 | 1,5 |
| 31/08/2026 | 19:00–21:30 | Retrospective e Review – Sprint 2 | 2,5 |
| 31/08/2026 | 21:30–23:00 | Planning – Sprint 3 | 1,5 |
| 15/09/2026 | 19:00–21:30 | Retrospective e Review – Sprint 3 | 2,5 |
| 15/09/2026 | 21:30–23:00 | Planning – Sprint 4 | 1,5 |
| 12/10/2026 | 19:00–21:30 | Retrospective e Review – Sprint 4 | 2,5 |
| 12/10/2026 | 21:30–23:00 | Planning – Sprint 5 | 1,5 |
| 26/10/2026 | 19:00–21:30 | Retrospective e Review – Sprint 5 | 2,5 |
| 09/11/2026 | 19:00–21:30 | Retrospective e Review – Sprint 6 | 2,5 |
| 09/11/2026 | 21:30–23:00 | Planning – Sprint 7 | 1,5 |
| | | **Total** | **24** |

**Dailies:** 10 minutos, às 12:00, toda terça, quarta, quinta e domingo. De 05/08 a 19/11 foram 62 dailies, ou 10,34 h por integrante.

**Total:** 34,34 h por integrante, 171,68 h do time. A cerimônia de 09/11 e as dailies a partir de 08/11 estão incluídas como lançadas; o time vai registrá-las no Clockify.

Essas horas não fazem parte da estimativa de 1.047 h, que cobre só os cards do backlog. Por isso elas aparecem no total trabalhado, mas não mudam o saldo nem a faixa ±30% de nenhum card.

### Regra da faixa ±30%

| Faixa | Quando |
| --- | --- |
| OK | Trabalhado entre 70% e 130% da estimativa |
| Em andamento | Card ainda não concluído, abaixo de 70% |
| Fora da faixa | Trabalhado acima de 130%, ou card concluído abaixo de 70% |
| Sem lançamento | Card sem horas no Clockify |
| Sem estimativa | Subtarefa criada na Sprint 7 sem estimativa de horas |

## Horas por pessoa

Soma do Clockify de cada integrante até 19/11. Detalhe card a card em [`horas-por-pessoa.csv`](horas-por-pessoa.csv).

| Pessoa | Cards com horas | Em cards (h) | Sem card (h) | Cerimônias e dailies (h) | Total (h) | % do total |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Augusto Ogawa | 28 | 144,87 | 12,91 | 34,33 | 192,11 | 22,9% |
| Victor Hugo Rodrigues de Oliveira | 28 | 137,04 | 0 | 34,34 | 171,37 | 20,4% |
| Kauê (kaueamaral96) | 39 | 133,52 | 0 | 34,34 | 167,86 | 20,0% |
| Andrey (andreyindras) | 20 | 122,86 | 0 | 34,34 | 157,2 | 18,7% |
| Gabriel Sena | 22 | 115,75 | 0 | 34,34 | 150,08 | 17,9% |
| **Total** | | **654,03** | **12,91** | **171,68** | **838,62** | 100% |

As horas do Augusto são estimadas a partir do total de cada dia (veja [De onde vêm as horas](#de-onde-vêm-as-horas)).

## Por sprint

| Sprint | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| Sprint Inicial | 6 | 39,5 | 24,76 | 17,07 | 3,8% |
| Sprint 2 | 5 | 28 | 35,98 | 7,21 | 2,7% |
| Sprint 3 | 6 | 69,5 | 42,22 | 29,19 | 6,6% |
| Sprint 4 | 6 | 104,5 | 108,15 | 8,21 | 10,0% |
| Sprint 5 | 14 | 76 | 71,79 | 6,57 | 7,3% |
| Sprint 6 | 18 | 179 | 107,45 | 89,8 | 17,1% |
| Sprint 7 | 67 | 550,5 | 263,73 | 321,1 | 52,6% |

## Por status

Status do Jira em 19/11.

| Status | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| CONCLUIDO | 90 | 705,5 | 536,61 | 241,13 | 67,4% |
| À TESTAR | 4 | 26,5 | 17,23 | 11,37 | 2,5% |
| PARA AJUSTE | 3 | 36 | 25,68 | 14,13 | 3,4% |
| AJUSTANDO | 3 | 14,5 | 22,31 | 0,03 | 1,4% |
| EM PROGRESSO | 11 | 116 | 51,92 | 64,32 | 11,1% |
| À FAZER | 11 | 148,5 | 0,33 | 148,17 | 14,2% |

## Por camada

| Camada | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| AEP | 1 | 39 | 12,43 | 26,57 | 3,7% |
| BACK-END | 46 | 423 | 259,44 | 194,21 | 40,4% |
| DEBT | 1 | 8 | 0 | 8 | 0,8% |
| DESIGN | 1 | 70,5 | 67,45 | 3,05 | 6,7% |
| DEV | 2 | 9 | 6,7 | 2,45 | 0,9% |
| DOCS | 12 | 106,4 | 91,71 | 34,44 | 10,2% |
| FRONT-END | 38 | 218 | 150,09 | 91,37 | 20,8% |
| GESTÃO | 1 | 1 | 3,08 | 0 | 0,1% |
| INFRA | 4 | 37,5 | 37,78 | 8,45 | 3,6% |
| QA | 2 | 80 | 0 | 80 | 7,6% |
| REUNIÃO | 6 | 36,5 | 20,01 | 17,07 | 3,5% |
| SUBTAREFA | 8 | 18,1 | 5,39 | 13,54 | 1,7% |

## Todos os cards

| Ticket | Camada | Sprint | Status | Título | Estimativa (h) | Trabalhado (h) | Faixa ±30% | Saldo (h) |
| --- | --- | --- | --- | --- | ---: | ---: | --- | ---: |
| [ETI-2](https://kaueamaral96.atlassian.net/browse/ETI-2) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-3](https://kaueamaral96.atlassian.net/browse/ETI-3) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-4](https://kaueamaral96.atlassian.net/browse/ETI-4) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 14 | 4,93 | Fora da faixa | 9,07 |
| [ETI-5](https://kaueamaral96.atlassian.net/browse/ETI-5) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-6](https://kaueamaral96.atlassian.net/browse/ETI-6) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-7](https://kaueamaral96.atlassian.net/browse/ETI-7) | DOCS | Sprint Inicial | CONCLUIDO | [DOCS] Revisar e construir Requisitos e Regras de Negócio | 11,5 | 13,83 | OK | 0 |
| [ETI-8](https://kaueamaral96.atlassian.net/browse/ETI-8) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Revisar e Construir Casos de Uso | 12 | 17,45 | Fora da faixa | 0 |
| [ETI-9](https://kaueamaral96.atlassian.net/browse/ETI-9) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Classes | 14,5 | 10,78 | OK | 3,72 |
| [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Criação de Diagrama Entidade-Relacionamento | 0,4 | 8,06 | Fora da faixa | 0 |
| [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Criação do Diagrama de Casos de Uso | 10 | 11,18 | OK | 0 |
| [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Atividade | 14 | 12,72 | OK | 1,28 |
| [ETI-19](https://kaueamaral96.atlassian.net/browse/ETI-19) | GESTÃO | Sprint 2 | CONCLUIDO | [GESTÃO] Estruturar base de Gestão, Cerimônias e Auditoria de Não-Conformidades | 1 | 3,08 | Fora da faixa | 0 |
| [ETI-20](https://kaueamaral96.atlassian.net/browse/ETI-20) | DESIGN | Sprint 4 | CONCLUIDO | [DESIGN] Prototipação de alta fidelidade das interfaces do aplicativo LIMIO | 70,5 | 67,45 | OK | 3,05 |
| [ETI-21](https://kaueamaral96.atlassian.net/browse/ETI-21) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Escrever Termos de Aceite e Politica de Privacidade da LIMIO | 8 | 7,39 | OK | 0,61 |
| [ETI-23](https://kaueamaral96.atlassian.net/browse/ETI-23) | DEV | Sprint 3 | CONCLUIDO | [DEV] Criação de Repositório para o projeto LIMIO | 4,5 | 2,05 | Fora da faixa | 2,45 |
| [ETI-24](https://kaueamaral96.atlassian.net/browse/ETI-24) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Atualizar Documento de Requisitos e UC para refletir as mudanças | 3 | 2,83 | OK | 0,17 |
| [ETI-25](https://kaueamaral96.atlassian.net/browse/ETI-25) | SUBTAREFA | Sprint 2 | CONCLUIDO | Criacao do DIAGRAMA DE ENTIDADE E RELACIONAMENTO  | 6,6 | 0 | Sem lançamento | 6,6 |
| [ETI-26](https://kaueamaral96.atlassian.net/browse/ETI-26) | REUNIÃO | Sprint 3 | CONCLUIDO | [REUNIÃO] Alinhamento entre equipe | 8,5 | 9,08 | OK | 0 |
| [ETI-27](https://kaueamaral96.atlassian.net/browse/ETI-27) | AEP | Sprint 3 | CONCLUIDO | [AEP] Preparo de entrega 1 (Agente Validação de código) | 39 | 12,43 | Fora da faixa | 26,57 |
| [ETI-28](https://kaueamaral96.atlassian.net/browse/ETI-28) | DEV | Sprint 3 | CONCLUIDO | [DEV] Setup Inicial dos Repositórios limio-api e limio-app | 4,5 | 4,65 | OK | 0 |
| [ETI-29](https://kaueamaral96.atlassian.net/browse/ETI-29) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Ajustar os docs de especificação, caso de uso e validar se precisa atualizar os diagramas | 1 | 0,84 | OK | 0,16 |
| [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) | BACK-END | Sprint 6 | CONCLUIDO | [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail | 7,5 | 6,87 | OK | 0,63 |
| [ETI-32](https://kaueamaral96.atlassian.net/browse/ETI-32) | BACK-END | Sprint 5 | CONCLUIDO | [auth] [BACK-END] Autenticar, renovar sessão, encerrar sessão e trocar papel ativo | 8,5 | 7,66 | OK | 0,84 |
| [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) | BACK-END | Sprint 6 | CONCLUIDO | [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada | 11 | 1,58 | Fora da faixa | 9,42 |
| [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) | BACK-END | Sprint 5 | CONCLUIDO | [conta] [BACK-END] Consultar e atualizar preferências de notificação | 9 | 8,95 | OK | 0,05 |
| [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criacão de ADR's | 3,5 | 6,63 | Fora da faixa | 0 |
| [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) | BACK-END | Sprint 6 | CONCLUIDO | [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria | 17 | 5,87 | Fora da faixa | 11,13 |
| [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) | INFRA | Sprint 4 | CONCLUIDO | [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod) | 1 | 9,73 | Fora da faixa | 0 |
| [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel | 4 | 3,58 | OK | 0,42 |
| [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha | 8 | 7,46 | OK | 0,54 |
| [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Fluxo de cadastro em 3 passos | 6 | 5,43 | OK | 0,57 |
| [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Toggles de notificação em Ajustes | 2 | 2,03 | OK | 0 |
| [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Tela "Encerrar conta" | 4,5 | 6,83 | Fora da faixa | 0 |
| [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) | SUBTAREFA | Sprint 6 | CONCLUIDO | remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ | 9 | 4,56 | Fora da faixa | 4,44 |
| [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) | INFRA | Sprint 5 | CONCLUIDO | [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails | 1,5 | 1,12 | OK | 0,38 |
| [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada | 13,5 | 6,09 | Fora da faixa | 7,41 |
| [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) | BACK-END | Sprint 7 | CONCLUIDO | [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha" | 6,5 | 7,84 | OK | 0 |
| [ETI-48](https://kaueamaral96.atlassian.net/browse/ETI-48) | BACK-END | Sprint 5 | CONCLUIDO | [empregador] [BACK-END] Consultar e editar o perfil de Empregador | 12 | 10,71 | OK | 1,29 |
| [ETI-49](https://kaueamaral96.atlassian.net/browse/ETI-49) | FRONT-END | Sprint 5 | CONCLUIDO | [empregador] [FRONT-END] Telas "Meu perfil" e "Dados de contato" | 5 | 4,38 | OK | 0,62 |
| [ETI-50](https://kaueamaral96.atlassian.net/browse/ETI-50) | BACK-END | Sprint 6 | CONCLUIDO | [empregador] [BACK-END] Cadastrar, editar, remover e marcar endereço padrão | 5 | 17,73 | Fora da faixa | 0 |
| [ETI-51](https://kaueamaral96.atlassian.net/browse/ETI-51) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Telas "Endereços salvos" e "Novo endereço" | 6,5 | 3,16 | Fora da faixa | 3,34 |
| [ETI-52](https://kaueamaral96.atlassian.net/browse/ETI-52) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar os anúncios do Empregador para o painel | 4,5 | 7,34 | Fora da faixa | 0 |
| [ETI-53](https://kaueamaral96.atlassian.net/browse/ETI-53) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Tela "Início" do Empregador e barra de navegação | 5,5 | 1,26 | Fora da faixa | 4,24 |
| [ETI-54](https://kaueamaral96.atlassian.net/browse/ETI-54) | BACK-END | Sprint 5 | CONCLUIDO | [prestador] [BACK-END] Salvar o perfil de atuação e calcular "perfil completo" | 5,5 | 4,81 | OK | 0,69 |
| [ETI-55](https://kaueamaral96.atlassian.net/browse/ETI-55) | FRONT-END | Sprint 5 | CONCLUIDO | [prestador] [FRONT-END] Telas "Perfil de atuação" e "Especialidades" | 5,5 | 5,06 | OK | 0,44 |
| [ETI-56](https://kaueamaral96.atlassian.net/browse/ETI-56) | BACK-END | Sprint 5 | CONCLUIDO | [perfil] [BACK-END] Enviar e trocar a foto de perfil | 4 | 3,77 | OK | 0,23 |
| [ETI-57](https://kaueamaral96.atlassian.net/browse/ETI-57) | FRONT-END | Sprint 6 | CONCLUIDO | [perfil] [FRONT-END] Trocar a foto em "Meu perfil" | 3,5 | 3,69 | OK | 0 |
| [ETI-58](https://kaueamaral96.atlassian.net/browse/ETI-58) | SUBTAREFA | Sprint 5 | CONCLUIDO | Adicionar novos membros como Code Oweners | 0,5 | 0 | Sem lançamento | 0,5 |
| [ETI-59](https://kaueamaral96.atlassian.net/browse/ETI-59) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Criar e publicar anúncio, com fotos | 16 | 9,66 | Fora da faixa | 6,34 |
| [ETI-60](https://kaueamaral96.atlassian.net/browse/ETI-60) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Novo anúncio", "Categoria" e "Anúncio publicado" | 13,5 | 4,06 | Fora da faixa | 9,44 |
| [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Editar anúncio antes da escolha | 6,5 | 5,87 | OK | 0,63 |
| [ETI-62](https://kaueamaral96.atlassian.net/browse/ETI-62) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Tela "Editar anúncio" | 4,5 | 5,25 | OK | 0 |
| [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Cancelar anúncio antes da escolha | 5,5 | 4 | OK | 1,5 |
| [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?" | 2 | 5,31 | Fora da faixa | 0 |
| [ETI-65](https://kaueamaral96.atlassian.net/browse/ETI-65) | BACK-END | Sprint 7 | PARA AJUSTE | [anuncio] [BACK-END] Avisar os prestadores compatíveis quando um anúncio é publicado | 11 | 11,33 | OK | 0 |
| [ETI-66](https://kaueamaral96.atlassian.net/browse/ETI-66) | BACK-END | Sprint 7 | AJUSTANDO | [anuncio] [BACK-END] Rotina de expiração de anúncios sem candidatos | 5,5 | 8,06 | Fora da faixa | 0 |
| [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato | 8 | 7,4 | OK | 0,6 |
| [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar | 5,5 | 4,95 | OK | 0,55 |
| [ETI-69](https://kaueamaral96.atlassian.net/browse/ETI-69) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Escolher o prestador: transação atômica, cota e liberação do contato | 16 | 6,69 | Fora da faixa | 9,31 |
| [ETI-70](https://kaueamaral96.atlassian.net/browse/ETI-70) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Confirmar escolha e "Não foi possível escolher" | 3,5 | 4,62 | Fora da faixa | 0 |
| [ETI-71](https://kaueamaral96.atlassian.net/browse/ETI-71) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Consultar histórico de anúncios e serviços com filtros | 8 | 0,33 | Em andamento | 7,67 |
| [ETI-72](https://kaueamaral96.atlassian.net/browse/ETI-72) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Tela "Histórico" do Empregador | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador | 13,5 | 8,22 | Fora da faixa | 5,28 |
| [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio" | 13,5 | 1,58 | Fora da faixa | 11,92 |
| [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Candidatar-se a um anúncio | 8 | 3,32 | Fora da faixa | 4,68 |
| [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?" | 2 | 4,49 | Fora da faixa | 0 |
| [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente | 6,5 | 6,35 | OK | 0,15 |
| [ETI-78](https://kaueamaral96.atlassian.net/browse/ETI-78) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Tela "Aplicações" (pendentes, combinadas e histórico), com desistir | 6,5 | 6,33 | OK | 0,17 |
| [ETI-79](https://kaueamaral96.atlassian.net/browse/ETI-79) | BACK-END | Sprint 6 | CONCLUIDO | [perfil] [BACK-END] Consultar a cota do mês e zerar na virada do mês | 6,5 | 3,97 | Fora da faixa | 2,53 |
| [ETI-80](https://kaueamaral96.atlassian.net/browse/ETI-80) | FRONT-END | Sprint 7 | CONCLUIDO | [perfil] [FRONT-END] Faixa de cota no mural e tela "Cota do mês" | 3,5 | 2,92 | OK | 0,58 |
| [ETI-81](https://kaueamaral96.atlassian.net/browse/ETI-81) | BACK-END | Sprint 7 | CONCLUIDO | [financeiro] [BACK-END] Assinar o GOLD pelo gateway de pagamento | 18,5 | 1,77 | Fora da faixa | 16,73 |
| [ETI-82](https://kaueamaral96.atlassian.net/browse/ETI-82) | FRONT-END | Sprint 7 | EM PROGRESSO | [financeiro] [FRONT-END] Tela "Assinatura" (assinar GOLD) | 5,5 | 5,74 | OK | 0 |
| [ETI-83](https://kaueamaral96.atlassian.net/browse/ETI-83) | BACK-END | Sprint 7 | À TESTAR | [financeiro] [BACK-END] Gerenciar a assinatura GOLD: consultar, trocar cartão e cancelar renovação | 11 | 1,85 | Em andamento | 9,15 |
| [ETI-84](https://kaueamaral96.atlassian.net/browse/ETI-84) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura GOLD" (gerenciar) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-85](https://kaueamaral96.atlassian.net/browse/ETI-85) | BACK-END | Sprint 7 | EM PROGRESSO | [financeiro] [BACK-END] Renovação mensal do GOLD: cobrança, falha, novas tentativas e volta ao FREE | 16 | 0 | Sem lançamento | 16 |
| [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados | 5,5 | 5,3 | OK | 0,2 |
| [ETI-87](https://kaueamaral96.atlassian.net/browse/ETI-87) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Serviço combinado" (Empregador) e "Seu serviço" (Prestador) | 6,5 | 5,49 | OK | 1,01 |
| [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Iniciar o serviço | 4,5 | 6,39 | Fora da faixa | 0 |
| [ETI-89](https://kaueamaral96.atlassian.net/browse/ETI-89) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Botão "Iniciar serviço" e tela "Serviço em andamento" | 4,5 | 8,88 | Fora da faixa | 0 |
| [ETI-90](https://kaueamaral96.atlassian.net/browse/ETI-90) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Fazer o check-out com foto | 6,5 | 6,67 | OK | 0 |
| [ETI-91](https://kaueamaral96.atlassian.net/browse/ETI-91) | FRONT-END | Sprint 7 | CONCLUIDO | [anuncio] [FRONT-END] Tela "Checkout" | 5,5 | 5,18 | OK | 0,32 |
| [ETI-92](https://kaueamaral96.atlassian.net/browse/ETI-92) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Validar o serviço (presencial ou pela foto) | 8 | 2,88 | Fora da faixa | 5,12 |
| [ETI-93](https://kaueamaral96.atlassian.net/browse/ETI-93) | FRONT-END | Sprint 7 | AJUSTANDO | [anuncio] [FRONT-END] Tela "Validar serviço" | 4,5 | 4,47 | OK | 0,03 |
| [ETI-94](https://kaueamaral96.atlassian.net/browse/ETI-94) | BACK-END | Sprint 7 | CONCLUIDO | [anuncio] [BACK-END] Empregador cancelar o serviço combinado (24h ou mais) | 6,5 | 9,71 | Fora da faixa | 0 |
| [ETI-95](https://kaueamaral96.atlassian.net/browse/ETI-95) | FRONT-END | Sprint 7 | EM PROGRESSO | [anuncio] [FRONT-END] Confirmação "Cancelar o serviço combinado" | 2 | 0 | Sem lançamento | 2 |
| [ETI-96](https://kaueamaral96.atlassian.net/browse/ETI-96) | BACK-END | Sprint 7 | À TESTAR | [anuncio] [BACK-END] Prestador cancelar depois de escolhido | 6,5 | 6,36 | OK | 0,14 |
| [ETI-97](https://kaueamaral96.atlassian.net/browse/ETI-97) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Confirmação "Cancelar este serviço?" (Prestador) | 2 | 0 | Sem lançamento | 2 |
| [ETI-98](https://kaueamaral96.atlassian.net/browse/ETI-98) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Rotina de conclusão automática por silêncio | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-99](https://kaueamaral96.atlassian.net/browse/ETI-99) | BACK-END | Sprint 7 | EM PROGRESSO | [anuncio] [BACK-END] Reagendar: propor, cancelar proposta, responder e expirar | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-100](https://kaueamaral96.atlassian.net/browse/ETI-100) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Telas "Propor reagendamento" e "Proposta recebida" | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) | BACK-END | Sprint 6 | CONCLUIDO | [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida | 23 | 9,92 | Fora da faixa | 13,08 |
| [ETI-102](https://kaueamaral96.atlassian.net/browse/ETI-102) | FRONT-END | Sprint 7 | CONCLUIDO | [chat] [FRONT-END] Telas "Chat" e "Chat somente leitura" | 13,5 | 3,42 | Fora da faixa | 10,08 |
| [ETI-103](https://kaueamaral96.atlassian.net/browse/ETI-103) | BACK-END | Sprint 7 | À TESTAR | [chat] [BACK-END] Listar minhas conversas por papel | 4,5 | 6,6 | Fora da faixa | 0 |
| [ETI-104](https://kaueamaral96.atlassian.net/browse/ETI-104) | FRONT-END | Sprint 7 | À TESTAR | [chat] [FRONT-END] Tela "Conversas" (Empregador e Prestador) | 4,5 | 2,42 | Em andamento | 2,08 |
| [ETI-105](https://kaueamaral96.atlassian.net/browse/ETI-105) | BACK-END | Sprint 7 | CONCLUIDO | [perfil] [BACK-END] Consultar o perfil público e a reputação | 5,5 | 4,75 | OK | 0,75 |
| [ETI-106](https://kaueamaral96.atlassian.net/browse/ETI-106) | FRONT-END | Sprint 7 | AJUSTANDO | [perfil] [FRONT-END] Telas "Perfil público" (candidato e consulta) | 4,5 | 9,78 | Fora da faixa | 0 |
| [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) | BACK-END | Sprint 7 | CONCLUIDO | [moderacao] [BACK-END] Avaliar a outra parte ou pular | 6,5 | 3,21 | Fora da faixa | 3,29 |
| [ETI-108](https://kaueamaral96.atlassian.net/browse/ETI-108) | FRONT-END | Sprint 7 | CONCLUIDO | [moderacao] [FRONT-END] Tela "Avaliação" | 3,5 | 2,23 | Fora da faixa | 1,27 |
| [ETI-109](https://kaueamaral96.atlassian.net/browse/ETI-109) | BACK-END | Sprint 7 | CONCLUIDO | [auth] [BACK-END] Rotina diária de limpeza de dados vencidos (LGPD) | 9 | 1,05 | Fora da faixa | 7,95 |
| [ETI-110](https://kaueamaral96.atlassian.net/browse/ETI-110) | BACK-END | Sprint 7 | PARA AJUSTE | [notificacao] [BACK-END] Listar minhas notificações e marcar como lidas | 4,5 | 7,98 | Fora da faixa | 0 |
| [ETI-111](https://kaueamaral96.atlassian.net/browse/ETI-111) | FRONT-END | Sprint 7 | CONCLUIDO | [notificacao] [FRONT-END] Tela "Notificações" | 4,5 | 7,84 | Fora da faixa | 0 |
| [ETI-112](https://kaueamaral96.atlassian.net/browse/ETI-112) | BACK-END | Sprint 7 | PARA AJUSTE | [notificacao] [BACK-END] Serviço único de envio de notificações, respeitando as preferências | 20,5 | 6,37 | Em andamento | 14,13 |
| [ETI-113](https://kaueamaral96.atlassian.net/browse/ETI-113) | FRONT-END | Sprint 7 | CONCLUIDO | [notificacao] [FRONT-END] Registrar o aparelho para push e abrir a tela certa ao tocar no aviso | 9 | 3,97 | Fora da faixa | 5,03 |
| [ETI-114](https://kaueamaral96.atlassian.net/browse/ETI-114) | BACK-END | Sprint 7 | EM PROGRESSO | [moderacao] [BACK-END] Registrar denúncia | 5,5 | 2,15 | Em andamento | 3,35 |
| [ETI-115](https://kaueamaral96.atlassian.net/browse/ETI-115) | FRONT-END | Sprint 7 | EM PROGRESSO | [moderacao] [FRONT-END] Tela "Abrir denúncia" | 3,5 | 2,39 | Em andamento | 1,11 |
| [ETI-116](https://kaueamaral96.atlassian.net/browse/ETI-116) | BACK-END | Sprint 7 | EM PROGRESSO | [moderacao] [BACK-END] Admin analisar denúncia e aplicar sanção | 11 | 2,59 | Em andamento | 8,41 |
| [ETI-117](https://kaueamaral96.atlassian.net/browse/ETI-117) | BACK-END | Sprint 7 | EM PROGRESSO | [administracao] [BACK-END] Dashboard administrativo com os números da operação | 8 | 6,85 | OK | 1,15 |
| [ETI-118](https://kaueamaral96.atlassian.net/browse/ETI-118) | FRONT-END | Sprint 7 | EM PROGRESSO | [administracao] [FRONT-END] Área do admin: fila de denúncias, análise, sanção e dashboard | 16 | 5,27 | Em andamento | 10,73 |
| [ETI-119](https://kaueamaral96.atlassian.net/browse/ETI-119) | SUBTAREFA | Sprint 7 | CONCLUIDO | Remover .env do front end | 1 | 0 | Sem lançamento | 1 |
| [ETI-120](https://kaueamaral96.atlassian.net/browse/ETI-120) | SUBTAREFA | Sprint 7 | CONCLUIDO | atualizar secure e cors do projeto para teste local | 1 | 0 | Sem lançamento | 1 |
| [ETI-121](https://kaueamaral96.atlassian.net/browse/ETI-121) | QA | Sprint 7 | À FAZER | [QA] Homologação de ponta a ponta dos fluxos do MVP | 40 | 0 | Sem lançamento | 40 |
| [ETI-122](https://kaueamaral96.atlassian.net/browse/ETI-122) | QA | Sprint 7 | À FAZER | [QA] Correção dos bugs encontrados na homologação | 40 | 0 | Sem lançamento | 40 |
| [ETI-123](https://kaueamaral96.atlassian.net/browse/ETI-123) | INFRA | Sprint 7 | EM PROGRESSO | [INFRA] Publicação do app na Play Store | 15 | 10,07 | Em andamento | 4,93 |
| [ETI-124](https://kaueamaral96.atlassian.net/browse/ETI-124) | INFRA | Sprint 7 | EM PROGRESSO | [INFRA] Deploy de produção: develop para main, migrations, variáveis e smoke test | 20 | 16,86 | OK | 3,14 |
| [ETI-125](https://kaueamaral96.atlassian.net/browse/ETI-125) | DOCS | Sprint 7 | À FAZER | [DOCS] Apresentação e documentação final da entrega | 25 | 0 | Sem lançamento | 25 |
| [ETI-126](https://kaueamaral96.atlassian.net/browse/ETI-126) | DOCS | Sprint 7 | À FAZER | [DOCS] Emenda ao ADR-0001: convenção de pastas por módulo (v2) | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-127](https://kaueamaral96.atlassian.net/browse/ETI-127) | DEBT | Sprint 7 | À FAZER | [DEBT] Aplicar convenção de pastas — entidade, repository/, modelos/ | 8 | 0 | Sem lançamento | 8 |
| [ETI-134](https://kaueamaral96.atlassian.net/browse/ETI-134) | BACK-END | Sprint 7 | CONCLUIDO | [auth] [BACK-END] Trocar a confirmação por SMS pela confirmação só por e-mail | 8 | 2,62 | Fora da faixa | 5,38 |
| [ETI-135](https://kaueamaral96.atlassian.net/browse/ETI-135) | FRONT-END | Sprint 7 | CONCLUIDO | [auth] [FRONT-END] Busca por CEP e remoção do SMS do app | 7 | 0,62 | Fora da faixa | 6,38 |
| [ETI-136](https://kaueamaral96.atlassian.net/browse/ETI-136) | SUBTAREFA | Sprint 7 | CONCLUIDO | [anuncio/chat] [BACK-END] Devolver o id do usuário nas telas que abrem o perfil público | — | 0,49 | Sem estimativa | — |
| [ETI-137](https://kaueamaral96.atlassian.net/browse/ETI-137) | SUBTAREFA | Sprint 7 | CONCLUIDO | desenho de tela admin figma | — | 0 | Sem estimativa | — |
| [ETI-138](https://kaueamaral96.atlassian.net/browse/ETI-138) | SUBTAREFA | Sprint 7 | CONCLUIDO | [BACK-END] devolver o id da candidatura no servico combinado | — | 0,34 | Sem estimativa | — |
| **Total** | | | | **122 cards** | **1.047** | **654,03** | | **479,15** |
