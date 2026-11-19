# Diagramas de atividade

Um diagrama por fluxo do app, com raias (quem faz) e decisões (o que muda o caminho).

- **Página no Confluence:** [Diagramas de Atividade](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/28442625), com a descrição completa de cada fluxo
- **Card original:** [ETI-18](https://kaueamaral96.atlassian.net/browse/ETI-18) · Criação de Diagrama de Atividade (Astah, setembro)
- **Versão atual:** 27/10/2026, redesenhada a partir do Astah e alinhada aos cards das Sprints 5 a 7 e ao código
- **Situação no código:** atualizada pelos status do Jira em 19/11/2026
- **Requisitos v1.4 (11/11/2026):** a confirmação de telefone por SMS saiu do cadastro (ETI-134 e ETI-135). O AD-01 ainda mostra esse passo; o fluxo vigente confirma só o e-mail

## Índice

| Diagrama | Fluxo | Cards | Situação no código |
| --- | --- | --- | --- |
| [AD-01](AD-01.png) | Cadastro | ETI-30, ETI-40, ETI-47 | No código (o diagrama ainda mostra a confirmação por SMS, removida na v1.4) |
| [AD-02](AD-02.png) | Login | ETI-32, ETI-38 | No código |
| [AD-03](AD-03.png) | Criação e publicação do anúncio | ETI-59, ETI-60, ETI-65 | Em desenvolvimento (falta o aviso aos prestadores, ETI-65) |
| [AD-04](AD-04.png) | Candidatura do Prestador | ETI-73 a ETI-76, ETI-101 | No código |
| [AD-05](AD-05.png) | Escolha do Prestador | ETI-67 a ETI-70 | No código |
| [AD-06](AD-06.png) | Execução e conclusão do serviço | ETI-86 a ETI-93, ETI-98 | Em desenvolvimento (falta a conclusão automática por silêncio, ETI-98) |
| [AD-07a](AD-07a.png) | Adesão à assinatura GOLD | ETI-81, ETI-82 | Em desenvolvimento |
| [AD-07b](AD-07b.png) | Renovação da assinatura GOLD | ETI-85 | Em desenvolvimento |
| [AD-08](AD-08.png) | Avaliação entre Prestador e Empregador | ETI-107, ETI-108 | No código |
| [AD-09](AD-09.png) | Denúncia e moderação | ETI-114 a ETI-116, ETI-118 | Em desenvolvimento |
| [AD-10](AD-10.png) | Reagendamento consensual | ETI-99, ETI-100 | Em desenvolvimento |
| [AD-11](AD-11.png) | Cancelamento pelo Empregador | ETI-94, ETI-95 | Em desenvolvimento |
| [AD-12](AD-12.png) | Cancelamento pelo Prestador | ETI-96, ETI-97 | Em desenvolvimento |
| [AD-13](AD-13.png) | Encerramento ou suspensão em cascata | ETI-36, ETI-42, ETI-46, ETI-116 | Em desenvolvimento (falta a suspensão pelo admin, ETI-116) |

## Status usados nos diagramas

São os nomes que estão no código.

| Onde | Status |
| --- | --- |
| Anúncio (`StatusAnuncio`) | `PUBLICADO`, `EM_ANDAMENTO`, `AGUARDANDO_VALIDACAO`, `CONCLUIDO`, `ENCERRADO` |
| Candidatura (`StatusAplicacao`) | `ENVIADA`, `ESCOLHIDA`, `RECUSADA`, `AGUARDANDO_VALIDACAO`, `CONCLUIDA`, `ENCERRADA` |
| Conta (`StatusConta`) | `PENDENTE_VERIFICACAO`, `ATIVA`, `BLOQUEADA` |
| Reagendamento (`StatusReagendamento`) | `PENDENTE`, `ACEITO`, `RECUSADO`, `CANCELADO` |
| Papel (`PapelUsuario`) | `EMPREGADOR`, `PRESTADOR`, `ADMIN` |
