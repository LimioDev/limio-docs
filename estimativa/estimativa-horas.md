# Estimativa de horas do produto — LIMIO

> Dados do Jira (projeto ETI) puxados em **27/10/2026**. Mesmos dados de [`estimativa-horas.csv`](estimativa-horas.csv), que abre no Excel ou no Google Sheets.
> Planilha de trabalho com fórmulas: anexada à página [Controle de Horas do Backlog](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/26476545) no Confluence.

## Resumo

| Indicador | Valor |
| --- | ---: |
| Total estimado do produto (MVP) | **1.001 h** |
| Horas já lançadas no Jira | 446,87 h (44,6%) |
| Saldo a fazer | 566,77 h |
| Cards | 110 |
| Cards dentro da faixa de ±30% | 34 |
| Cards fora da faixa | 5 (ETI-42, ETI-50, ETI-51, ETI-52, ETI-53) |
| Cards em andamento, ainda abaixo de 70% | 4 |
| Cards sem horas lançadas (não iniciados ou entregues sem lançamento) | 67 |

## Como a estimativa foi feita

1. **Escopo:** todos os cards do Jira do projeto, da documentação inicial (agosto) até a Sprint 7 (fim do MVP), incluindo reuniões, design, documentação, back-end e front-end.
2. **Cards que já têm horas lançadas:** a estimativa foi escolhida para que as horas lançadas fiquem entre 70% e 130% dela. Na média, o lançado ficou em torno de 89% do estimado.
3. **Cards ainda não iniciados:** estimados pelo escopo da descrição do card (quantidade de telas, cenários de teste, rotinas automáticas, integrações externas e pendências).
4. **Referência do próprio time:** mediana de 7,2 h por card de back-end e 4,3 h por card de front-end, medida nos cards já concluídos.
5. **Fechamento:** as estimativas base foram multiplicadas por um fator único (1,12) para fechar o total combinado pelo time de 1.000 h, e arredondadas para 0,5 h. Depois entrou a subtarefa ETI-120 (1 h), o que levou o total a 1.001 h.

**Maiores incertezas:** chat em tempo real (ETI-101), assinatura GOLD com gateway de pagamento ainda não escolhido (ETI-81 e ETI-85) e envio de notificações em quatro canais (ETI-112).

### Regra da faixa ±30%

| Faixa | Quando |
| --- | --- |
| OK | Lançado entre 70% e 130% da estimativa |
| Em andamento | Card ainda não concluído, abaixo de 70% |
| Fora da faixa | Lançado acima de 130%, ou card concluído abaixo de 70% |
| Sem lançamento | Card sem horas lançadas no Jira |

## Horas por pessoa

Soma de cada lançamento de horas no Jira pela pessoa que o registrou. Detalhe card a card em [`horas-por-pessoa.csv`](horas-por-pessoa.csv).

| Pessoa | Cards com lançamento | Lançado (h) | % do lançado |
| --- | ---: | ---: | ---: |
| Victor Hugo Rodrigues de Oliveira | 19 | 206,17 | 46,1% |
| Augusto Ogawa | 6 | 62,53 | 14% |
| Andrey (andreyindras) | 9 | 61,35 | 13,7% |
| Kauê (kaueamaral96) | 21 | 59,92 | 13,4% |
| Gabriel Sena | 11 | 56,92 | 12,7% |
| **Total** | | **446,88** | 100% |

## Por sprint

| Sprint | Cards | Estimado (h) | Lançado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| Sprint Inicial | 6 | 39,5 | 31,72 | 7,78 | 3,9% |
| Sprint 2 | 5 | 28 | 19,33 | 8,67 | 2,8% |
| Sprint 3 | 6 | 69,5 | 58,1 | 11,4 | 6,9% |
| Sprint 4 | 6 | 104,5 | 93,61 | 10,89 | 10,4% |
| Sprint 5 | 14 | 196,5 | 177,79 | 21,21 | 19,6% |
| Sprint 6 | 43 | 324,5 | 66,32 | 268,32 | 32,4% |
| Sprint 7 | 30 | 238,5 | 0 | 238,5 | 23,8% |

## Por status

