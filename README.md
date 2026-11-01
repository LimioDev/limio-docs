# LIMIO — Entrega do bimestre

App que conecta quem precisa de um serviço pontual (**Empregador**) a prestadores próximos (**Prestador**). O Empregador publica a demanda, os prestadores compatíveis se candidatam, os dois conversam no chat e o Empregador escolhe um. Só o escolhido recebe telefone e endereço. O pagamento do serviço é feito fora da plataforma; o único produto pago é a assinatura **GOLD**, que tira o limite de 4 escolhas por mês do Prestador.

Projeto da Escola de TI · Situação em **01/11/2026** · Sprint 6 em andamento

## Repositórios e ambientes

| O quê | Onde |
| --- | --- |
| API (back-end) | [github.com/LimioDev/limio-api](https://github.com/LimioDev/limio-api) — Java 21 e Spring Boot |
| App (front-end mobile) | [github.com/LimioDev/limio-app](https://github.com/LimioDev/limio-app) — Expo e React Native |
| API em desenvolvimento | [api-dev.limio.dev.br](https://api-dev.limio.dev.br/actuator/health) |
| API em produção | [api.limio.dev.br](https://api.limio.dev.br/actuator/health) |
| Issues (Jira) | [Board do projeto ETI](https://kaueamaral96.atlassian.net/jira/software/projects/ETI/boards/2) |
| Documentação viva (Confluence) | [LIMIO — Visão Geral](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/overview) |
| Protótipo (Figma) | [LIMIO — Protótipo Real](https://www.figma.com/design/mksrtupXi3Xs9uNeT0zKCw/LIMIO---PROTOTIPO-REAL?node-id=0-1) |

O trabalho do dia a dia fica nos dois repositórios de código. Os branches de desenvolvimento são `develop` (publica em desenvolvimento) e `main` (publica em produção).

## O que tem nesta entrega

| Item pedido | Onde está | Resumo |
| --- | --- | --- |
| Estimativa de horas do produto | [`estimativa/`](estimativa/) | **1.020,5 h** estimadas para os 115 cards do MVP; **405,74 h** trabalhadas até 01/11, medidas pelo Clockify. Em [CSV](estimativa/estimativa-horas.csv) e em [Markdown](estimativa/estimativa-horas.md). |
| Artefatos | [`artefatos/`](artefatos/) | Requisitos (v1.3), casos de uso, diagrama de classes, DER, 13 diagramas de atividade e backlog de user stories. |
| Design | [`design/`](design/) | Fundamentos visuais, mapa das telas e as 90 telas do protótipo (exportação de 27/10), separadas por módulo. |
| System design | [`system-design/`](system-design/system-design.md) | Arquitetura, módulos, fluxos, dados, segurança, infraestrutura e as 3 ADRs. |
| Registro.br | [`registros/`](registros/) | Domínio `limio.dev.br`, usado pela API. |
| Issues e equipe | [`equipe.md`](equipe.md) | Papéis, como ligar card → branch → pull request, horas e entregas de cada integrante, cerimônias. |

## Estrutura

```
.
├── README.md                     este índice
├── equipe.md                     papéis, horas e entregas por pessoa
├── estimativa/
│   ├── estimativa-horas.csv      115 cards: estimativa, trabalhado, faixa ±30% e saldo
│   ├── estimativa-horas.md       método, resumos e tabela completa
│   └── horas-por-pessoa.csv      horas do Clockify por pessoa e por card
├── artefatos/
│   ├── requisitos/               especificação de requisitos e regras de negócio v1.3
│   ├── casos-de-uso/             diagrama e especificação dos casos de uso
│   ├── classes/                  diagrama de classes
│   ├── der/                      diagrama entidade-relacionamento
│   ├── atividade/                13 fluxos do app
│   └── user-stories/             backlog de user stories
├── design/
│   ├── fundamentos.png           paleta, tipografia, componentes e ícones
│   ├── mapa-de-telas.png         fluxo entre as telas e requisitos de cada uma
│   ├── modulos/                  visão geral das telas de cada módulo
│   └── telas/                    90 telas, por módulo
├── system-design/
│   ├── system-design.md          documento principal, com diagramas
│   └── adr/                      decisões de arquitetura 0001 a 0003
└── registros/
    └── registro-br/              comprovantes do domínio
```

## Andamento

| Sprint | Período | Entregas | Status |
| --- | --- | --- | --- |
| Inicial | 05/08 – 19/08 | Requisitos, regras de negócio e casos de uso | Concluída |
| 2 | 20/08 – 31/08 | DER, Termos de Uso e Política de Privacidade | Concluída |
| 3 | 01/09 – 14/09 | Repositórios, diagrama de casos de uso, agente de validação de código | Concluída |
| 4 | 15/09 – 11/10 | Arquitetura (ADR-0001), Railway, protótipo, diagramas de classes e de atividade | Concluída |
| 5 | 12/10 – 25/10 | Login e sessão, cadastro no app, senhas, preferências, perfis de Empregador e Prestador, foto | Concluída |
| 6 | 27/10 – 08/11 | Ciclo principal: anúncio, mural, candidatura, chat, escolha, execução, validação e avaliação | Em andamento |
| 7 | 09/11 – 21/11 | Cancelamentos, reagendamento, rotinas automáticas, notificações, GOLD e moderação | Planejada |

## Equipe

| Integrante | Papel |
| --- | --- |
| Kauê | Product Owner e Frontend |
| Augusto | Backend e Tech Lead |
| Andrey | Backend |
| Gabriel | Backend |
| Victor | Frontend |

Detalhes em [`equipe.md`](equipe.md).
