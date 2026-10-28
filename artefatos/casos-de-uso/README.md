# Casos de uso

- **Diagrama:** feito no draw.io em 9 páginas, uma por pacote (card [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17)). O arquivo editável é [`diagramas/limio-casos-de-uso.drawio`](diagramas/limio-casos-de-uso.drawio). As imagens ficam em [`diagramas/`](diagramas/):

  | Página | Imagem |
  | --- | --- |
  | 0. Visão Geral | [`00-visao-geral.png`](diagramas/00-visao-geral.png) |
  | 1. Identidade e Acesso | [`01-identidade-e-acesso.png`](diagramas/01-identidade-e-acesso.png) |
  | 2. Perfil e Preferências | [`02-perfil-e-preferencias.png`](diagramas/02-perfil-e-preferencias.png) |
  | 3. Anúncios de Serviço | [`03-anuncios-de-servico.png`](diagramas/03-anuncios-de-servico.png) |
  | 4. Mural e Matching | [`04-mural-e-matching.png`](diagramas/04-mural-e-matching.png) |
  | 5. Assinatura GOLD | [`05-assinatura-gold.png`](diagramas/05-assinatura-gold.png) |
  | 6. Execução do Serviço | [`06-execucao-do-servico.png`](diagramas/06-execucao-do-servico.png) |
  | 7. Avaliação e Reputação | [`07-avaliacao-e-reputacao.png`](diagramas/07-avaliacao-e-reputacao.png) |
  | 8. Moderação e Admin | [`08-moderacao-e-admin.png`](diagramas/08-moderacao-e-admin.png) |

  Legenda das elipses: amarelo é caso de uso iniciado por um ator humano; verde é executado automaticamente pelo Sistema; cinza tracejado é caso de uso de outro pacote, mostrado só para indicar o relacionamento.
