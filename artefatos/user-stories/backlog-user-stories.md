> Cópia do documento anexado à página [Backlog de User Stories](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/26443777) do Confluence, versão de 06/10/2026. Depois dessa data as histórias viraram os cards ETI-46 a ETI-118 do Jira, e as tags dos cards foram alinhadas aos módulos do código (26/10): `contratante` virou `[empregador]`, `servico` virou `[anuncio]`, o GOLD virou `[financeiro]`, as notificações viraram `[notificacao]`, o admin virou `[administracao]`, a cota virou `[perfil]` e a avaliação virou `[moderacao]`.

# LIMIO — Backlog completo de User Stories

> **Base:** planilha de casos de uso (UCs), telas do Figma, DER e diagrama de classes de 06/10 e decisões do PO registradas em `LIMIO-base-de-contexto.md`.
> **Data:** 06/10/2026.
> **Como ler:**
> - Cada história é ponta a ponta (Regra de Ouro). UCs que só funcionam juntos foram agrupados em uma história.
> - **Situação** indica se a história já tem card no Jira ou se é nova.
> - Os nomes de estado (`AguardandoCandidatos`, `Combinado` etc.) são os dos UCs. Os valores oficiais dos enums `StatusAnuncio` e `StatusAplicacao` ainda serão definidos pelo time.
> - Rotas e nomes de `CodigoErro` não aparecem aqui: são definidos no card BACK-END de cada história.
> - Histórias marcadas como **Candidata** existem no modelo de dados, mas não têm caso de uso nem tela. O PO decide se entram no MVP.

---

## Resumo

| Módulo | Histórias | Já no Jira | Novas | Candidatas (sem UC) |
|---|---|---|---|---|
| `auth` | 9 | 9 | 0 | 0 |
| `conta` | 5 | 2 | 1 | 2 |
| `contratante` | 3 | 0 | 3 | 0 |
| `prestador` | 11 | 0 | 11 | 0 |
| `anuncio` | 10 | 1 | 9 | 0 |
| `servico` | 9 | 0 | 9 | 0 |
| `chat` | 3 | 0 | 2 | 1 |
| `perfil` | 4 | 0 | 3 | 1 |
| Módulo a definir | 8 | 0 | 5 | 3 |
| **Total** | **62** | **12** | **43** | **7** |

---

## Módulo `auth`

Todas as histórias deste módulo já têm card no Jira. O texto completo está em `cards-jira-acesso-identidade.md` e no site de copia e cola.

### US01 · [auth] Cadastrar conta universal
- **User Story:** Como um visitante, eu quero criar uma conta única com CPF e e-mail, para que eu use a plataforma como Empregador ou Prestador sem precisar de duas contas.
- **Critérios principais:**
  - Formulário: nome, e-mail, celular, senha, CPF, data de nascimento, cidade/UF e opt-in de WhatsApp (desmarcado, separado dos Termos).
  - Recusa menores de 18 anos e CPF com formato ou dígitos inválidos.
  - Senha de 8 a 72 caracteres, com ao menos 1 letra e 1 número.
  - Conta criada em `PENDENTE_VERIFICACAO`, com papel ativo `CONTRATANTE`.
  - Após o envio, o SMS com o código é disparado e o app vai para a tela 03.
- **Telas:** 01 Boas-vindas · 02 Criar conta
- **UC:** Cadastrar conta universal
- **Situação:** Jira ETI-30 + card FRONT-END par

### US02 · [auth] Recusar cadastro duplicado
- **User Story:** Como plataforma, eu quero recusar cadastros com CPF ou e-mail já usados, para que ninguém crie contas novas para burlar a cota.
- **Critérios principais:**
  - CPF ou e-mail repetido, ou CPF de conta encerrada há menos de 12 meses (`CpfBloqueado`), recebem a mesma mensagem genérica.
  - A mensagem não revela qual campo colidiu.
  - CPF com bloqueio vencido segue o cadastro normal.
- **Telas:** 02 Criar conta
- **UC:** Recusar cadastro duplicado
- **Situação:** Jira ETI-30

### US03 · [auth] Confirmar telefone por código SMS
- **User Story:** Como um usuário em cadastro, eu quero confirmar meu celular com um código, para que minha conta seja considerada segura.
- **Critérios principais:**
  - Código de 6 dígitos, válido por 5 min, com 5 tentativas.
  - Reenvio a cada 60 s, no máximo 5 por hora por telefone.
  - Inclui a opção "Trocar número".
  - Sucesso preenche `telefoneConfirmadoEm` e permite login.
- **Telas:** 03 Confirmar telefone
- **UC:** Confirmar telefone por OTP
- **Situação:** Jira ETI-30
- **Pendência (Tech lead):** como a API identifica a conta no passo 2, com o usuário ainda não logado.

### US04 · [auth] Confirmar e-mail por link
- **User Story:** Como um usuário, eu quero confirmar meu e-mail por um link, para que eu possa criar anúncios e me candidatar.
- **Critérios principais:**
  - Link de uso único, válido por 24 h, que abre uma página web servida pela `limio-api`.
  - Reenvio a cada 60 s, no máximo 5 por hora. Inclui "Usar outro e-mail".
  - Sem telefone **e** e-mail confirmados, o usuário loga, mas não cria anúncio nem se candidata.
- **Telas:** 04 Confirmar e-mail · página web "Confirmar e-mail"
- **UC:** Confirmar e-mail
- **Situação:** Jira ETI-30 + card de páginas web

### US05 · [auth] Entrar com e-mail e senha
- **User Story:** Como um usuário cadastrado, eu quero entrar com e-mail e senha, para que eu volte ao painel do meu último papel.
- **Critérios principais:**
  - Emite token de acesso (~15 min) e refresh token por aparelho (`Sessao`).
  - Restaura o último papel ativo.
  - 5 senhas erradas por e-mail em 15 min bloqueiam por 15 min. Erro sempre genérico.
  - Conta `BLOQUEADA` não entra e vê o aviso de conta suspensa.
