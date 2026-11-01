# Diagramas de atividade

Um diagrama por fluxo do app, com raias (quem faz) e decisões (o que muda o caminho).

- **Página no Confluence:** [Diagramas de Atividade](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/28442625), com a descrição completa de cada fluxo
- **Card original:** [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) · Criação de Diagrama de Atividade (Astah, setembro)
- **Versão atual:** 27/10/2026, redesenhada a partir do Astah e alinhada aos cards das Sprints 5 a 7 e ao código
- **Arquivos originais do Astah:** [`astah/`](astah/)

## Índice

| Diagrama | Fluxo | Cards | Situação no código |
| --- | --- | --- | --- |
| [AD-01](AD-01.png) | Cadastro | ETI-30, ETI-40, ETI-47 | Parcial |
| [AD-02](AD-02.png) | Login | ETI-32, ETI-38 | No código |
| [AD-03](AD-03.png) | Criação e publicação do anúncio | ETI-59, ETI-60, ETI-65 | Em desenvolvimento |
| [AD-04](AD-04.png) | Candidatura do Prestador | ETI-73 a ETI-76, ETI-101 | Não iniciado |
| [AD-05](AD-05.png) | Escolha do Prestador | ETI-67 a ETI-70 | Não iniciado |
| [AD-06](AD-06.png) | Execução e conclusão do serviço | ETI-86 a ETI-93, ETI-98 | Não iniciado |
| [AD-07a](AD-07a.png) | Adesão à assinatura GOLD | ETI-81, ETI-82 | Depende da escolha do gateway |
| [AD-07b](AD-07b.png) | Renovação da assinatura GOLD | ETI-85 | Depende da escolha do gateway |
| [AD-08](AD-08.png) | Avaliação entre Prestador e Empregador | ETI-107, ETI-108 | Em desenvolvimento |
| [AD-09](AD-09.png) | Denúncia e moderação | ETI-114 a ETI-116, ETI-118 | Depende do acesso do admin |
| [AD-10](AD-10.png) | Reagendamento consensual | ETI-99, ETI-100 | Não iniciado |
| [AD-11](AD-11.png) | Cancelamento pelo Empregador | ETI-94, ETI-95 | Não iniciado |
| [AD-12](AD-12.png) | Cancelamento pelo Prestador | ETI-96, ETI-97 | Não iniciado |
| [AD-13](AD-13.png) | Encerramento ou suspensão em cascata | ETI-36, ETI-42, ETI-46, ETI-116 | Parcial |

## Status usados nos diagramas

São os nomes que estão no código.

| Onde | Status |
| --- | --- |
| Anúncio (`StatusAnuncio`) | `PUBLICADO`, `EM_ANDAMENTO`, `AGUARDANDO_VALIDACAO`, `CONCLUIDO`, `ENCERRADO` |
| Candidatura (`StatusAplicacao`) | `ENVIADA`, `ESCOLHIDA`, `RECUSADA`, `AGUARDANDO_VALIDACAO`, `CONCLUIDA`, `ENCERRADA` |
| Conta (`StatusConta`) | `PENDENTE_VERIFICACAO`, `ATIVA`, `BLOQUEADA` |
| Reagendamento (`StatusReagendamento`) | `PENDENTE`, `ACEITO`, `RECUSADO`, `CANCELADO` |
| Papel (`PapelUsuario`) | `EMPREGADOR`, `PRESTADOR`, `ADMIN` |
