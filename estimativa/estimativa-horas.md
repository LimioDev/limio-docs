# Estimativa de horas do produto — LIMIO

> **Situação em 08/11/2026.** Status, sprint e responsável de cada card vêm do Jira (projeto ETI) nessa data. As horas **card a card** são as do Clockify de cada integrante copiadas em **01/11/2026**, mais as cerimônias e dailies até 01/11. O **total do time em 08/11** (603,64 h) também vem do Clockify, mas ainda sem o detalhe por card (veja [De onde vêm as horas](#de-onde-vêm-as-horas)). Mesmos dados de [`estimativa-horas.csv`](estimativa-horas.csv), que abre no Excel ou no Google Sheets.
> Planilha de trabalho anexada à página [Controle de Horas do Backlog](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/26476545) no Confluence.

## Resumo

| Indicador | Valor |
| --- | ---: |
| Total estimado do produto (MVP) | **1.032 h** |
| **Horas lançadas no Clockify pelo time até 08/11** | **603,64 h** |
| Medidas em detalhe até 01/11 | 548,24 h |
| · em cards do backlog | 403,69 h (39,1% do estimado) |
| · sem card | 2,05 h |
| · cerimônias: plannings, retrospectives e reviews | 100 h (20 h por integrante) |
| · dailies | 42,5 h (8,5 h por integrante) |
| Lançadas depois de 01/11, ainda sem detalhe por card | 55,4 h |
| Saldo (estimado − trabalhado até 01/11, todos os cards) | 667,83 h |
| Saldo só dos cards ainda não concluídos | 498,86 h |
| Cards | 117 |
| Cards dentro da faixa de ±30% | 33 |
| Cards acima de 130% | 7 (ETI-10, ETI-37, ETI-42, ETI-50, ETI-52, ETI-64, ETI-76) |
| Cards concluídos até 01/11 abaixo de 70% | 11 (ETI-4, ETI-23, ETI-27, ETI-44, ETI-51, ETI-53, ETI-59, ETI-60, ETI-74, ETI-79, ETI-101) |
| Cards concluídos depois de 01/11, aguardando as horas finais | 5 (ETI-33, ETI-36, ETI-46, ETI-67, ETI-73) |
| Cards em andamento, ainda abaixo de 70% | 4 |
| Cards sem horas até 01/11 | 57 |

## Como a estimativa foi feita

1. **Escopo:** todos os cards do Jira do projeto, da documentação inicial (agosto) até a Sprint 7 (fim do MVP), incluindo reuniões, design, documentação, back-end e front-end.
2. **Cards que já tinham horas na época da estimativa:** a estimativa foi escolhida para que as horas fiquem entre 70% e 130% dela.
3. **Cards ainda não iniciados:** estimados pelo escopo da descrição do card (quantidade de telas, cenários de teste, rotinas automáticas, integrações externas e pendências).
4. **Referência do próprio time:** mediana de 7,2 h por card de back-end e 4,3 h por card de front-end, medida nos cards já concluídos.
5. **Fechamento:** as estimativas base foram multiplicadas por um fator único (1,12) para fechar o total combinado pelo time de 1.000 h, e arredondadas para 0,5 h (exceções: ETI-10 e ETI-25). Depois entrou a subtarefa ETI-120 (1 h), o que levou o total a 1.001 h.
6. **Revisão de 01/11:** a estimativa do ETI-40 foi corrigida de 126,5 h para 6 h (veja abaixo) e entraram cinco cards da Sprint 7 que faltavam no backlog: homologação do MVP (ETI-121, 40 h), correção dos bugs da homologação (ETI-122, 40 h), publicação na Play Store (ETI-123, 15 h), deploy de produção (ETI-124, 20 h) e apresentação e documentação final (ETI-125, 25 h). O total passou a 1.020,5 h.
7. **Revisão de 08/11:** entraram os dois cards criados em 04/11 a partir da proposta de engenharia do Augusto: emenda ao ADR-0001 com a convenção de pastas por módulo (ETI-126, 3,5 h, mesmo porte do ETI-35, que criou as ADRs) e aplicação dessa convenção no código, movendo 34 arquivos em três PRs (ETI-127, 8 h, a mediana de um card de back-end). O total passou a 1.032 h. Os status e sprints de todos os cards foram atualizados pelo Jira; o ETI-123 (Play Store) e o ETI-124 (deploy de produção) passaram da Sprint 7 para a Sprint 6.

**Maiores incertezas:** chat em tempo real (ETI-101), assinatura GOLD com gateway de pagamento ainda não escolhido (ETI-81 e ETI-85) e envio de notificações em quatro canais (ETI-112).

**Leitura dos desvios:** a maior parte dos cards fora da faixa são cards concluídos com menos horas que o estimado, ou seja, estimativas altas. Isso será usado ao estimar os próximos cards.

### De onde vêm as horas

As horas foram medidas pelo Clockify, o cronômetro que cada integrante usa ao trabalhar em um card. Até 27/10 esta estimativa usava os lançamentos manuais do Jira, que tinham lançamentos repetidos e horas no card errado; por isso a fonte passou a ser o Clockify.

- **Andrey:** usou dois workspaces no Clockify ("kaueamaral96.atlassian.net" e "LIMIO"). As horas dele juntam os dois, contando uma vez só as entradas repetidas entre eles.
- **Augusto:** o Clockify enviado trazia só o total de cada dia. Em quatro dias com dois cards (02/09, 08/09, 09/10 e 21/10), o total do dia foi dividido igualmente entre os dois. Em 02/09 a segunda entrada não tinha card e ficou como "sem card" (2,05 h). Uma entrada de outro projeto foi excluída.

**Horas depois de 01/11:** em 08/11 o Clockify do time somava 603,64 h, 55,4 h a mais que o medido em 01/11. Essa diferença junta o trabalho de 02/11 a 08/11 (fim da Sprint 6), as dailies de 03, 04 e 05/11 e horas de code review que alguns integrantes lançaram depois, nos cards que revisaram. Os relatórios detalhados de cada integrante ainda não foram enviados, por isso essas horas entram no total, mas não na tabela card a card. Quando os relatórios chegarem, a tabela é atualizada e os cards com code review podem passar de 130%.

**Erro encontrado e corrigido em 01/11:** a estimativa do ETI-40 (fluxo de cadastro em 3 passos, front-end) tinha sido calibrada em 27/10 com as 112,97 h que estavam lançadas no Jira, o que levou a 126,5 h. A comparação com o Clockify mostrou que o lançamento estava errado e que o trabalho real foi de 5,43 h. A estimativa foi corrigida para 6 h. Esse erro foi o motivo de o Clockify passar a ser a fonte das horas.

### Cerimônias e dailies

Plannings, retrospectives, reviews e dailies não têm card no Jira. Por isso não entravam no Clockify nem no relatório de 01/11. Em novembro o time combinou lançar essas horas no Clockify de cada integrante, no mesmo horário para todos, com as descrições "Planning – Sprint X", "Retrospective e Review – Sprint X" e "Daily". Os cinco integrantes estiveram em todas.

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
| | | **Total** | **20** |

**Dailies:** 10 minutos, às 12:00, toda terça, quarta, quinta e domingo. De 05/08 a 01/11 foram 51 dailies, ou 8,5 h por integrante. As dailies de 03, 04 e 05/11 entram na próxima atualização, junto com as horas de cards depois de 01/11.

**Total:** 28,5 h por integrante, 142,5 h do time.

Essas horas não fazem parte da estimativa de 1.032 h, que cobre só os cards do backlog. Por isso elas aparecem no total trabalhado, mas não mudam o saldo nem a faixa ±30% de nenhum card. As cerimônias e dailies das Sprints 6 e 7 também não estão na estimativa.

### Regra da faixa ±30%

As horas usadas na faixa são as medidas card a card até 01/11; o status é o do Jira em 08/11.

| Faixa | Quando |
| --- | --- |
| OK | Trabalhado entre 70% e 130% da estimativa |
| Em andamento | Card ainda não concluído, abaixo de 70% |
| Fora da faixa | Trabalhado acima de 130%, ou card concluído até 01/11 abaixo de 70% |
| Aguardando horas | Card concluído depois de 01/11 e abaixo de 70%: as horas lançadas depois de 01/11 ainda não foram somadas |
| Sem lançamento | Card sem horas no Clockify até 01/11 |

## Horas por pessoa

Soma do Clockify de cada integrante até 01/11, a última data com o relatório detalhado de todos. As 55,4 h lançadas depois ainda não estão separadas por pessoa. Detalhe card a card em [`horas-por-pessoa.csv`](horas-por-pessoa.csv).

| Pessoa | Cards com horas | Em cards (h) | Cerimônias e dailies (h) | Total (h) | % do total |
| --- | ---: | ---: | ---: | ---: | ---: |
| Victor Hugo Rodrigues de Oliveira | 20 | 103,07 | 28,5 | 131,57 | 24,0% |
| Augusto Ogawa | 20 | 85,92 | 28,5 | 114,42 | 20,9% |
| Gabriel Sena | 13 | 72,76 | 28,5 | 101,26 | 18,5% |
| Andrey (andreyindras) | 12 | 72,56 | 28,5 | 101,06 | 18,4% |
| Kauê (kaueamaral96) | 24 | 71,43 | 28,5 | 99,93 | 18,2% |
| **Total** | | **405,74** | **142,5** | **548,24** | 100% |

As horas em cards do Augusto incluem 2,05 h sem card (veja acima).

## Por sprint

| Sprint | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| Sprint Inicial | 6 | 39,5 | 26,38 | 15,5 | 3,8% |
| Sprint 2 | 5 | 28 | 22,79 | 7,21 | 2,7% |
| Sprint 3 | 6 | 69,5 | 38,25 | 32,43 | 6,7% |
| Sprint 4 | 6 | 104,5 | 100,75 | 12,48 | 10,1% |
| Sprint 5 | 14 | 76 | 71,97 | 6,56 | 7,4% |
| Sprint 6 | 45 | 359,5 | 143,55 | 238,65 | 34,8% |
| Sprint 7 | 35 | 355 | 0 | 355 | 34,4% |

## Por status

Status do Jira em 08/11.

| Status | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| CONCLUIDO | 57 | 498,5 | 364,64 | 168,97 | 48,3% |
| À TESTAR | 7 | 57 | 9,45 | 47,55 | 5,5% |
| PARA AJUSTE | 3 | 15,5 | 3,17 | 12,33 | 1,5% |
| AJUSTANDO | 5 | 28,5 | 24,42 | 8,49 | 2,8% |
| EM PROGRESSO | 2 | 11,5 | 2,01 | 9,49 | 1,1% |
| À FAZER | 43 | 421 | 0 | 421 | 40,8% |

## Por camada

| Camada | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| AEP | 1 | 39 | 10,94 | 28,06 | 3,8% |
| BACK-END | 45 | 415 | 144,59 | 287,34 | 40,2% |
| DEBT | 1 | 8 | 0 | 8 | 0,8% |
| DESIGN | 1 | 70,5 | 63,37 | 7,13 | 6,8% |
| DEV | 2 | 9 | 6,2 | 2,8 | 0,9% |
| DOCS | 12 | 106,4 | 77,33 | 34,63 | 10,3% |
| FRONT-END | 37 | 211 | 65,25 | 154,05 | 20,4% |
| GESTÃO | 1 | 1 | 1 | 0 | 0,1% |
| INFRA | 4 | 37,5 | 10,85 | 35,38 | 3,6% |
| QA | 2 | 80 | 0 | 80 | 7,8% |
| REUNIÃO | 6 | 36,5 | 19,6 | 16,9 | 3,5% |
| SUBTAREFA | 5 | 18,1 | 4,56 | 13,54 | 1,8% |

## Todos os cards

| Ticket | Camada | Sprint | Status | Título | Estimativa (h) | Trabalhado (h) | Faixa ±30% | Saldo (h) |
| --- | --- | --- | --- | --- | ---: | ---: | --- | ---: |
| [ETI-2](https://kaueamaral96.atlassian.net/browse/ETI-2) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-3](https://kaueamaral96.atlassian.net/browse/ETI-3) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-4](https://kaueamaral96.atlassian.net/browse/ETI-4) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 14 | 6,5 | Fora da faixa | 7,5 |
| [ETI-5](https://kaueamaral96.atlassian.net/browse/ETI-5) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-6](https://kaueamaral96.atlassian.net/browse/ETI-6) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-7](https://kaueamaral96.atlassian.net/browse/ETI-7) | DOCS | Sprint Inicial | CONCLUIDO | [DOCS] Revisar e construir Requisitos e Regras de Negócio | 11,5 | 13,88 | OK | 0 |
| [ETI-8](https://kaueamaral96.atlassian.net/browse/ETI-8) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Revisar e Construir Casos de Uso | 12 | 12,38 | OK | 0 |
| [ETI-9](https://kaueamaral96.atlassian.net/browse/ETI-9) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Classes | 14,5 | 10,78 | OK | 3,72 |
| [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Criação de Diagrama Entidade-Relacionamento | 0,4 | 2,02 | Fora da faixa | 0 |
| [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Criação do Diagrama de Casos de Uso | 10 | 11,18 | OK | 0 |
| [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Atividade | 14 | 12,72 | OK | 1,28 |
| [ETI-19](https://kaueamaral96.atlassian.net/browse/ETI-19) | GESTÃO | Sprint 2 | CONCLUIDO | [GESTÃO] Estruturar base de Gestão, Cerimônias e Auditoria de Não-Conformidades | 1 | 1 | OK | 0 |
| [ETI-20](https://kaueamaral96.atlassian.net/browse/ETI-20) | DESIGN | Sprint 4 | CONCLUIDO | [DESIGN] Prototipação de alta fidelidade das interfaces do aplicativo LIMIO | 70,5 | 63,37 | OK | 7,13 |
| [ETI-21](https://kaueamaral96.atlassian.net/browse/ETI-21) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Escrever Termos de Aceite e Politica de Privacidade da LIMIO | 8 | 7,39 | OK | 0,61 |
| [ETI-23](https://kaueamaral96.atlassian.net/browse/ETI-23) | DEV | Sprint 3 | CONCLUIDO | [DEV] Criação de Repositório para o projeto LIMIO | 4,5 | 2,05 | Fora da faixa | 2,45 |
| [ETI-24](https://kaueamaral96.atlassian.net/browse/ETI-24) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Atualizar Documento de Requisitos e UC para refletir as mudanças | 3 | 2,83 | OK | 0,17 |
| [ETI-25](https://kaueamaral96.atlassian.net/browse/ETI-25) | SUBTAREFA | Sprint 2 | CONCLUIDO | Criacao do DIAGRAMA DE ENTIDADE E RELACIONAMENTO  | 6,6 | 0 | Sem lançamento | 6,6 |
| [ETI-26](https://kaueamaral96.atlassian.net/browse/ETI-26) | REUNIÃO | Sprint 3 | CONCLUIDO | [REUNIÃO] Alinhamento entre equipe | 8,5 | 7,1 | OK | 1,4 |
| [ETI-27](https://kaueamaral96.atlassian.net/browse/ETI-27) | AEP | Sprint 3 | CONCLUIDO | [AEP] Preparo de entrega 1 (Agente Validação de código) | 39 | 10,94 | Fora da faixa | 28,06 |
| [ETI-28](https://kaueamaral96.atlassian.net/browse/ETI-28) | DEV | Sprint 3 | CONCLUIDO | [DEV] Setup Inicial dos Repositórios limio-api e limio-app | 4,5 | 4,15 | OK | 0,35 |
| [ETI-29](https://kaueamaral96.atlassian.net/browse/ETI-29) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Ajustar os docs de especificação, caso de uso e validar se precisa atualizar os diagramas | 1 | 0,84 | OK | 0,16 |
| [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) | BACK-END | Sprint 6 | CONCLUIDO | [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail | 7,5 | 6,87 | OK | 0,63 |
| [ETI-32](https://kaueamaral96.atlassian.net/browse/ETI-32) | BACK-END | Sprint 5 | CONCLUIDO | [auth] [BACK-END] Autenticar, renovar sessão, encerrar sessão e trocar papel ativo | 8,5 | 7,66 | OK | 0,84 |
| [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) | BACK-END | Sprint 6 | CONCLUIDO | [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada | 11 | 1,58 | Aguardando horas | 9,42 |
| [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) | BACK-END | Sprint 5 | CONCLUIDO | [conta] [BACK-END] Consultar e atualizar preferências de notificação | 9 | 8,95 | OK | 0,05 |
| [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criacão de ADR's | 3,5 | 3,31 | OK | 0,19 |
| [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) | BACK-END | Sprint 6 | CONCLUIDO | [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria | 17 | 5,87 | Aguardando horas | 11,13 |
| [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) | INFRA | Sprint 4 | CONCLUIDO | [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod) | 1 | 9,73 | Fora da faixa | 0 |
| [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel | 4 | 3,58 | OK | 0,42 |
| [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha | 8 | 7,46 | OK | 0,54 |
| [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Fluxo de cadastro em 3 passos | 6 | 5,43 | OK | 0,57 |
| [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Toggles de notificação em Ajustes | 2 | 2,03 | OK | 0 |
| [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Tela "Encerrar conta" | 4,5 | 7 | Fora da faixa | 0 |
| [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) | SUBTAREFA | Sprint 6 | CONCLUIDO | remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ | 9 | 4,56 | Fora da faixa | 4,44 |
| [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) | INFRA | Sprint 5 | CONCLUIDO | [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails | 1,5 | 1,12 | OK | 0,38 |
| [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada | 13,5 | 6,09 | Aguardando horas | 7,41 |
| [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) | BACK-END | Sprint 6 | AJUSTANDO | [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha" | 6,5 | 7,82 | OK | 0 |
| [ETI-48](https://kaueamaral96.atlassian.net/browse/ETI-48) | BACK-END | Sprint 5 | CONCLUIDO | [empregador] [BACK-END] Consultar e editar o perfil de Empregador | 12 | 10,71 | OK | 1,29 |
| [ETI-49](https://kaueamaral96.atlassian.net/browse/ETI-49) | FRONT-END | Sprint 5 | CONCLUIDO | [empregador] [FRONT-END] Telas "Meu perfil" e "Dados de contato" | 5 | 4,38 | OK | 0,62 |
| [ETI-50](https://kaueamaral96.atlassian.net/browse/ETI-50) | BACK-END | Sprint 6 | CONCLUIDO | [empregador] [BACK-END] Cadastrar, editar, remover e marcar endereço padrão | 5 | 17,76 | Fora da faixa | 0 |
| [ETI-51](https://kaueamaral96.atlassian.net/browse/ETI-51) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Telas "Endereços salvos" e "Novo endereço" | 6,5 | 3,16 | Fora da faixa | 3,34 |
| [ETI-52](https://kaueamaral96.atlassian.net/browse/ETI-52) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar os anúncios do Empregador para o painel | 4,5 | 7,35 | Fora da faixa | 0 |
| [ETI-53](https://kaueamaral96.atlassian.net/browse/ETI-53) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Tela "Início" do Empregador e barra de navegação | 5,5 | 1,26 | Fora da faixa | 4,24 |
| [ETI-54](https://kaueamaral96.atlassian.net/browse/ETI-54) | BACK-END | Sprint 5 | CONCLUIDO | [prestador] [BACK-END] Salvar o perfil de atuação e calcular "perfil completo" | 5,5 | 4,81 | OK | 0,69 |
| [ETI-55](https://kaueamaral96.atlassian.net/browse/ETI-55) | FRONT-END | Sprint 5 | CONCLUIDO | [prestador] [FRONT-END] Telas "Perfil de atuação" e "Especialidades" | 5,5 | 5,07 | OK | 0,43 |
| [ETI-56](https://kaueamaral96.atlassian.net/browse/ETI-56) | BACK-END | Sprint 5 | CONCLUIDO | [perfil] [BACK-END] Enviar e trocar a foto de perfil | 4 | 3,77 | OK | 0,23 |
| [ETI-57](https://kaueamaral96.atlassian.net/browse/ETI-57) | FRONT-END | Sprint 6 | CONCLUIDO | [perfil] [FRONT-END] Trocar a foto em "Meu perfil" | 3,5 | 3,69 | OK | 0 |
| [ETI-58](https://kaueamaral96.atlassian.net/browse/ETI-58) | SUBTAREFA | Sprint 5 | CONCLUIDO | Adicionar novos membros como Code Oweners | 0,5 | 0 | Sem lançamento | 0,5 |
| [ETI-59](https://kaueamaral96.atlassian.net/browse/ETI-59) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Criar e publicar anúncio, com fotos | 16 | 9,67 | Fora da faixa | 6,33 |
| [ETI-60](https://kaueamaral96.atlassian.net/browse/ETI-60) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Novo anúncio", "Categoria" e "Anúncio publicado" | 13,5 | 4,06 | Fora da faixa | 9,44 |
| [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) | BACK-END | Sprint 6 | AJUSTANDO | [anuncio] [BACK-END] Editar anúncio antes da escolha | 6,5 | 4,19 | Em andamento | 2,31 |
| [ETI-62](https://kaueamaral96.atlassian.net/browse/ETI-62) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Editar anúncio" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) | BACK-END | Sprint 6 | AJUSTANDO | [anuncio] [BACK-END] Cancelar anúncio antes da escolha | 5,5 | 4 | OK | 1,5 |
| [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) | FRONT-END | Sprint 6 | AJUSTANDO | [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?" | 2 | 5,09 | Fora da faixa | 0 |
| [ETI-65](https://kaueamaral96.atlassian.net/browse/ETI-65) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Avisar os prestadores compatíveis quando um anúncio é publicado | 11 | 0 | Sem lançamento | 11 |
| [ETI-66](https://kaueamaral96.atlassian.net/browse/ETI-66) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Rotina de expiração de anúncios sem candidatos | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato | 8 | 4,22 | Aguardando horas | 3,78 |
| [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) | FRONT-END | Sprint 6 | À TESTAR | [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar | 5,5 | 4,96 | OK | 0,54 |
| [ETI-69](https://kaueamaral96.atlassian.net/browse/ETI-69) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Escolher o prestador: transação atômica, cota e liberação do contato | 16 | 0 | Sem lançamento | 16 |
| [ETI-70](https://kaueamaral96.atlassian.net/browse/ETI-70) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Confirmar escolha e "Não foi possível escolher" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-71](https://kaueamaral96.atlassian.net/browse/ETI-71) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Consultar histórico de anúncios e serviços com filtros | 8 | 0 | Sem lançamento | 8 |
| [ETI-72](https://kaueamaral96.atlassian.net/browse/ETI-72) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Tela "Histórico" do Empregador | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador | 13,5 | 8,22 | Aguardando horas | 5,28 |
| [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio" | 13,5 | 1,58 | Fora da faixa | 11,92 |
| [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) | BACK-END | Sprint 6 | AJUSTANDO | [anuncio] [BACK-END] Candidatar-se a um anúncio | 8 | 3,32 | Em andamento | 4,68 |
| [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?" | 2 | 4,49 | Fora da faixa | 0 |
| [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) | BACK-END | Sprint 6 | PARA AJUSTE | [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente | 6,5 | 3,17 | Em andamento | 3,33 |
| [ETI-78](https://kaueamaral96.atlassian.net/browse/ETI-78) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Aplicações" (pendentes, combinadas e histórico), com desistir | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-79](https://kaueamaral96.atlassian.net/browse/ETI-79) | BACK-END | Sprint 6 | CONCLUIDO | [perfil] [BACK-END] Consultar a cota do mês e zerar na virada do mês | 6,5 | 3,97 | Fora da faixa | 2,53 |
| [ETI-80](https://kaueamaral96.atlassian.net/browse/ETI-80) | FRONT-END | Sprint 6 | PARA AJUSTE | [perfil] [FRONT-END] Faixa de cota no mural e tela "Cota do mês" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-81](https://kaueamaral96.atlassian.net/browse/ETI-81) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Assinar o GOLD pelo gateway de pagamento | 18,5 | 0 | Sem lançamento | 18,5 |
| [ETI-82](https://kaueamaral96.atlassian.net/browse/ETI-82) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura" (assinar GOLD) | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-83](https://kaueamaral96.atlassian.net/browse/ETI-83) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Gerenciar a assinatura GOLD: consultar, trocar cartão e cancelar renovação | 11 | 0 | Sem lançamento | 11 |
| [ETI-84](https://kaueamaral96.atlassian.net/browse/ETI-84) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura GOLD" (gerenciar) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-85](https://kaueamaral96.atlassian.net/browse/ETI-85) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Renovação mensal do GOLD: cobrança, falha, novas tentativas e volta ao FREE | 16 | 0 | Sem lançamento | 16 |
| [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) | BACK-END | Sprint 6 | PARA AJUSTE | [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-87](https://kaueamaral96.atlassian.net/browse/ETI-87) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Telas "Serviço combinado" (Empregador) e "Seu serviço" (Prestador) | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Iniciar o serviço | 4,5 | 4,49 | OK | 0,01 |
| [ETI-89](https://kaueamaral96.atlassian.net/browse/ETI-89) | FRONT-END | Sprint 6 | À TESTAR | [anuncio] [FRONT-END] Botão "Iniciar serviço" e tela "Serviço em andamento" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-90](https://kaueamaral96.atlassian.net/browse/ETI-90) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Fazer o check-out com foto | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-91](https://kaueamaral96.atlassian.net/browse/ETI-91) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Checkout" | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-92](https://kaueamaral96.atlassian.net/browse/ETI-92) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Validar o serviço (presencial ou pela foto) | 8 | 0 | Sem lançamento | 8 |
| [ETI-93](https://kaueamaral96.atlassian.net/browse/ETI-93) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Validar serviço" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-94](https://kaueamaral96.atlassian.net/browse/ETI-94) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Empregador cancelar o serviço combinado (24h ou mais) | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-95](https://kaueamaral96.atlassian.net/browse/ETI-95) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Confirmação "Cancelar o serviço combinado" | 2 | 0 | Sem lançamento | 2 |
| [ETI-96](https://kaueamaral96.atlassian.net/browse/ETI-96) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Prestador cancelar depois de escolhido | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-97](https://kaueamaral96.atlassian.net/browse/ETI-97) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Confirmação "Cancelar este serviço?" (Prestador) | 2 | 0 | Sem lançamento | 2 |
| [ETI-98](https://kaueamaral96.atlassian.net/browse/ETI-98) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Rotina de conclusão automática por silêncio | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-99](https://kaueamaral96.atlassian.net/browse/ETI-99) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Reagendar: propor, cancelar proposta, responder e expirar | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-100](https://kaueamaral96.atlassian.net/browse/ETI-100) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Telas "Propor reagendamento" e "Proposta recebida" | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) | BACK-END | Sprint 6 | CONCLUIDO | [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida | 23 | 10,1 | Fora da faixa | 12,9 |
| [ETI-102](https://kaueamaral96.atlassian.net/browse/ETI-102) | FRONT-END | Sprint 6 | À TESTAR | [chat] [FRONT-END] Telas "Chat" e "Chat somente leitura" | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-103](https://kaueamaral96.atlassian.net/browse/ETI-103) | BACK-END | Sprint 7 | À FAZER | [chat] [BACK-END] Listar minhas conversas por papel | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-104](https://kaueamaral96.atlassian.net/browse/ETI-104) | FRONT-END | Sprint 7 | À FAZER | [chat] [FRONT-END] Tela "Conversas" (Empregador e Prestador) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-105](https://kaueamaral96.atlassian.net/browse/ETI-105) | BACK-END | Sprint 7 | À FAZER | [perfil] [BACK-END] Consultar o perfil público e a reputação | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-106](https://kaueamaral96.atlassian.net/browse/ETI-106) | FRONT-END | Sprint 7 | À FAZER | [perfil] [FRONT-END] Telas "Perfil público" (candidato e consulta) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) | BACK-END | Sprint 6 | À TESTAR | [moderacao] [BACK-END] Avaliar a outra parte ou pular | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-108](https://kaueamaral96.atlassian.net/browse/ETI-108) | FRONT-END | Sprint 6 | EM PROGRESSO | [moderacao] [FRONT-END] Tela "Avaliação" | 3,5 | 2,01 | Em andamento | 1,49 |
| [ETI-109](https://kaueamaral96.atlassian.net/browse/ETI-109) | BACK-END | Sprint 7 | À FAZER | [auth] [BACK-END] Rotina diária de limpeza de dados vencidos (LGPD) | 9 | 0 | Sem lançamento | 9 |
| [ETI-110](https://kaueamaral96.atlassian.net/browse/ETI-110) | BACK-END | Sprint 7 | À FAZER | [notificacao] [BACK-END] Listar minhas notificações e marcar como lidas | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-111](https://kaueamaral96.atlassian.net/browse/ETI-111) | FRONT-END | Sprint 7 | À FAZER | [notificacao] [FRONT-END] Tela "Notificações" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-112](https://kaueamaral96.atlassian.net/browse/ETI-112) | BACK-END | Sprint 7 | À FAZER | [notificacao] [BACK-END] Serviço único de envio de notificações, respeitando as preferências | 20,5 | 0 | Sem lançamento | 20,5 |
| [ETI-113](https://kaueamaral96.atlassian.net/browse/ETI-113) | FRONT-END | Sprint 7 | À FAZER | [notificacao] [FRONT-END] Registrar o aparelho para push e abrir a tela certa ao tocar no aviso | 9 | 0 | Sem lançamento | 9 |
| [ETI-114](https://kaueamaral96.atlassian.net/browse/ETI-114) | BACK-END | Sprint 7 | À FAZER | [moderacao] [BACK-END] Registrar denúncia | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-115](https://kaueamaral96.atlassian.net/browse/ETI-115) | FRONT-END | Sprint 7 | À FAZER | [moderacao] [FRONT-END] Tela "Abrir denúncia" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-116](https://kaueamaral96.atlassian.net/browse/ETI-116) | BACK-END | Sprint 7 | À FAZER | [moderacao] [BACK-END] Admin analisar denúncia e aplicar sanção | 11 | 0 | Sem lançamento | 11 |
| [ETI-117](https://kaueamaral96.atlassian.net/browse/ETI-117) | BACK-END | Sprint 7 | À FAZER | [administracao] [BACK-END] Dashboard administrativo com os números da operação | 8 | 0 | Sem lançamento | 8 |
| [ETI-118](https://kaueamaral96.atlassian.net/browse/ETI-118) | FRONT-END | Sprint 7 | À FAZER | [administracao] [FRONT-END] Área do admin: fila de denúncias, análise, sanção e dashboard | 16 | 0 | Sem lançamento | 16 |
| [ETI-119](https://kaueamaral96.atlassian.net/browse/ETI-119) | SUBTAREFA | Sprint 6 | CONCLUIDO | Remover .env do front end | 1 | 0 | Sem lançamento | 1 |
| [ETI-120](https://kaueamaral96.atlassian.net/browse/ETI-120) | SUBTAREFA | Sprint 6 | CONCLUIDO | atualizar secure e cors do projeto para teste local | 1 | 0 | Sem lançamento | 1 |
| [ETI-121](https://kaueamaral96.atlassian.net/browse/ETI-121) | QA | Sprint 7 | À FAZER | [QA] Homologação de ponta a ponta dos fluxos do MVP | 40 | 0 | Sem lançamento | 40 |
| [ETI-122](https://kaueamaral96.atlassian.net/browse/ETI-122) | QA | Sprint 7 | À FAZER | [QA] Correção dos bugs encontrados na homologação | 40 | 0 | Sem lançamento | 40 |
| [ETI-123](https://kaueamaral96.atlassian.net/browse/ETI-123) | INFRA | Sprint 6 | À FAZER | [INFRA] Publicação do app na Play Store | 15 | 0 | Sem lançamento | 15 |
| [ETI-124](https://kaueamaral96.atlassian.net/browse/ETI-124) | INFRA | Sprint 6 | À FAZER | [INFRA] Deploy de produção: develop para main, migrations, variáveis e smoke test | 20 | 0 | Sem lançamento | 20 |
| [ETI-125](https://kaueamaral96.atlassian.net/browse/ETI-125) | DOCS | Sprint 7 | À FAZER | [DOCS] Apresentação e documentação final da entrega | 25 | 0 | Sem lançamento | 25 |
| [ETI-126](https://kaueamaral96.atlassian.net/browse/ETI-126) | DOCS | Sprint 7 | À FAZER | [DOCS] Emenda ao ADR-0001: convenção de pastas por módulo (v2) | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-127](https://kaueamaral96.atlassian.net/browse/ETI-127) | DEBT | Sprint 7 | À FAZER | [DEBT] Aplicar convenção de pastas — entidade, repository/, modelos/ | 8 | 0 | Sem lançamento | 8 |
| **Total** | | | | **117 cards** | **1.032** | **403,69** | | **667,83** |