- **Telas:** 05 Entrar
- **UC:** Login com e-mail e senha
- **Situação:** Jira ETI-32 + card FRONT-END par

### US06 · [auth] Sair do aparelho
- **User Story:** Como um usuário autenticado, eu quero sair da conta neste aparelho, para que ninguém use minha sessão nele.
- **Critérios principais:**
  - Revoga só a sessão do aparelho atual.
  - Botão "Sair" em Ajustes. Leva à tela 01 Boas-vindas.
- **Telas:** 11 Ajustes
- **UC:** Logout do dispositivo
- **Situação:** Jira ETI-32

### US07 · [auth] Alternar entre Empregador e Prestador
- **User Story:** Como um usuário autenticado, eu quero trocar entre os papéis Empregador e Prestador, para que eu use os dois lados da plataforma com uma única conta.
- **Critérios principais:**
  - O papel fica em `Usuario.papelAtivo` e vale para a conta inteira.
  - Conta `BLOQUEADA` não troca de papel.
  - Ao virar Prestador com perfil incompleto, o app leva ao preenchimento do perfil de atuação (US18) antes do mural.
- **Telas:** 07 Trocar papel
- **UC:** Alternar papel Empregador/Prestador
- **Situação:** Jira ETI-32
- **Pendência (Tech lead):** como o `auth` lê `PerfilPrestador.completo` sem importar o módulo `prestador`.

### US08 · [auth] Recuperar senha por e-mail
- **User Story:** Como um usuário que esqueceu a senha, eu quero receber um link para criar uma nova, para que eu recupere o acesso.
- **Critérios principais:**
  - Resposta sempre genérica, exista ou não o e-mail.
  - Link de uso único, válido por 1 h, que abre a página web "Nova senha".
  - Máximo de 3 pedidos por hora por e-mail.
  - Ao redefinir, encerra **todas** as sessões e leva à tela 05 Entrar.
- **Telas:** 06 Recuperar senha · página web "Nova senha"
- **UC:** Recuperar senha por e-mail
- **Situação:** Jira ETI-33 + card FRONT-END par

### US09 · [auth] Alterar senha logado
- **User Story:** Como um usuário autenticado, eu quero trocar minha senha informando a atual, para que eu proteja minha conta.
- **Critérios principais:**
  - Senha atual incorreta é recusada. Nova senha igual à atual é recusada.
  - Mantém este aparelho com novos tokens e encerra os outros.
  - Envia o e-mail "Sua senha foi alterada. Não foi você?".
  - Toast "Senha alterada com sucesso" e volta para Ajustes.
- **Telas:** Alterar senha (sem número) · 11 Ajustes
- **UC:** Alterar senha autenticado
- **Situação:** Jira ETI-33

---

## Módulo `conta`

### US10 · [conta] Encerrar minha conta
- **User Story:** Como um usuário autenticado, eu quero encerrar definitivamente minha conta, para que meus dados pessoais sejam anonimizados conforme a LGPD.
- **Critérios principais:**
  - Confirmação por checkbox "Entendi que a exclusão é irreversível" e botão destrutivo, sem senha.
  - Apaga CPF, data de nascimento, cidade/UF, localização do Prestador, foto e arquivos (do storage).
  - Anonimiza nome, e-mail, telefone, nome de exibição e endereços. E-mail e telefone ficam livres.
  - Bloqueia o CPF por 12 meses em `CpfBloqueado` e registra `LogAuditoria`.
  - Encerra todas as sessões e leva à tela 01 Boas-vindas.
  - Dispara evento para os outros módulos (US38).
- **Telas:** 11 Ajustes · 12 Encerrar conta
- **UC:** Encerrar conta
- **Situação:** Jira ETI-36 + card FRONT-END par
- **Pendência (PO):** o que acontece com `Combinado` com 24h ou mais e com `EmAndamento`.

### US11 · [conta] Configurar preferências de notificação
- **User Story:** Como um usuário autenticado, eu quero ligar e desligar Push, E-mail, SMS e WhatsApp, para que eu seja avisado só pelos canais que quero.
- **Critérios principais:**
  - Padrão de conta nova: Push ligado, E-mail desligado, WhatsApp conforme o opt-in.
  - WhatsApp só liga com consentimento gravado em `AceiteTermo`.
  - E-mails de segurança saem sempre.
  - Permissão de push negada no aparelho mostra aviso com atalho para os ajustes.
- **Telas:** 11 Ajustes
- **UC:** Configurar preferências de notificação
- **Situação:** Jira ETI-34 + card FRONT-END par
- **Pendência (PO):** padrão do canal SMS.

### US12 · [conta] Rotina diária de limpeza de dados
- **User Story:** Como plataforma, eu quero apagar automaticamente os dados que passaram do prazo de retenção, para que o LIMIO cumpra a LGPD sem trabalho manual.
- **Critérios principais:**
  - Roda uma vez por dia.
  - Apaga registros de `CpfBloqueado` já liberados.
  - Apaga logs de `LogAuditoria` com mais de 5 anos.
  - Apaga sessões encerradas há mais de 6 meses.
- **Telas:** nenhuma (rotina do sistema)
- **UC:** decisão do PO registrada na base (exclusão de conta)
- **Situação:** Nova

### US13 · [conta] Exportar meus dados — **Candidata**
- **User Story:** Como um usuário autenticado, eu quero baixar uma cópia dos meus dados, para que eu exerça meu direito de portabilidade da LGPD.
- **Critérios principais (do modelo de dados):**
  - O pedido cria uma `ExportacaoDados` com `status` (`StatusExportacao`).
  - Quando pronto, o arquivo fica disponível por um link com prazo (`expiraEm`).
- **Telas:** não existe
- **UC:** não existe
- **Situação:** Candidata
- **Pendências:** **PO:** entra no MVP? · **Design:** tela · **Tech lead:** valores de `StatusExportacao` e formato do arquivo.

### US14 · [conta] Bloquear outro usuário — **Candidata**
- **User Story:** Como um usuário autenticado, eu quero bloquear outra pessoa, para que ela não interaja mais comigo.
- **Critérios principais (do modelo de dados):**
  - Grava `BloqueioUsuario` (`bloqueador`, `bloqueado`). Desbloquear preenche `removidoEm`.