| Status | Cards | Estimado (h) | Lançado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| CONCLUIDO | 45 | 474 | 408,07 | 78,57 | 47,4% |
| À TESTAR | 5 | 66,5 | 26,09 | 40,41 | 6,6% |
| AJUSTANDO | 2 | 18,5 | 6,7 | 11,8 | 1,8% |
| PARA AJUSTE | 1 | 13,5 | 4,03 | 9,47 | 1,3% |
| EM PROGRESSO | 6 | 53,5 | 1,98 | 51,52 | 5,3% |
| À FAZER | 51 | 375 | 0 | 375 | 37,5% |

## Por camada

| Camada | Cards | Estimado (h) | Lançado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| AEP | 1 | 39 | 34,9 | 4,1 | 3,9% |
| BACK-END | 45 | 415 | 86,75 | 338,21 | 41,5% |
| DESIGN | 1 | 70,5 | 63,17 | 7,33 | 7% |
| DEV | 2 | 9 | 3,83 | 5,17 | 0,9% |
| DOCS | 10 | 77,9 | 69,88 | 8,02 | 7,8% |
| FRONT-END | 37 | 331,5 | 157,36 | 176,82 | 33,1% |
| GESTÃO | 1 | 1 | 1 | 0 | 0,1% |
| INFRA | 2 | 2,5 | 1 | 1,5 | 0,2% |
| REUNIÃO | 6 | 36,5 | 28,98 | 7,52 | 3,6% |
| SUBTAREFA | 5 | 18,1 | 0 | 18,1 | 1,8% |

## Todos os cards

