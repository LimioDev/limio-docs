# Estimativa de horas do produto — LIMIO

> Horas trabalhadas medidas pelo **Clockify** de cada integrante (copiado em **01/11/2026**). Status, sprint e responsável de cada card vêm do Jira (projeto ETI). Mesmos dados de [`estimativa-horas.csv`](estimativa-horas.csv), que abre no Excel ou no Google Sheets.
> Planilha de trabalho anexada à página [Controle de Horas do Backlog](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/26476545) no Confluence.

## Resumo

| Indicador | Valor |
| --- | ---: |
| Total estimado do produto (MVP) | **1.001 h** |
| Horas trabalhadas (Clockify) | 405,74 h (40,5%) |
| Horas trabalhadas em cards do backlog | 403,69 h (mais 2,05 h sem card) |
| Saldo a fazer | 636,83 h |
| Cards | 110 |
| Cards dentro da faixa de ±30% | 32 |
| Cards acima de 130% | 7 (ETI-10, ETI-37, ETI-42, ETI-50, ETI-52, ETI-64, ETI-76) |
| Cards concluídos abaixo de 70% | 12 (ETI-4, ETI-23, ETI-27, ETI-40, ETI-44, ETI-51, ETI-53, ETI-59, ETI-60, ETI-74, ETI-79, ETI-101) |
| Cards em andamento, ainda abaixo de 70% | 9 |
| Cards sem horas (não iniciados) | 50 |

## Como a estimativa foi feita

1. **Escopo:** todos os cards do Jira do projeto, da documentação inicial (agosto) até a Sprint 7 (fim do MVP), incluindo reuniões, design, documentação, back-end e front-end.
2. **Cards que já tinham horas na época da estimativa:** a estimativa foi escolhida para que as horas fiquem entre 70% e 130% dela.
3. **Cards ainda não iniciados:** estimados pelo escopo da descrição do card (quantidade de telas, cenários de teste, rotinas automáticas, integrações externas e pendências).
4. **Referência do próprio time:** mediana de 7,2 h por card de back-end e 4,3 h por card de front-end, medida nos cards já concluídos.
5. **Fechamento:** as estimativas base foram multiplicadas por um fator único (1,12) para fechar o total combinado pelo time de 1.000 h, e arredondadas para 0,5 h. Depois entrou a subtarefa ETI-120 (1 h), o que levou o total a 1.001 h.

**Maiores incertezas:** chat em tempo real (ETI-101), assinatura GOLD com gateway de pagamento ainda não escolhido (ETI-81 e ETI-85) e envio de notificações em quatro canais (ETI-112).

**Leitura dos desvios:** a maior parte dos cards fora da faixa são cards concluídos com menos horas que o estimado. Isso indica estimativa alta para esses cards e será usado na reestimativa da Sprint 7.

### De onde vêm as horas

As horas foram medidas pelo Clockify, o cronômetro que cada integrante usa ao trabalhar em um card. Até 27/10 esta estimativa usava os lançamentos manuais do Jira, que tinham lançamentos repetidos e horas no card errado; por isso a fonte passou a ser o Clockify.

- **Andrey:** usou dois workspaces no Clockify ("kaueamaral96.atlassian.net" e "LIMIO"). As horas dele juntam os dois, contando uma vez só as entradas repetidas entre eles.
- **Augusto:** o Clockify enviado trazia só o total de cada dia. Em quatro dias com dois cards (02/09, 08/09, 09/10 e 21/10), o total do dia foi dividido igualmente entre os dois. Em 02/09 a segunda entrada não tinha card e ficou como "sem card" (2,05 h). Uma entrada de outro projeto foi excluída.

### Regra da faixa ±30%

| Faixa | Quando |
| --- | --- |
| OK | Trabalhado entre 70% e 130% da estimativa |
| Em andamento | Card ainda não concluído, abaixo de 70% |
| Fora da faixa | Trabalhado acima de 130%, ou card concluído abaixo de 70% |
| Sem lançamento | Card sem horas no Clockify |