- **Telas:** não existe
- **UC:** não existe
- **Situação:** Candidata
- **Pendências:** **PO:** entra no MVP? O que o bloqueio impede (chat, candidatura, ver anúncio)? · **Design:** onde fica o botão.

---

## Módulo `contratante`

### US15 · [contratante] Gerenciar meu perfil de Empregador
- **User Story:** Como um Empregador, eu quero editar meu nome de exibição, foto e contatos, para que os prestadores me reconheçam.
- **Critérios principais:**
  - Mostra e edita `nomeExibicao`, foto, telefone e e-mail de contato.
  - Foto com tipo ou tamanho inválido é recusada (usa US51).
  - Anúncios futuros passam a usar os novos dados.
- **Telas:** 08 Meu perfil · Dados de contato
- **UC:** Gerenciar perfil empregador
- **Situação:** Nova
- **Pendência (Tech lead):** trocar telefone ou e-mail aqui exige nova confirmação (US03/US04)?

### US16 · [contratante] Gerenciar endereços salvos
- **User Story:** Como um Empregador, eu quero cadastrar, editar, remover e marcar um endereço padrão, para que eu crie anúncios mais rápido.
- **Critérios principais:**
  - Campos de `EnderecoSalvo`: apelido, CEP, logradouro completo, bairro/região, cidade, UF, latitude e longitude.
  - Só um endereço pode ser o padrão (`isPadrao`).
  - Remover um endereço usado só em anúncios terminais é permitido (`removidoEm`).
  - Anúncios `Combinado` mantêm o snapshot do endereço da escolha.
- **Telas:** 09 Endereços salvos · Novo endereço
- **UC:** Gerenciar perfil empregador
- **Situação:** Nova
- **Pendências:** **PO:** remover endereço usado em anúncio ainda aberto é permitido? · **Tech lead:** de onde vêm latitude e longitude (busca por CEP/geocodificação).

### US17 · [contratante] Ver meu painel de Empregador
- **User Story:** Como um Empregador, eu quero ver meus anúncios e seus andamentos em um painel, para que eu saiba o que precisa da minha ação.
- **Critérios principais:**
  - Lista os anúncios do próprio Empregador com status e quantidade de candidatos.
  - Atalho para criar anúncio (US29).
  - Ponto de chegada do login e da troca para o papel Empregador.
- **Telas:** 13 Dashboard
- **UC:** não há UC específico (painel citado no UC de login)
- **Situação:** Nova
- **Pendência (PO/Design):** o que o painel mostra além da lista de anúncios.

---

## Módulo `prestador`

### US18 · [prestador] Preencher meu perfil de atuação
- **User Story:** Como um Prestador, eu quero informar especialidades, raio, município-base e horários, para que eu veja no mural só os anúncios que combinam comigo.
- **Critérios principais:**
  - Campos: especialidades (inclui "Outros"), raio em km, município-base/UF e janelas de atendimento.
  - Remover todas as especialidades é aceito, mas o mural fica vazio.
  - O mural passa a filtrar com os novos parâmetros assim que salva.
  - Calcula `PerfilPrestador.completo`.
- **Telas:** 10 Perfil de atuação · Especialidades
- **UC:** Gerenciar perfil prestador
- **Situação:** Nova
- **Pendência (PO):** quais campos tornam o perfil completo.

### US19 · [prestador] Ver o mural de anúncios
- **User Story:** Como um Prestador, eu quero ver os anúncios compatíveis comigo, para que eu encontre serviços para fazer.
- **Critérios principais:**
  - Exige perfil completo, telefone e e-mail confirmados e papel Prestador ativo. Perfil incompleto leva à US18.
  - Mostra descrição, fotos, nome e foto do Empregador, categoria, data/hora e bairro/região.
  - Nunca mostra endereço completo, telefone, e-mail nem WhatsApp.
  - FREE e GOLD veem os mesmos campos, sem prioridade.
  - Sem resultados, mostra o estado vazio.
- **Telas:** 28 Mural · 29 Mural vazio · 30 Detalhe do anúncio
- **UC:** Visualizar mural com dados básicos
- **Situação:** Nova

### US20 · [prestador] Filtrar o mural
- **User Story:** Como um Prestador, eu quero filtrar o mural, para que eu encontre mais rápido o que me interessa.
- **Critérios principais:**
  - Regra fixa de compatibilidade: categoria está nas especialidades, ou é "Outros", ou o Prestador tem "Outros"; e distância ≤ raio.
  - Filtro de horário é só de interface, não bloqueia o match.
- **Telas:** 28a Filtros do mural
- **UC:** Filtrar mural por categoria, raio e Outros
- **Situação:** Nova
- **Pendência (PO/Design):** quais filtros a tela oferece além de horário.

### US21 · [prestador] Candidatar-me a um anúncio
- **User Story:** Como um Prestador, eu quero me candidatar a um anúncio, para que o Empregador me considere e possamos conversar.
- **Critérios principais:**
  - Só para anúncio em `AguardandoCandidatos`, com telefone e e-mail confirmados.
  - Recusa: anúncio próprio; já existe candidatura `Pendente` ou `Escolhida` do mesmo par; FREE com cota esgotada (US24).
  - Candidatura anterior `Recusada` ou `Encerrada` permite nova candidatura.
  - Cria `Aplicacao` em `Pendente`, **não** consome cota, abre o chat 1:1 e notifica o Empregador.
  - Após o sucesso, o app oferece abrir o chat.
- **Telas:** 30 Detalhe do anúncio · 31 Candidatar-se
- **UC:** Aplicar para um serviço
- **Situação:** Nova

### US22 · [prestador] Desistir da candidatura
- **User Story:** Como um Prestador, eu quero desistir de uma candidatura pendente, para que eu libere minha agenda.
- **Critérios principais:**
  - Só para candidatura `Pendente`. Se já foi escolhido, deve usar US44.
  - Marca `Encerrada` por desistência, chat fica somente leitura e não altera cota.
  - O candidato some da lista do Empregador.