| Ticket | Camada | Sprint | Status | Título | Estimativa (h) | Lançado (h) | Faixa ±30% | Saldo (h) |
| --- | --- | --- | --- | --- | ---: | ---: | --- | ---: |
| [ETI-2](https://kaueamaral96.atlassian.net/browse/ETI-2) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-3](https://kaueamaral96.atlassian.net/browse/ETI-3) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-4](https://kaueamaral96.atlassian.net/browse/ETI-4) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 14 | 12,5 | OK | 1,5 |
| [ETI-5](https://kaueamaral96.atlassian.net/browse/ETI-5) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-6](https://kaueamaral96.atlassian.net/browse/ETI-6) | REUNIÃO | Sprint Inicial | CONCLUIDO | [REUNIÃO] Alinhamento de Regras de Negócio | 3,5 | 3 | OK | 0,5 |
| [ETI-7](https://kaueamaral96.atlassian.net/browse/ETI-7) | DOCS | Sprint Inicial | CONCLUIDO | [DOCS] Revisar e construir Requisitos e Regras de Negócio | 11,5 | 10,22 | OK | 1,28 |
| [ETI-8](https://kaueamaral96.atlassian.net/browse/ETI-8) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Revisar e Construir Casos de Uso | 12 | 10,68 | OK | 1,32 |
| [ETI-9](https://kaueamaral96.atlassian.net/browse/ETI-9) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Classes | 14,5 | 12,78 | OK | 1,72 |
| [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Criação de Diagrama Entidade-Relacionamento | 0,4 | 0,3 | OK | 0,1 |
| [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Criação do Diagrama de Casos de Uso | 10 | 9,07 | OK | 0,93 |
| [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criação de Diagrama de Atividade | 14 | 12,53 | OK | 1,47 |
| [ETI-19](https://kaueamaral96.atlassian.net/browse/ETI-19) | GESTÃO | Sprint 2 | CONCLUIDO | [GESTÃO] Estruturar base de Gestão, Cerimônias e Auditoria de Não-Conformidades | 1 | 1 | OK | 0 |
| [ETI-20](https://kaueamaral96.atlassian.net/browse/ETI-20) | DESIGN | Sprint 4 | CONCLUIDO | [DESIGN] Prototipação de alta fidelidade das interfaces do aplicativo LIMIO | 70,5 | 63,17 | OK | 7,33 |
| [ETI-21](https://kaueamaral96.atlassian.net/browse/ETI-21) | DOCS | Sprint 2 | CONCLUIDO | [DOCS] Escrever Termos de Aceite e Politica de Privacidade da LIMIO | 8 | 7,35 | OK | 0,65 |
| [ETI-23](https://kaueamaral96.atlassian.net/browse/ETI-23) | DEV | Sprint 3 | CONCLUIDO | [DEV] Criação de Repositório para o projeto LIMIO | 4,5 | 3,83 | OK | 0,67 |
| [ETI-24](https://kaueamaral96.atlassian.net/browse/ETI-24) | DOCS | Sprint 3 | CONCLUIDO | [DOCS] Atualizar Documento de Requisitos e UC para refletir as mudanças | 3 | 2,82 | OK | 0,18 |
| [ETI-25](https://kaueamaral96.atlassian.net/browse/ETI-25) | SUBTAREFA | Sprint 2 | CONCLUIDO | Criacao do DIAGRAMA DE ENTIDADE E RELACIONAMENTO  | 6,6 | 0 | Sem lançamento | 6,6 |
| [ETI-26](https://kaueamaral96.atlassian.net/browse/ETI-26) | REUNIÃO | Sprint 3 | CONCLUIDO | [REUNIÃO] Alinhamento entre equipe | 8,5 | 7,48 | OK | 1,02 |
| [ETI-27](https://kaueamaral96.atlassian.net/browse/ETI-27) | AEP | Sprint 3 | CONCLUIDO | [AEP] Preparo de entrega 1 (Agente Validação de código) | 39 | 34,9 | OK | 4,1 |
| [ETI-28](https://kaueamaral96.atlassian.net/browse/ETI-28) | DEV | Sprint 3 | CONCLUIDO | [DEV] Setup Inicial dos Repositórios limio-api e limio-app | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-29](https://kaueamaral96.atlassian.net/browse/ETI-29) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Ajustar os docs de especificação, caso de uso e validar se precisa atualizar os diagramas | 1 | 0,83 | OK | 0,17 |
| [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) | BACK-END | Sprint 6 | AJUSTANDO | [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail | 7,5 | 6,7 | OK | 0,8 |
| [ETI-32](https://kaueamaral96.atlassian.net/browse/ETI-32) | BACK-END | Sprint 5 | CONCLUIDO | [auth] [BACK-END] Autenticar, renovar sessão, encerrar sessão e trocar papel ativo | 8,5 | 7,62 | OK | 0,88 |
| [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) | BACK-END | Sprint 6 | AJUSTANDO | [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada | 11 | 0 | Sem lançamento | 11 |
| [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) | BACK-END | Sprint 5 | CONCLUIDO | [conta] [BACK-END] Consultar e atualizar preferências de notificação | 9 | 8,9 | OK | 0,1 |
| [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criacão de ADR's | 3,5 | 3,3 | OK | 0,2 |
| [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) | BACK-END | Sprint 6 | À TESTAR | [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria | 17 | 15,27 | OK | 1,73 |
| [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) | INFRA | Sprint 4 | CONCLUIDO | [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod) | 1 | 1 | OK | 0 |
| [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel | 4 | 3,55 | OK | 0,45 |
| [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha | 8 | 7,33 | OK | 0,67 |
| [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Fluxo de cadastro em 3 passos | 126,5 | 112,97 | OK | 13,53 |
| [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Toggles de notificação em Ajustes | 2 | 1,85 | OK | 0,15 |
| [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Tela "Encerrar conta" | 4,5 | 7 | Fora da faixa | 0 |
| [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) | SUBTAREFA | Sprint 6 | CONCLUIDO | remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ | 9 | 0 | Sem lançamento | 9 |
| [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) | INFRA | Sprint 5 | CONCLUIDO | [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails | 1,5 | 0 | Sem lançamento | 1,5 |
| [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) | BACK-END | Sprint 6 | À TESTAR | [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha" | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-48](https://kaueamaral96.atlassian.net/browse/ETI-48) | BACK-END | Sprint 5 | CONCLUIDO | [empregador] [BACK-END] Consultar e editar o perfil de Empregador | 12 | 10,65 | OK | 1,35 |
| [ETI-49](https://kaueamaral96.atlassian.net/browse/ETI-49) | FRONT-END | Sprint 5 | CONCLUIDO | [empregador] [FRONT-END] Telas "Meu perfil" e "Dados de contato" | 5 | 4,35 | OK | 0,65 |
| [ETI-50](https://kaueamaral96.atlassian.net/browse/ETI-50) | BACK-END | Sprint 6 | CONCLUIDO | [empregador] [BACK-END] Cadastrar, editar, remover e marcar endereço padrão | 5 | 12,18 | Fora da faixa | 0 |
| [ETI-51](https://kaueamaral96.atlassian.net/browse/ETI-51) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Telas "Endereços salvos" e "Novo endereço" | 6,5 | 3,13 | Fora da faixa | 3,37 |
| [ETI-52](https://kaueamaral96.atlassian.net/browse/ETI-52) | BACK-END | Sprint 6 | CONCLUIDO | [anuncio] [BACK-END] Listar os anúncios do Empregador para o painel | 4,5 | 7,28 | Fora da faixa | 0 |
| [ETI-53](https://kaueamaral96.atlassian.net/browse/ETI-53) | FRONT-END | Sprint 6 | CONCLUIDO | [empregador] [FRONT-END] Tela "Início" do Empregador e barra de navegação | 5,5 | 1,25 | Fora da faixa | 4,25 |
| [ETI-54](https://kaueamaral96.atlassian.net/browse/ETI-54) | BACK-END | Sprint 5 | CONCLUIDO | [prestador] [BACK-END] Salvar o perfil de atuação e calcular "perfil completo" | 5,5 | 4,77 | OK | 0,73 |
| [ETI-55](https://kaueamaral96.atlassian.net/browse/ETI-55) | FRONT-END | Sprint 5 | CONCLUIDO | [prestador] [FRONT-END] Telas "Perfil de atuação" e "Especialidades" | 5,5 | 5,07 | OK | 0,43 |
| [ETI-56](https://kaueamaral96.atlassian.net/browse/ETI-56) | BACK-END | Sprint 5 | CONCLUIDO | [perfil] [BACK-END] Enviar e trocar a foto de perfil | 4 | 3,73 | OK | 0,27 |
| [ETI-57](https://kaueamaral96.atlassian.net/browse/ETI-57) | FRONT-END | Sprint 6 | CONCLUIDO | [perfil] [FRONT-END] Trocar a foto em "Meu perfil" | 3,5 | 3,68 | OK | 0 |
| [ETI-58](https://kaueamaral96.atlassian.net/browse/ETI-58) | SUBTAREFA | Sprint 5 | CONCLUIDO | Adicionar novos membros como Code Oweners | 0,5 | 0 | Sem lançamento | 0,5 |
| [ETI-59](https://kaueamaral96.atlassian.net/browse/ETI-59) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Criar e publicar anúncio, com fotos | 16 | 9,65 | Em andamento | 6,35 |
| [ETI-60](https://kaueamaral96.atlassian.net/browse/ETI-60) | FRONT-END | Sprint 6 | PARA AJUSTE | [anuncio] [FRONT-END] Telas "Novo anúncio", "Categoria" e "Anúncio publicado" | 13,5 | 4,03 | Em andamento | 9,47 |
| [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Editar anúncio antes da escolha | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-62](https://kaueamaral96.atlassian.net/browse/ETI-62) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Editar anúncio" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Cancelar anúncio antes da escolha | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?" | 2 | 0 | Sem lançamento | 2 |
| [ETI-65](https://kaueamaral96.atlassian.net/browse/ETI-65) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Avisar os prestadores compatíveis quando um anúncio é publicado | 11 | 0 | Sem lançamento | 11 |
| [ETI-66](https://kaueamaral96.atlassian.net/browse/ETI-66) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Rotina de expiração de anúncios sem candidatos | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato | 8 | 0 | Sem lançamento | 8 |
| [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-69](https://kaueamaral96.atlassian.net/browse/ETI-69) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Escolher o prestador: transação atômica, cota e liberação do contato | 16 | 0 | Sem lançamento | 16 |
| [ETI-70](https://kaueamaral96.atlassian.net/browse/ETI-70) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Confirmar escolha e "Não foi possível escolher" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-71](https://kaueamaral96.atlassian.net/browse/ETI-71) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Consultar histórico de anúncios e serviços com filtros | 8 | 0 | Sem lançamento | 8 |
| [ETI-72](https://kaueamaral96.atlassian.net/browse/ETI-72) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Tela "Histórico" do Empregador | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) | FRONT-END | Sprint 6 | À TESTAR | [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio" | 13,5 | 1,17 | Em andamento | 12,33 |
| [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Candidatar-se a um anúncio | 8 | 0 | Sem lançamento | 8 |
| [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?" | 2 | 0 | Sem lançamento | 2 |
| [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-78](https://kaueamaral96.atlassian.net/browse/ETI-78) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Aplicações" (pendentes, combinadas e histórico), com desistir | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-79](https://kaueamaral96.atlassian.net/browse/ETI-79) | BACK-END | Sprint 6 | À FAZER | [perfil] [BACK-END] Consultar a cota do mês e zerar na virada do mês | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-80](https://kaueamaral96.atlassian.net/browse/ETI-80) | FRONT-END | Sprint 6 | À FAZER | [perfil] [FRONT-END] Faixa de cota no mural e tela "Cota do mês" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-81](https://kaueamaral96.atlassian.net/browse/ETI-81) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Assinar o GOLD pelo gateway de pagamento | 18,5 | 0 | Sem lançamento | 18,5 |
| [ETI-82](https://kaueamaral96.atlassian.net/browse/ETI-82) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura" (assinar GOLD) | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-83](https://kaueamaral96.atlassian.net/browse/ETI-83) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Gerenciar a assinatura GOLD: consultar, trocar cartão e cancelar renovação | 11 | 0 | Sem lançamento | 11 |
| [ETI-84](https://kaueamaral96.atlassian.net/browse/ETI-84) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura GOLD" (gerenciar) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-85](https://kaueamaral96.atlassian.net/browse/ETI-85) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Renovação mensal do GOLD: cobrança, falha, novas tentativas e volta ao FREE | 16 | 0 | Sem lançamento | 16 |
| [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-87](https://kaueamaral96.atlassian.net/browse/ETI-87) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Telas "Serviço combinado" (Empregador) e "Seu serviço" (Prestador) | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Iniciar o serviço | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-89](https://kaueamaral96.atlassian.net/browse/ETI-89) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Botão "Iniciar serviço" e tela "Serviço em andamento" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-90](https://kaueamaral96.atlassian.net/browse/ETI-90) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Fazer o check-out com foto | 6,5 | 0 | Sem lançamento | 6,5 |
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
| [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) | BACK-END | Sprint 6 | EM PROGRESSO | [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida | 23 | 0 | Sem lançamento | 23 |
| [ETI-102](https://kaueamaral96.atlassian.net/browse/ETI-102) | FRONT-END | Sprint 6 | À FAZER | [chat] [FRONT-END] Telas "Chat" e "Chat somente leitura" | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-103](https://kaueamaral96.atlassian.net/browse/ETI-103) | BACK-END | Sprint 7 | À FAZER | [chat] [BACK-END] Listar minhas conversas por papel | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-104](https://kaueamaral96.atlassian.net/browse/ETI-104) | FRONT-END | Sprint 7 | À FAZER | [chat] [FRONT-END] Tela "Conversas" (Empregador e Prestador) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-105](https://kaueamaral96.atlassian.net/browse/ETI-105) | BACK-END | Sprint 7 | À FAZER | [perfil] [BACK-END] Consultar o perfil público e a reputação | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-106](https://kaueamaral96.atlassian.net/browse/ETI-106) | FRONT-END | Sprint 7 | À FAZER | [perfil] [FRONT-END] Telas "Perfil público" (candidato e consulta) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) | BACK-END | Sprint 6 | À FAZER | [moderacao] [BACK-END] Avaliar a outra parte ou pular | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-108](https://kaueamaral96.atlassian.net/browse/ETI-108) | FRONT-END | Sprint 6 | EM PROGRESSO | [moderacao] [FRONT-END] Tela "Avaliação" | 3,5 | 1,98 | Em andamento | 1,52 |
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
| **Total** | | | | **110 cards** | **1.001** | **446,87** | | **566,77** |