## Horas por pessoa

Soma do Clockify de cada integrante. Detalhe card a card em [`horas-por-pessoa.csv`](horas-por-pessoa.csv).

| Pessoa | Cards com horas | Horas (h) | % do total |
| --- | ---: | ---: | ---: |
| Victor Hugo Rodrigues de Oliveira | 20 | 103,07 | 25,4% |
| Augusto Ogawa | 20 | 85,92 | 21,2% |
| Gabriel Sena | 13 | 72,76 | 17,9% |
| Andrey (andreyindras) | 12 | 72,56 | 17,9% |
| Kauê (kaueamaral96) | 24 | 71,43 | 17,6% |
| **Total** | | **405,74** | 100% |

## Por sprint

| Sprint | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| Sprint Inicial | 6 | 39,5 | 26,38 | 15,5 | 3,9% |
| Sprint 2 | 5 | 28 | 22,8 | 7,21 | 2,8% |
| Sprint 3 | 6 | 69,5 | 38,26 | 32,42 | 6,9% |
| Sprint 4 | 6 | 104,5 | 100,74 | 12,48 | 10,4% |
| Sprint 5 | 14 | 196,5 | 71,97 | 127,06 | 19,6% |
| Sprint 6 | 43 | 324,5 | 143,54 | 203,66 | 32,4% |
| Sprint 7 | 30 | 238,5 | 0 | 238,5 | 23,8% |

## Por status

| Status | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| CONCLUIDO | 51 | 548,5 | 331,78 | 251,82 | 54,8% |
| À TESTAR | 6 | 32 | 26,94 | 8,15 | 3,2% |
| PARA AJUSTE | 2 | 14,5 | 11,14 | 4,68 | 1,4% |
| AJUSTANDO | 5 | 62,5 | 28,64 | 33,86 | 6,2% |
| EM PROGRESSO | 5 | 30 | 5,18 | 24,82 | 3% |
| À FAZER | 41 | 313,5 | 0 | 313,5 | 31,3% |

## Por camada