- **Telas:** 32a Aplicações pendentes
- **UC:** Desistir da aplicação
- **Situação:** Nova

### US23 · [prestador] Acompanhar minhas candidaturas
- **User Story:** Como um Prestador, eu quero ver minhas candidaturas pendentes, combinadas e o histórico, para que eu acompanhe meus serviços.
- **Critérios principais:**
  - Três abas: pendentes, combinadas e histórico.
  - Mostra só candidaturas do próprio Prestador.
  - Em anúncios onde não foi escolhido, não mostra endereço completo nem contatos.
- **Telas:** 32a Aplicações pendentes · 32b Aplicações combinadas · 32c Aplicações histórico
- **UC:** não há UC específico (telas existem)
- **Situação:** Nova

### US24 · [prestador] Controlar a cota mensal FREE
- **User Story:** Como plataforma, eu quero limitar o Prestador FREE a 4 escolhas por mês, para que o plano GOLD tenha valor.
- **Critérios principais:**
  - A cota só é consumida na escolha (US37), nunca na candidatura.
  - Com 4 escolhas no mês, nova candidatura é recusada e aparece a tela de cota esgotada com CTA para o GOLD.
  - O contador zera no dia 1, 00:00 (America/Sao_Paulo).
  - GOLD ativo não tem teto.
- **Telas:** 33 Cota esgotada
- **UC:** Bloquear aplicação com cota esgotada · Consumir cota FREE na escolha
- **Situação:** Nova

### US25 · [prestador] Assinar o plano GOLD
- **User Story:** Como um Prestador, eu quero assinar o GOLD, para que eu não tenha limite de escolhas no mês.
- **Critérios principais:**
  - Mostra preço e ciclo, que vêm de parâmetros (`Plano`).
  - Pagamento pelo checkout do gateway, só para a assinatura.
  - Pagamento aprovado ativa o GOLD na hora (`isGoldAtivo`) e envia o recibo.
  - Pagamento recusado mantém FREE e informa a falha.
  - GOLD não muda o mural nem antecipa contatos.
- **Telas:** 34 Assinar GOLD
- **UC:** Assinar plano GOLD
- **Situação:** Nova
- **Pendências:** **Tech lead:** qual gateway · **PO:** preço e ciclo do plano.

### US26 · [prestador] Cadastrar ou trocar o cartão do GOLD
- **User Story:** Como um Prestador, eu quero cadastrar ou trocar o cartão da assinatura, para que a cobrança continue funcionando.
- **Critérios principais:**
  - Os dados do cartão são digitados no fluxo do gateway.
  - O LIMIO guarda só o token (`MeioPagamento`), nunca número ou CVV.
  - Falha do gateway mostra o erro e nada é gravado.
- **Telas:** 35 Gerenciar GOLD
- **UC:** Cadastrar ou atualizar método de pagamento
- **Situação:** Nova

### US27 · [prestador] Cancelar a renovação do GOLD
- **User Story:** Como um Prestador GOLD, eu quero cancelar a renovação, para que eu não seja cobrado no próximo ciclo.
- **Critérios principais:**
  - Mantém o GOLD até o fim do período pago e notifica.
  - No fim do ciclo, volta para FREE. Escolhas feitas como GOLD não contam no teto.
  - Reassinar antes do fim mantém o GOLD sem interrupção.
- **Telas:** 35 Gerenciar GOLD
- **UC:** Cancelar assinatura GOLD
- **Situação:** Nova

### US28 · [prestador] Tratar falha de cobrança do GOLD
- **User Story:** Como plataforma, eu quero tentar cobrar de novo quando a renovação falhar, para que o Prestador não perca o GOLD por um problema pontual.
- **Critérios principais:**
  - O aviso de falha do gateway chega por webhook, é registrado em `Cobranca` e o Prestador é notificado.
  - Novas tentativas em fila, em quantidade parametrizável.
  - Esgotadas as tentativas, volta para FREE.
  - Webhook repetido não gera cobrança duplicada (idempotência).
- **Telas:** nenhuma (rotina do sistema) · aviso em 43 Notificações
- **UC:** Falha de cobrança e retry
- **Situação:** Nova

---

## Módulo `anuncio`

### US29 · [anuncio] Criar e publicar um anúncio
- **User Story:** Como um Empregador, eu quero publicar uma demanda de serviço, para que prestadores próximos se candidatem.
- **Critérios principais:**
  - Exige telefone e e-mail confirmados e papel Empregador ativo.
  - Campos: categoria (inclui "Outros"), descrição, data/hora, endereço (salvo ou avulso), observações; opcionais: tamanho do local e número de pessoas. Sem valor.
  - Data/hora no passado é recusada.
  - Cria o anúncio em `AguardandoCandidatos`, com snapshot do endereço.
  - Após publicar, mostra a tela de anúncio publicado.
- **Telas:** 14 Novo anúncio 1 · 14a Escolher categoria · 15 Novo anúncio 2 · 16 Anúncio publicado
- **UC:** Criar anúncio de serviço (sem valor)
- **Situação:** Nova

### US30 · [anuncio] Anexar fotos ao anúncio
- **User Story:** Como um Empregador, eu quero anexar fotos ao anúncio, para que os prestadores entendam o serviço antes de se candidatar.
- **Critérios principais:**
  - Só em `AguardandoCandidatos` (na criação ou edição).
  - Arquivo inválido é recusado. Fotos gravadas como `Midia` `FOTO_ANUNCIO`.
  - As fotos aparecem no mural sem precisar se candidatar.
- **Telas:** 15 Novo anúncio 2 · 16a Editar anúncio
- **UC:** Anexar fotos ao anúncio
- **Situação:** Nova
- **Pendência (PO):** quantidade máxima de fotos e tamanho máximo.