- **Especificação:** [`especificacao-casos-de-uso.pdf`](especificacao-casos-de-uso.pdf), com finalidade, atores, pré-condições, fluxo principal e fluxos alternativos de cada caso de uso (cards [ETI-8](https://kaueamaral96.atlassian.net/browse/ETI-8) e [ETI-24](https://kaueamaral96.atlassian.net/browse/ETI-24))
- **Planilha de trabalho:** [Google Sheets](https://docs.google.com/spreadsheets/d/1kWNyoly5FkJhXvtluj5rvOOADmTCcx7xr4R0tdRfUdw/edit?usp=sharing), uma aba por caso de uso
- **Página no Confluence:** [Documentação de Casos de Uso](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/7667713)

## Arquivos CSV

Exportados da planilha em 27/10/2026. Separador `;` e acentos em UTF-8, para abrir direto no Excel ou no Google Sheets.

| Arquivo | O que tem |
| --- | --- |
| [`casos-de-uso.csv`](casos-de-uso.csv) | Uma linha por caso de uso (51): número, nome, atores, finalidade, pré-condições e o arquivo do caso. |
| [`casos-de-uso-passos.csv`](casos-de-uso-passos.csv) | Uma linha por passo (355): caso de uso, fluxo (principal ou alternativo), número do passo, quem executa (ator ou sistema) e descrição. |
| [`csv/`](csv/) | Um arquivo por caso de uso, igual à aba da planilha: nome, finalidade, atores, pré-condições e os fluxos em duas colunas (ações do ator e ações do sistema). |

## Atores

| Ator | Papel |
| --- | --- |
| Visitante | Ainda sem conta; pode se cadastrar. |
| Usuário | Pessoa com conta única (CPF + e-mail), que alterna entre os papéis abaixo. |
| Empregador | Publica anúncios, escolhe o prestador e valida o serviço. |
| Prestador (FREE ou GOLD) | Vê o mural, se candidata e executa o serviço. |
| Administrador | Analisa denúncias, aplica sanções e acompanha o dashboard. |
| Sistema | Rotinas automáticas: expiração, conclusão por silêncio, cobrança do GOLD. |

## Lista dos casos de uso

| UC | Caso de uso | Ator(es) | CSV |
| --- | --- | --- | --- |
| UC01 | Cadastrar conta universal | Visitante | [`uc01-cadastrar-conta-universal.csv`](csv/uc01-cadastrar-conta-universal.csv) |
| UC02 | Recusar cadastro duplicado | Visitante | [`uc02-recusar-cadastro-duplicado.csv`](csv/uc02-recusar-cadastro-duplicado.csv) |
| UC03 | Login com e-mail e senha | Usuário | [`uc03-login-com-e-mail-e-senha.csv`](csv/uc03-login-com-e-mail-e-senha.csv) |
| UC04 | Confirmar telefone por OTP | Usuário em cadastro (ou usuário com telefone ainda não verificado) | [`uc04-confirmar-telefone-por-otp.csv`](csv/uc04-confirmar-telefone-por-otp.csv) |
| UC05 | Confirmar e-mail | Usuário | [`uc05-confirmar-e-mail.csv`](csv/uc05-confirmar-e-mail.csv) |
| UC06 | Recuperar senha por e-mail | Usuário (não autenticado) | [`uc06-recuperar-senha-por-e-mail.csv`](csv/uc06-recuperar-senha-por-e-mail.csv) |
| UC07 | Alterar senha autenticado | Usuário autenticado | [`uc07-alterar-senha-autenticado.csv`](csv/uc07-alterar-senha-autenticado.csv) |
| UC08 | Logout do dispositivo | Usuário autenticado | [`uc08-logout-do-dispositivo.csv`](csv/uc08-logout-do-dispositivo.csv) |
| UC09 | Alternar papel Empregador/Prestador | Usuário autenticado | [`uc09-alternar-papel-empregador-prestador.csv`](csv/uc09-alternar-papel-empregador-prestador.csv) |
| UC10 | Encerrar conta | Usuário autenticado | [`uc10-encerrar-conta.csv`](csv/uc10-encerrar-conta.csv) |
| UC11 | Gerenciar perfil empregador | Empregador | [`uc11-gerenciar-perfil-empregador.csv`](csv/uc11-gerenciar-perfil-empregador.csv) |
| UC12 | Gerenciar perfil prestador | Prestador | [`uc12-gerenciar-perfil-prestador.csv`](csv/uc12-gerenciar-perfil-prestador.csv) |
| UC13 | Visualizar perfil público e reputação | Usuário autenticado | [`uc13-visualizar-perfil-publico-e-reputacao.csv`](csv/uc13-visualizar-perfil-publico-e-reputacao.csv) |
| UC14 | Enviar foto de perfil | Usuário autenticado | [`uc14-enviar-foto-de-perfil.csv`](csv/uc14-enviar-foto-de-perfil.csv) |
| UC15 | Configurar preferências de notificação | Usuário autenticado | [`uc15-configurar-preferencias-de-notificacao.csv`](csv/uc15-configurar-preferencias-de-notificacao.csv) |
| UC17 | Criar anúncio de serviço (sem valor) | Empregador | [`uc17-criar-anuncio-de-servico-sem-valor.csv`](csv/uc17-criar-anuncio-de-servico-sem-valor.csv) |
| UC18 | Anexar fotos ao anúncio | Empregador | [`uc18-anexar-fotos-ao-anuncio.csv`](csv/uc18-anexar-fotos-ao-anuncio.csv) |
| UC19 | Editar anúncio antes da escolha | Empregador (dono do anúncio) | [`uc19-editar-anuncio-antes-da-escolha.csv`](csv/uc19-editar-anuncio-antes-da-escolha.csv) |
| UC20 | Cancelar anúncio antes da escolha | Empregador (dono do anúncio) | [`uc20-cancelar-anuncio-antes-da-escolha.csv`](csv/uc20-cancelar-anuncio-antes-da-escolha.csv) |
| UC21 | Publicar no mural geográfico | Sistema; Empregador (disparo pela criação) | [`uc21-publicar-no-mural-geografico.csv`](csv/uc21-publicar-no-mural-geografico.csv) |
| UC22 | Expirar anúncio sem combinação | Sistema | [`uc22-expirar-anuncio-sem-combinacao.csv`](csv/uc22-expirar-anuncio-sem-combinacao.csv) |
| UC23 | Consultar histórico com filtros | Empregador ou Prestador | [`uc23-consultar-historico-com-filtros.csv`](csv/uc23-consultar-historico-com-filtros.csv) |
| UC24 | Visualizar mural com dados básicos | Prestador (FREE ou GOLD) | [`uc24-visualizar-mural-com-dados-basicos.csv`](csv/uc24-visualizar-mural-com-dados-basicos.csv) |
| UC25 | Filtrar mural por categoria, raio e Outros | Sistema (em nome do Prestador) | [`uc25-filtrar-mural-por-categoria-raio-e-outros.csv`](csv/uc25-filtrar-mural-por-categoria-raio-e-outros.csv) |
| UC26 | Aplicar para um serviço | Prestador | [`uc26-aplicar-para-um-servico.csv`](csv/uc26-aplicar-para-um-servico.csv) |
| UC27 | Desistir da aplicação | Prestador | [`uc27-desistir-da-aplicacao.csv`](csv/uc27-desistir-da-aplicacao.csv) |
| UC28 | Empregador listar candidatos | Empregador | [`uc28-empregador-listar-candidatos.csv`](csv/uc28-empregador-listar-candidatos.csv) |
| UC29 | Recusar um candidato | Empregador | [`uc29-recusar-um-candidato.csv`](csv/uc29-recusar-um-candidato.csv) |
| UC30 | Conversar no chat após aplicar | Empregador e Prestador candidato | [`uc30-conversar-no-chat-apos-aplicar.csv`](csv/uc30-conversar-no-chat-apos-aplicar.csv) |
| UC31 | Empregador escolhe um prestador | Empregador | [`uc31-empregador-escolhe-um-prestador.csv`](csv/uc31-empregador-escolhe-um-prestador.csv) |
| UC32 | Encerrar demais aplicações após a escolha. | Sistema | [`uc32-encerrar-demais-aplicacoes-apos-a-escolha.csv`](csv/uc32-encerrar-demais-aplicacoes-apos-a-escolha.csv) |
| UC33 | Consumir cota FREE na escolha | Sistema | [`uc33-consumir-cota-free-na-escolha.csv`](csv/uc33-consumir-cota-free-na-escolha.csv) |
| UC34 | Bloquear aplicação com cota esgotada | Prestador | [`uc34-bloquear-aplicacao-com-cota-esgotada.csv`](csv/uc34-bloquear-aplicacao-com-cota-esgotada.csv) |
| UC35 | Assinar plano GOLD | Prestador | [`uc35-assinar-plano-gold.csv`](csv/uc35-assinar-plano-gold.csv) |
| UC36 | Cadastrar ou atualizar método de pagamento | Prestador | [`uc36-cadastrar-ou-atualizar-metodo-de-pagamento.csv`](csv/uc36-cadastrar-ou-atualizar-metodo-de-pagamento.csv) |
| UC37 | Cancelar assinatura GOLD | Prestador | [`uc37-cancelar-assinatura-gold.csv`](csv/uc37-cancelar-assinatura-gold.csv) |
| UC38 | Falha de cobrança e retry | Sistema | [`uc38-falha-de-cobranca-e-retry.csv`](csv/uc38-falha-de-cobranca-e-retry.csv) |
| UC39 | Prestador iniciar serviço | Prestador | [`uc39-prestador-iniciar-servico.csv`](csv/uc39-prestador-iniciar-servico.csv) |
| UC40 | Prestador marcar conclusão com foto | Prestador | [`uc40-prestador-marcar-conclusao-com-foto.csv`](csv/uc40-prestador-marcar-conclusao-com-foto.csv) |
| UC41 | Solicitante validar o serviço (presencial ou pela foto) | Empregador / Solicitante | [`uc41-solicitante-validar-o-servico-presencial-ou-pela-foto.csv`](csv/uc41-solicitante-validar-o-servico-presencial-ou-pela-foto.csv) |
| UC42 | Empregador cancelar após combinação (≥ 24h) | Empregador | [`uc42-empregador-cancelar-apos-combinacao-24h.csv`](csv/uc42-empregador-cancelar-apos-combinacao-24h.csv) |
| UC43 | Prestador cancelar após ser escolhido | Prestador escolhido | [`uc43-prestador-cancelar-apos-ser-escolhido.csv`](csv/uc43-prestador-cancelar-apos-ser-escolhido.csv) |
| UC44 | Conclusão automática por silêncio | Sistema | [`uc44-conclusao-automatica-por-silencio.csv`](csv/uc44-conclusao-automatica-por-silencio.csv) |
| UC45 | Avaliar a outra parte | Empregador ou Prestador | [`uc45-avaliar-a-outra-parte.csv`](csv/uc45-avaliar-a-outra-parte.csv) |
| UC46 | Pular avaliação | Empregador ou Prestador | [`uc46-pular-avaliacao.csv`](csv/uc46-pular-avaliacao.csv) |
| UC47 | Exibir média somente com avaliações | Qualquer usuário autenticado | [`uc47-exibir-media-somente-com-avaliacoes.csv`](csv/uc47-exibir-media-somente-com-avaliacoes.csv) |
| UC48 | Registrar denúncia | Usuário autenticado (Prestador ou Solicitante, conforme o caso) | [`uc48-registrar-denuncia.csv`](csv/uc48-registrar-denuncia.csv) |
| UC49 | Admin moderar denúncia e suspender conta | Administrador | [`uc49-admin-moderar-denuncia-e-suspender-conta.csv`](csv/uc49-admin-moderar-denuncia-e-suspender-conta.csv) |
| UC50 | Dashboard administrativo | Administrador | [`uc50-dashboard-administrativo.csv`](csv/uc50-dashboard-administrativo.csv) |
| UC51 | Propor reagendamento do serviço | Empregador ou Prestador escolhido | [`uc51-propor-reagendamento-do-servico.csv`](csv/uc51-propor-reagendamento-do-servico.csv) |
| UC52 | Responder proposta de reagendamento | Contraparte (Empregador ou Prestador escolhido) | [`uc52-responder-proposta-de-reagendamento.csv`](csv/uc52-responder-proposta-de-reagendamento.csv) |



## Diferenças conhecidas em relação ao código

A especificação é de agosto. No código, alguns nomes mudaram:

- O status inicial do anúncio é `PUBLICADO` (no documento, "AguardandoCandidatos"), e "Combinado" não é um status: é o anúncio `PUBLICADO` com uma candidatura `ESCOLHIDA`.
- A candidatura pendente é `ENVIADA` (no documento, "Pendente").
- A conta é criada antes do SMS, e não depois (decisão do grupo no ETI-30).

Os diagramas de atividade de 27/10 ([`../atividade/`](../atividade/)) já estão com os nomes do código.