| Camada | Cards | Estimado (h) | Trabalhado (h) | Saldo (h) | % do estimado |
| --- | ---: | ---: | ---: | ---: | ---: |
| AEP | 1 | 39 | 10,94 | 28,06 | 3,9% |
| BACK-END | 45 | 415 | 144,59 | 287,33 | 41,5% |
| DESIGN | 1 | 70,5 | 63,37 | 7,13 | 7% |
| DEV | 2 | 9 | 6,2 | 2,8 | 0,9% |
| DOCS | 10 | 77,9 | 77,33 | 6,13 | 7,8% |
| FRONT-END | 37 | 331,5 | 65,24 | 274,56 | 33,1% |
| GESTÃO | 1 | 1 | 1 | 0 | 0,1% |
| INFRA | 2 | 2,5 | 10,84 | 0,38 | 0,2% |
| REUNIÃO | 6 | 36,5 | 19,6 | 16,9 | 3,6% |
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
| [ETI-30](https://kaueamaral96.atlassian.net/browse/ETI-30) | BACK-END | Sprint 6 | AJUSTANDO | [auth] [BACK-END] Cadastrar conta e confirmar telefone (OTP) e e-mail | 7,5 | 6,87 | OK | 0,63 |
| [ETI-32](https://kaueamaral96.atlassian.net/browse/ETI-32) | BACK-END | Sprint 5 | CONCLUIDO | [auth] [BACK-END] Autenticar, renovar sessão, encerrar sessão e trocar papel ativo | 8,5 | 7,66 | OK | 0,84 |
| [ETI-33](https://kaueamaral96.atlassian.net/browse/ETI-33) | BACK-END | Sprint 6 | AJUSTANDO | [auth] [BACK-END] Recuperação de senha por link e alteração de senha autenticada | 11 | 1,58 | Em andamento | 9,42 |
| [ETI-34](https://kaueamaral96.atlassian.net/browse/ETI-34) | BACK-END | Sprint 5 | CONCLUIDO | [conta] [BACK-END] Consultar e atualizar preferências de notificação | 9 | 8,95 | OK | 0,05 |
| [ETI-35](https://kaueamaral96.atlassian.net/browse/ETI-35) | DOCS | Sprint 4 | CONCLUIDO | [DOCS] Criacão de ADR's | 3,5 | 3,31 | OK | 0,19 |
| [ETI-36](https://kaueamaral96.atlassian.net/browse/ETI-36) | BACK-END | Sprint 6 | AJUSTANDO | [conta] [BACK-END] Encerrar conta: anonimização, bloqueio de acesso, bloqueio de CPF e auditoria | 17 | 5,87 | Em andamento | 11,13 |
| [ETI-37](https://kaueamaral96.atlassian.net/browse/ETI-37) | INFRA | Sprint 4 | CONCLUIDO | [INFRA] Subir limio-api + Postgres na Railway (ambientes dev e prod) | 1 | 9,73 | Fora da faixa | 0 |
| [ETI-38](https://kaueamaral96.atlassian.net/browse/ETI-38) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Tela de login, sessão do app, logout e seletor de papel | 4 | 3,58 | OK | 0,42 |
| [ETI-39](https://kaueamaral96.atlassian.net/browse/ETI-39) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Telas de solicitar recuperação e de alterar senha | 8 | 7,46 | OK | 0,54 |
| [ETI-40](https://kaueamaral96.atlassian.net/browse/ETI-40) | FRONT-END | Sprint 5 | CONCLUIDO | [auth] [FRONT-END] Fluxo de cadastro em 3 passos | 126,5 | 5,43 | Fora da faixa | 121,07 |
| [ETI-41](https://kaueamaral96.atlassian.net/browse/ETI-41) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Toggles de notificação em Ajustes | 2 | 2,03 | OK | 0 |
| [ETI-42](https://kaueamaral96.atlassian.net/browse/ETI-42) | FRONT-END | Sprint 5 | CONCLUIDO | [conta] [FRONT-END] Tela "Encerrar conta" | 4,5 | 7 | Fora da faixa | 0 |
| [ETI-44](https://kaueamaral96.atlassian.net/browse/ETI-44) | SUBTAREFA | Sprint 6 | CONCLUIDO | remodelar estrutura de diretorio, ADR e INCONSISTENCIA DE CPNJ | 9 | 4,56 | Fora da faixa | 4,44 |
| [ETI-45](https://kaueamaral96.atlassian.net/browse/ETI-45) | INFRA | Sprint 5 | CONCLUIDO | [INFRA] Criar conta no Resend e configurar o domínio de envio de e-mails | 1,5 | 1,12 | OK | 0,38 |
| [ETI-46](https://kaueamaral96.atlassian.net/browse/ETI-46) | BACK-END | Sprint 6 | AJUSTANDO | [anuncio] [BACK-END] Encerrar anúncios, candidaturas e combinados de conta encerrada | 13,5 | 6,09 | Em andamento | 7,41 |
| [ETI-47](https://kaueamaral96.atlassian.net/browse/ETI-47) | BACK-END | Sprint 6 | PARA AJUSTE | [auth] [BACK-END] Páginas web "Confirmar e-mail" e "Nova senha" | 6,5 | 7,82 | OK | 0 |
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
| [ETI-61](https://kaueamaral96.atlassian.net/browse/ETI-61) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Editar anúncio antes da escolha | 6,5 | 4,19 | Em andamento | 2,31 |
| [ETI-62](https://kaueamaral96.atlassian.net/browse/ETI-62) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Editar anúncio" | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-63](https://kaueamaral96.atlassian.net/browse/ETI-63) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Cancelar anúncio antes da escolha | 5,5 | 4 | OK | 1,5 |
| [ETI-64](https://kaueamaral96.atlassian.net/browse/ETI-64) | FRONT-END | Sprint 6 | À TESTAR | [anuncio] [FRONT-END] Confirmação "Cancelar este anúncio?" | 2 | 5,09 | Fora da faixa | 0 |
| [ETI-65](https://kaueamaral96.atlassian.net/browse/ETI-65) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Avisar os prestadores compatíveis quando um anúncio é publicado | 11 | 0 | Sem lançamento | 11 |
| [ETI-66](https://kaueamaral96.atlassian.net/browse/ETI-66) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Rotina de expiração de anúncios sem candidatos | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-67](https://kaueamaral96.atlassian.net/browse/ETI-67) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Listar os candidatos do anúncio e recusar candidato | 8 | 4,22 | Em andamento | 3,78 |
| [ETI-68](https://kaueamaral96.atlassian.net/browse/ETI-68) | FRONT-END | Sprint 6 | À TESTAR | [anuncio] [FRONT-END] Telas "Candidatos" e "Candidatos vazio", com recusar | 5,5 | 4,96 | OK | 0,54 |
| [ETI-69](https://kaueamaral96.atlassian.net/browse/ETI-69) | BACK-END | Sprint 6 | À FAZER | [anuncio] [BACK-END] Escolher o prestador: transação atômica, cota e liberação do contato | 16 | 0 | Sem lançamento | 16 |
| [ETI-70](https://kaueamaral96.atlassian.net/browse/ETI-70) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Confirmar escolha e "Não foi possível escolher" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-71](https://kaueamaral96.atlassian.net/browse/ETI-71) | BACK-END | Sprint 7 | À FAZER | [anuncio] [BACK-END] Consultar histórico de anúncios e serviços com filtros | 8 | 0 | Sem lançamento | 8 |
| [ETI-72](https://kaueamaral96.atlassian.net/browse/ETI-72) | FRONT-END | Sprint 7 | À FAZER | [anuncio] [FRONT-END] Tela "Histórico" do Empregador | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-73](https://kaueamaral96.atlassian.net/browse/ETI-73) | BACK-END | Sprint 6 | AJUSTANDO | [anuncio] [BACK-END] Listar o mural e o detalhe do anúncio para o Prestador | 13,5 | 8,22 | Em andamento | 5,28 |
| [ETI-74](https://kaueamaral96.atlassian.net/browse/ETI-74) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Telas "Mural", "Filtros", "Mural vazio" e "Detalhe do anúncio" | 13,5 | 1,58 | Fora da faixa | 11,92 |
| [ETI-75](https://kaueamaral96.atlassian.net/browse/ETI-75) | BACK-END | Sprint 6 | PARA AJUSTE | [anuncio] [BACK-END] Candidatar-se a um anúncio | 8 | 3,32 | Em andamento | 4,68 |
| [ETI-76](https://kaueamaral96.atlassian.net/browse/ETI-76) | FRONT-END | Sprint 6 | CONCLUIDO | [anuncio] [FRONT-END] Confirmação "Candidatar-se a este serviço?" | 2 | 4,49 | Fora da faixa | 0 |
| [ETI-77](https://kaueamaral96.atlassian.net/browse/ETI-77) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Listar minhas candidaturas e desistir de candidatura pendente | 6,5 | 3,17 | Em andamento | 3,33 |
| [ETI-78](https://kaueamaral96.atlassian.net/browse/ETI-78) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Tela "Aplicações" (pendentes, combinadas e histórico), com desistir | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-79](https://kaueamaral96.atlassian.net/browse/ETI-79) | BACK-END | Sprint 6 | CONCLUIDO | [perfil] [BACK-END] Consultar a cota do mês e zerar na virada do mês | 6,5 | 3,97 | Fora da faixa | 2,53 |
| [ETI-80](https://kaueamaral96.atlassian.net/browse/ETI-80) | FRONT-END | Sprint 6 | À FAZER | [perfil] [FRONT-END] Faixa de cota no mural e tela "Cota do mês" | 3,5 | 0 | Sem lançamento | 3,5 |
| [ETI-81](https://kaueamaral96.atlassian.net/browse/ETI-81) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Assinar o GOLD pelo gateway de pagamento | 18,5 | 0 | Sem lançamento | 18,5 |
| [ETI-82](https://kaueamaral96.atlassian.net/browse/ETI-82) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura" (assinar GOLD) | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-83](https://kaueamaral96.atlassian.net/browse/ETI-83) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Gerenciar a assinatura GOLD: consultar, trocar cartão e cancelar renovação | 11 | 0 | Sem lançamento | 11 |
| [ETI-84](https://kaueamaral96.atlassian.net/browse/ETI-84) | FRONT-END | Sprint 7 | À FAZER | [financeiro] [FRONT-END] Tela "Assinatura GOLD" (gerenciar) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-85](https://kaueamaral96.atlassian.net/browse/ETI-85) | BACK-END | Sprint 7 | À FAZER | [financeiro] [BACK-END] Renovação mensal do GOLD: cobrança, falha, novas tentativas e volta ao FREE | 16 | 0 | Sem lançamento | 16 |
| [ETI-86](https://kaueamaral96.atlassian.net/browse/ETI-86) | BACK-END | Sprint 6 | EM PROGRESSO | [anuncio] [BACK-END] Consultar o serviço combinado com os contatos liberados | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-87](https://kaueamaral96.atlassian.net/browse/ETI-87) | FRONT-END | Sprint 6 | À FAZER | [anuncio] [FRONT-END] Telas "Serviço combinado" (Empregador) e "Seu serviço" (Prestador) | 6,5 | 0 | Sem lançamento | 6,5 |
| [ETI-88](https://kaueamaral96.atlassian.net/browse/ETI-88) | BACK-END | Sprint 6 | À TESTAR | [anuncio] [BACK-END] Iniciar o serviço | 4,5 | 4,49 | OK | 0,01 |
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
| [ETI-101](https://kaueamaral96.atlassian.net/browse/ETI-101) | BACK-END | Sprint 6 | CONCLUIDO | [chat] [BACK-END] Chat 1:1 em tempo real: abrir na candidatura, enviar, entregar e marcar como lida | 23 | 10,1 | Fora da faixa | 12,9 |
| [ETI-102](https://kaueamaral96.atlassian.net/browse/ETI-102) | FRONT-END | Sprint 6 | À FAZER | [chat] [FRONT-END] Telas "Chat" e "Chat somente leitura" | 13,5 | 0 | Sem lançamento | 13,5 |
| [ETI-103](https://kaueamaral96.atlassian.net/browse/ETI-103) | BACK-END | Sprint 7 | À FAZER | [chat] [BACK-END] Listar minhas conversas por papel | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-104](https://kaueamaral96.atlassian.net/browse/ETI-104) | FRONT-END | Sprint 7 | À FAZER | [chat] [FRONT-END] Tela "Conversas" (Empregador e Prestador) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-105](https://kaueamaral96.atlassian.net/browse/ETI-105) | BACK-END | Sprint 7 | À FAZER | [perfil] [BACK-END] Consultar o perfil público e a reputação | 5,5 | 0 | Sem lançamento | 5,5 |
| [ETI-106](https://kaueamaral96.atlassian.net/browse/ETI-106) | FRONT-END | Sprint 7 | À FAZER | [perfil] [FRONT-END] Telas "Perfil público" (candidato e consulta) | 4,5 | 0 | Sem lançamento | 4,5 |
| [ETI-107](https://kaueamaral96.atlassian.net/browse/ETI-107) | BACK-END | Sprint 6 | EM PROGRESSO | [moderacao] [BACK-END] Avaliar a outra parte ou pular | 6,5 | 0 | Sem lançamento | 6,5 |
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
| **Total** | | | | **110 cards** | **1.001** | **403,69** | | **636,83** |