### US31 · [anuncio] Editar anúncio antes da escolha
- **User Story:** Como um Empregador, eu quero corrigir meu anúncio enquanto ninguém foi escolhido, para que ele fique certo para os candidatos.
- **Critérios principais:**
  - Só em `AguardandoCandidatos`. Data/hora continua no futuro.
  - Depois de `Combinado`, a edição é recusada; mudança de data/hora vai para reagendamento (US46).
  - O mural mostra a nova versão.
- **Telas:** 16a Editar anúncio
- **UC:** Editar anúncio antes da escolha
- **Situação:** Nova
- **Pendência (PO):** candidatos já inscritos são avisados da edição?

### US32 · [anuncio] Cancelar anúncio antes da escolha
- **User Story:** Como um Empregador, eu quero cancelar um anúncio que ainda não tem escolhido, para que ele saia do mural.
- **Critérios principais:**
  - Só em `AguardandoCandidatos`, com confirmação.
  - Marca `Cancelado`, candidaturas `Pendente` viram `Encerrada`, chats ficam somente leitura e a cota não muda.
- **Telas:** 17 Cancelar anúncio
- **UC:** Cancelar anúncio antes da escolha
- **Situação:** Nova

### US33 · [anuncio] Mostrar o anúncio no mural certo e avisar prestadores
- **User Story:** Como plataforma, eu quero indexar cada anúncio por categoria e localização, para que só prestadores compatíveis o vejam e sejam avisados.
- **Critérios principais:**
  - Indexa por categoria e geolocalização, sem expor latitude/longitude nem logradouro.
  - Avisa os prestadores compatíveis, respeitando as preferências de notificação.
  - Sem prestador no raio, o anúncio existe, mas não aparece em nenhum mural.
- **Telas:** nenhuma (rotina do sistema)
- **UC:** Publicar no mural geográfico
- **Situação:** Nova

### US34 · [anuncio] Expirar anúncio sem candidatos
- **User Story:** Como plataforma, eu quero retirar do mural anúncios vencidos e sem candidatos, para que o mural mostre só demandas reais.
- **Critérios principais:**
  - Rotina periódica: `AguardandoCandidatos` + data/hora passada + zero candidaturas → `Expirado`.
  - Remove do mural, não altera cota e notifica o Empregador.
  - Com ao menos uma candidatura, não expira por esta regra.
- **Telas:** nenhuma (rotina do sistema)
- **UC:** Expirar anúncio sem combinação
- **Situação:** Nova
- **Pendência (PO):** o que acontece com anúncio vencido que **tem** candidatos e ninguém foi escolhido.

### US35 · [anuncio] Ver os candidatos do meu anúncio
- **User Story:** Como um Empregador, eu quero ver quem se candidatou, para que eu escolha o melhor prestador.
- **Critérios principais:**
  - Lista candidaturas `Pendente` com nome, foto, média (se houver) e especialidades.
  - Não libera telefone nem endereço.
  - Toque no candidato abre o perfil público (US52) e o chat.
  - Sem candidatos, mostra o estado vazio.
- **Telas:** 18 Candidatos · 19 Candidatos vazio · 20a Perfil público do candidato
- **UC:** Empregador listar candidatos
- **Situação:** Nova

### US36 · [anuncio] Recusar um candidato
- **User Story:** Como um Empregador, eu quero recusar um candidato, para que ele saiba que não foi escolhido.
- **Critérios principais:**
  - Só candidatura `Pendente` em anúncio `AguardandoCandidatos`.
  - Marca `Recusada`, chat do par somente leitura, demais candidatos continuam e o Prestador é notificado.
- **Telas:** 18 Candidatos · 20a Perfil público do candidato
- **UC:** Recusar um candidato
- **Situação:** Nova

### US37 · [anuncio] Escolher o prestador
- **User Story:** Como um Empregador, eu quero escolher um candidato, para que o serviço fique combinado e ele receba meu contato e endereço.
- **Critérios principais:**
  - Confirmação antes de escolher.
  - Transação atômica: anúncio vira `Combinado`, a candidatura escolhida vira `Escolhida` e as demais `Pendente` viram `Encerrada` (as `Recusada` continuam `Recusada`).
  - Consome 1 da cota do Prestador FREE; GOLD ativo não consome.
  - Cota esgotada entre a candidatura e a escolha: recusa e informa o Empregador; os demais candidatos continuam.
  - Duas escolhas simultâneas: só a primeira vale; a segunda recebe erro de conflito.
  - Libera telefone/WhatsApp e endereço completo **só** ao escolhido. Chats dos demais ficam somente leitura.
  - Notifica o escolhido e os não escolhidos.
  - Após o sucesso, vai para a tela de serviço combinado.
- **Telas:** 23 Confirmar escolha · 24 Escolha recusada · 25 Serviço combinado
- **UC:** Empregador escolhe um prestador · Encerrar demais aplicações após a escolha · Consumir cota FREE na escolha
- **Situação:** Nova

### US38 · [anuncio] Encerrar compromissos de conta encerrada ou suspensa
- **User Story:** Como plataforma, eu quero encerrar os compromissos abertos de quem saiu ou foi suspenso, para que a outra parte não fique esperando.
- **Critérios principais:**
  - Reage ao evento de encerramento de conta (US10) ou de suspensão (US58).
  - Anúncios abertos e candidaturas encerrados.
  - `Combinado` com menos de 24h cancelado, sem estorno de cota.
  - `AguardandoValidacao` vira "Cancelado por saída de conta".
  - Reagendamentos pendentes encerrados sem efeito.
- **Telas:** nenhuma (reação do sistema)
- **UC:** Encerrar conta (fluxos alternativos) · Admin moderar denúncia e suspender conta
- **Situação:** Jira (backlog, sem ID)
- **Pendência (PO):** `Combinado` com 24h ou mais e `EmAndamento`.

---

## Módulo `servico`

### US39 · [servico] Ver o serviço combinado
- **User Story:** Como Empregador ou Prestador escolhido, eu quero ver os detalhes do serviço combinado com os contatos da outra parte, para que a gente se organize.
- **Critérios principais:**
  - Mostra data/hora vigente, endereço completo, telefone/WhatsApp e status.
  - Só as duas partes do serviço acessam.
  - Dá acesso às ações do estado atual: iniciar, check-out, validar, cancelar, propor reagendamento.
- **Telas:** 25 Serviço combinado · 36 Combinado (prestador)
- **UC:** Empregador escolhe um prestador (liberação do lead)
- **Situação:** Nova

### US40 · [servico] Iniciar o serviço
- **User Story:** Como Prestador escolhido, eu quero marcar que cheguei, para que o Empregador saiba que o serviço começou.
- **Critérios principais:**
  - Só o Prestador escolhido, com anúncio `Combinado`.
  - Muda para `EmAndamento` (`iniciadoEm`) e notifica o Empregador.
  - A partir daqui o Empregador não cancela e não há reagendamento; proposta pendente é encerrada sem efeito.
  - O passo é opcional: a validação presencial funciona direto de `Combinado`.
- **Telas:** 36 Combinado (prestador) · 37 Serviço em andamento
- **UC:** Prestador iniciar serviço
- **Situação:** Nova

### US41 · [servico] Fazer o check-out com foto
- **User Story:** Como Prestador escolhido, eu quero enviar a foto do serviço pronto, para que o Empregador valide à distância.
- **Critérios principais:**
  - Só em `EmAndamento` ou `Combinado`, com ao menos 1 foto (`Midia` `EVIDENCIA_CHECKOUT`).
  - Muda para `AguardandoValidacao` (`checkoutEm`) e notifica o Empregador para validar e pagar fora da plataforma.
  - O Prestador nunca marca `Concluido` sozinho.
- **Telas:** 38 Check-out
- **UC:** Prestador marcar conclusão com foto
- **Situação:** Nova

### US42 · [servico] Validar o serviço
- **User Story:** Como Empregador, eu quero confirmar que o serviço foi feito, para que o ciclo se encerre e eu pague o prestador.
- **Critérios principais:**
  - Presencial: a partir de `Combinado` ou `EmAndamento`, sem foto.
  - Pela foto: a partir de `AguardandoValidacao`.
  - A tela avisa que o pagamento é feito fora do LIMIO.
  - Marca `Concluido` (`validadoEm`) e abre a avaliação (US53).
  - Validação à distância sem check-out é recusada.
- **Telas:** 27 Validar serviço
- **UC:** Solicitante validar o serviço (presencial ou pela foto)
- **Situação:** Nova

### US43 · [servico] Empregador cancelar o serviço combinado
- **User Story:** Como Empregador, eu quero cancelar um serviço combinado com antecedência, para que o Prestador se organize.
- **Critérios principais:**
  - Só em `Combinado` e com 24h ou mais até a data vigente. Abaixo disso, recusa.
  - Marca `Cancelado`, estorna a cota FREE, chat somente leitura e notifica o Prestador.
  - Dentro da carência pós-reagendamento (padrão 24h): permitido, mas marca `CanceladoTardio`, sem estorno, com auditoria das duas datas.
  - Em `EmAndamento` ou `AguardandoValidacao`, recusa e orienta a usar denúncia.
- **Telas:** 26 Cancelar combinado
- **UC:** Empregador cancelar após combinação (≥ 24h)
- **Situação:** Nova

### US44 · [servico] Prestador cancelar depois de escolhido
- **User Story:** Como Prestador escolhido, eu quero cancelar um serviço que não vou conseguir fazer, para que o Empregador saiba a tempo.
- **Critérios principais:**
  - Só em `Combinado` ou `EmAndamento`. Em `AguardandoValidacao`, recusa.
  - Marca `Cancelado` (terminal), não estorna cota, não volta ao mural e notifica o Empregador.
  - Proposta de reagendamento pendente é encerrada sem efeito.
- **Telas:** 39 Cancelar (prestador)
- **UC:** Prestador cancelar após ser escolhido
- **Situação:** Nova

### US45 · [servico] Concluir automaticamente por silêncio
- **User Story:** Como plataforma, eu quero concluir serviços que ninguém fechou, para que nada fique aberto para sempre.
- **Critérios principais:**
  - Rotina periódica.
  - `Combinado` ou `EmAndamento` passado o prazo pós-agenda (padrão 24h) → `Concluido`.
  - `AguardandoValidacao` passado o prazo de validação (padrão 24h após o check-out) → `Concluido`.
  - Proposta de reagendamento pendente suspende a conclusão.
  - Não reprocessa `Concluido` nem `Cancelado`. Oferece a avaliação.
- **Telas:** nenhuma (rotina do sistema)
- **UC:** Conclusão automática por silêncio
- **Situação:** Nova

### US46 · [servico] Propor nova data para o serviço
- **User Story:** Como Empregador ou Prestador escolhido, eu quero propor uma nova data, para que a gente remarque sem cancelar.
- **Critérios principais:**
  - Só em `Combinado`, sem outra proposta pendente e abaixo do `limite_reagendamentos`.
  - Nova data no futuro e justificativa obrigatória.
  - Com a data vigente já passada, só uma proposta é permitida (se outra foi recusada ou expirou, recusa).
  - Grava o `Reagendamento`, notifica a outra parte, suspende a conclusão por silêncio e registra auditoria.
  - O proponente pode cancelar a proposta antes da resposta.
- **Telas:** 40 Propor reagendamento
- **UC:** Propor reagendamento do serviço
- **Situação:** Nova
- **Pendência (PO):** valores de `limite_reagendamentos` e `prazo_resposta_reagendamento`.

### US47 · [servico] Responder à proposta de nova data
- **User Story:** Como a outra parte do serviço, eu quero aceitar ou recusar a nova data, para que a agenda fique combinada entre nós.
- **Critérios principais:**
  - Mostra data vigente, data proposta, justificativa e prazo de resposta.
  - Aceitar: muda a data, mantém `Combinado`, conta o reagendamento, recalcula prazos, inicia a carência e notifica os dois.
  - Recusar: mantém a data original e notifica o proponente.
  - Sem resposta no prazo: a proposta expira sem efeito.
  - Data proposta já passada no aceite: recusa e encerra a proposta.
- **Telas:** 41 Responder reagendamento
- **UC:** Responder proposta de reagendamento
- **Situação:** Nova

---

## Módulo `chat`

### US48 · [chat] Conversar com a outra parte
- **User Story:** Como Empregador ou Prestador candidato, eu quero conversar em tempo real, para que a gente combine escopo e valor.
- **Critérios principais:**
  - O chat 1:1 nasce na candidatura (US21). Sem candidatura `Pendente` ou `Escolhida`, não há chat.
  - Entrega em tempo real (WebSocket), com histórico salvo e status de entregue e lida.
  - O valor conversado não vira cobrança.
  - Candidatura recusada, encerrada ou não escolhida: chat somente leitura (`isSomenteLeitura`), com histórico preservado.
  - Usuário excluído aparece como "Usuário excluído".
- **Telas:** 21 Chat · 22 Chat somente leitura
- **UC:** Conversar no chat após aplicar
- **Situação:** Nova
- **Pendência (PO):** envio de imagem entra no MVP? O modelo tem `Midia` `ANEXO_MENSAGEM`.

### US49 · [chat] Ver minhas conversas
- **User Story:** Como usuário, eu quero ver a lista das minhas conversas, para que eu retome qualquer uma rapidamente.
- **Critérios principais:**
  - Lista separada por papel (Empregador e Prestador).
  - Mostra a outra parte, o anúncio, a última mensagem e as não lidas.
  - Conversas somente leitura aparecem identificadas.
- **Telas:** 42 Conversas · 42b Conversas (prestador)
- **UC:** não há UC específico (telas existem)
- **Situação:** Nova

### US50 · [chat] Esconder contatos enviados antes da escolha — **Candidata**
- **User Story:** Como plataforma, eu quero mascarar telefones e e-mails digitados no chat antes da escolha, para que ninguém pule a escolha e a cota.
- **Critérios principais (do modelo de dados):**
  - A mensagem guarda `texto` original e `textoExibido` mascarado.
  - Cada caso gera uma `TentativaContato` (`padraoDetectado`, `trechoMascarado`).
- **Telas:** não existe
- **UC:** não existe
- **Situação:** Candidata
- **Pendências:** **PO:** entra no MVP? Mascara também depois da escolha? · **Tech lead:** quais padrões detectar.

---

## Módulo `perfil`

### US51 · [perfil] Enviar foto de perfil
- **User Story:** Como usuário, eu quero colocar minha foto, para que as pessoas me reconheçam no mural e no perfil.
- **Critérios principais:**
  - Valida tipo e tamanho; arquivo inválido é recusado com mensagem.
  - Grava `Midia` `FOTO_PERFIL`, com metadados de localização (EXIF) removidos.
  - A foto aparece no mural e no perfil público.
- **Telas:** 08 Meu perfil
- **UC:** Enviar foto de perfil
- **Situação:** Nova
- **Pendência (PO):** tipos e tamanho máximo aceitos. A mesma foto vale para os dois papéis?

### US52 · [perfil] Ver o perfil público e a reputação
- **User Story:** Como usuário, eu quero ver o perfil de outra pessoa, para que eu decida se confio nela.
- **Critérios principais:**
  - Mostra nome de exibição, foto, quantidade de avaliações e histórico resumido de serviços concluídos.
  - Média com uma casa decimal só com ao menos 1 avaliação; sem avaliações, mostra "sem avaliações" (nunca 0,0).
  - A média aparece assim que a primeira avaliação é gravada.
  - Nunca mostra endereço nem telefone.
  - Perfil anonimizado não mostra dados pessoais.
- **Telas:** 20a Perfil público do candidato · 20b Perfil público (consulta)
- **UC:** Visualizar perfil público e reputação · Exibir média somente com avaliações
- **Situação:** Nova

### US53 · [perfil] Avaliar a outra parte
- **User Story:** Como Empregador ou Prestador, eu quero avaliar quem trabalhou comigo, para que outros usuários saibam em quem confiar.
- **Critérios principais:**
  - Só para anúncio `Concluido`, uma vez por pessoa por serviço.
  - Nota de 1 a 5 obrigatória; comentário opcional. Comentário sem nota é recusado.
  - Pode pular sem gerar nota e avaliar depois, dentro de 7 dias após `Concluido`.
  - Recalcula `mediaAvaliacoes` e `qtdAvaliacoes`.
  - Nunca bloqueia o uso da plataforma.
- **Telas:** 45 Avaliação
- **UC:** Avaliar a outra parte · Pular avaliação
- **Situação:** Nova

### US54 · [perfil] Responder a uma avaliação — **Candidata**
- **User Story:** Como usuário avaliado, eu quero responder publicamente a uma avaliação, para que eu dê minha versão.
- **Critérios principais (do modelo de dados):**
  - Grava `Avaliacao.resposta`.
- **Telas:** não existe
- **UC:** não existe
- **Situação:** Candidata
- **Pendências:** **PO:** entra no MVP? Uma resposta só? Pode editar?

---

## Módulo a definir

> Estas histórias não se encaixam com clareza nos 8 módulos atuais (notificações, moderação e administração). **Decisão do tech lead:** criar módulos novos ou distribuir nos existentes. A sugestão de módulo está ao lado de cada uma.

### US55 · Ver minhas notificações *(sugestão: `conta`)*
- **User Story:** Como usuário, eu quero ver a lista das minhas notificações, para que eu não perca nenhuma atualização.
- **Critérios principais:**
  - Lista `Notificacao` com título, corpo e data, marcando lida (`lidaEm`) ao abrir.
  - Notificação ligada a um anúncio leva à tela dele.
- **Telas:** 43 Notificações
- **UC:** não há UC específico (tela existe)
- **Situação:** Nova

### US56 · Enviar notificações respeitando as preferências *(sugestão: `conta`)*
- **User Story:** Como plataforma, eu quero enviar cada aviso só pelos canais que o usuário ligou, para que ele receba o que quer e como quer.
- **Critérios principais:**
  - Todo evento que notifica (candidatura, escolha, cancelamento, reagendamento, check-out etc.) passa por um único serviço de envio.
  - O serviço consulta `PreferenciaNotificacao` e não envia por canal desligado.
  - WhatsApp só com consentimento ativo. E-mails de segurança saem sempre.
  - Toda notificação também fica gravada para a US55.
- **Telas:** nenhuma (serviço do sistema)
- **UC:** Configurar preferências de notificação · Publicar no mural geográfico
- **Situação:** Nova
- **Pendências:** **Tech lead:** provedores de SMS, e-mail, WhatsApp e push; onde ficam os tokens de push; valores de `TipoNotificacao` e `CanalNotificacao`.

### US57 · Registrar uma denúncia *(sugestão: módulo novo de moderação)*
- **User Story:** Como usuário, eu quero denunciar um perfil, anúncio, chat ou serviço, para que a plataforma analise mau comportamento.
- **Critérios principais:**
  - Motivos: mau comportamento, fraude, serviço não realizado e não pagamento fora da plataforma.
  - Evidência opcional (`Midia` `EVIDENCIA_DENUNCIA`).
  - Abre `Denuncia` na fila do admin.
  - Não reabre o serviço, não muda status do anúncio e não move dinheiro.
- **Telas:** 46 Denúncia
- **UC:** Registrar denúncia
- **Situação:** Nova

### US58 · Admin moderar denúncia e aplicar sanção *(sugestão: módulo novo de moderação)*
- **User Story:** Como Administrador, eu quero analisar denúncias e aplicar sanções, para que a plataforma continue segura.
- **Critérios principais:**
  - Mostra histórico, chat, fotos e dados do alvo.
  - Sanções: advertência, ocultar avaliação, suspender ou encerrar conta. Também pode fechar como improcedente.
  - Nunca marca serviço como pago ou não pago.
  - Suspensão: conta vira `BLOQUEADA`, sessões são revogadas e os compromissos abertos são encerrados (US38).
  - Toda decisão vai para `LogAuditoria`.
- **Telas:** não existe (é área administrativa)
- **UC:** Admin moderar denúncia e suspender conta
- **Situação:** Nova
- **Pendências:** **Design:** telas do admin · **Tech lead:** o admin é web ou app? valores de `VereditoModeracao`, `TipoSancao`, `SeveridadeDenuncia`, `StatusResolucaoDenuncia`.

### US59 · Dashboard administrativo *(sugestão: módulo novo de administração)*
- **User Story:** Como Administrador, eu quero ver os números da operação, para que eu acompanhe a saúde da plataforma.
- **Critérios principais:**
  - Somente leitura: usuários, anúncios, candidaturas, escolhas, GOLD ativas, denúncias abertas e status resumido.
  - Usuário comum recebe 403.
  - Atalho para a fila de denúncias (US58).
- **Telas:** não existe
- **UC:** Dashboard administrativo
- **Situação:** Nova

### US60 · Entrar como Administrador — **Candidata**
- **User Story:** Como Administrador, eu quero entrar em uma área separada, para que só a equipe acesse a moderação.
- **Critérios principais (do modelo de dados):**
  - `Administrador` é entidade separada de `Usuario` (`email`, `senhaHash`, `ativo`).
- **Telas:** não existe
- **UC:** não existe (implícito nos UCs de admin)
- **Situação:** Candidata
- **Pendência (Tech lead):** como o admin autentica; existe também `PapelUsuario.ADMIN`, o que parece duplicar a entidade `Administrador`.

### US61 · Recorrer de uma sanção — **Candidata**
- **User Story:** Como usuário sancionado, eu quero contestar a decisão, para que um erro possa ser revisto.
- **Critérios principais (do modelo de dados):**
  - Grava `Recurso`, com decisão `DecisaoRecurso`.
- **Telas:** não existe
- **UC:** não existe
- **Situação:** Candidata
- **Pendências:** **PO:** entra no MVP? Prazo para recorrer?

### US62 · Admin ajustar parâmetros e catálogo — **Candidata**
- **User Story:** Como Administrador, eu quero ajustar prazos, limites e categorias sem publicar código, para que a operação se adapte rápido.
- **Critérios principais (do modelo de dados e UCs):**
  - `Parametro` (`chave`, `valor`, `tipo`) com histórico em `ParametroHistorico`.
  - Exemplos citados nos UCs: `carencia_pos_reagendamento`, `limite_reagendamentos`, `prazo_resposta_reagendamento`, prazo pós-agenda, tentativas de cobrança, preço do GOLD.
  - A categoria "Outros" não pode ser desativada.
- **Telas:** não existe
- **UC:** citado em Gerenciar perfil prestador e nos UCs com parâmetros
- **Situação:** Candidata
- **Pendência (PO/Tech lead):** no MVP, os parâmetros podem ser ajustados direto no banco?

---

## Pendências consolidadas

### PO
- Critério de perfil de Prestador completo (US18).
- Exclusão de conta com `Combinado` ≥ 24h ou `EmAndamento` (US10, US38).
- Padrão do canal SMS (US11).
- Anúncio vencido com candidatos e sem escolha (US34).
- Limites de fotos do anúncio e da foto de perfil (US30, US51).
- Avisar candidatos quando o anúncio é editado (US31).
- Remover endereço usado em anúncio aberto (US16).
- Conteúdo do painel do Empregador e filtros do mural (US17, US20).
- Preço e ciclo do GOLD (US25); limites de reagendamento (US46).
- Imagem no chat (US48).
- Entram no MVP? US13, US14, US50, US54, US61, US62.

### Tech lead
- Módulos para notificações, moderação e administração (US55 a US62).
- Gateway de pagamento (US25 a US28).
- Provedores de envio e tokens de push (US56).
- Autenticação do admin e duplicidade `PapelUsuario.ADMIN` × `Administrador` (US60).
- Geolocalização de endereços (US16).
- Valores de todos os enums ainda sem valores.

### Design
- Telas para: área do admin (US58, US59), bloqueio de usuário (US14), exportação de dados (US13), resposta a avaliação (US54) e recurso (US61), caso entrem no MVP.
