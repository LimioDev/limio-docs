# Especificação de requisitos e regras de negócio — LIMIO

> Cópia da página do Confluence [Especificação de requisitos e regras de negócio](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/557058), versão 1.3 de 06/10/2026. A página do Confluence é a fonte oficial.

**Versão:** 1.3 · **Data:** 06/10/2026 · **Versão anterior:** 1.2, de 29/08/2026

**Alterações da 1.3:** incorporação das decisões de Acesso e Identidade tomadas até 06/10 e alinhamento com o DER de 06/10. Novo **RF70** (política de senha). Prazos e limites definidos em RF05, RF06, RF07 e RF08. Encerramento de sessões em RF08 e RF09. Detalhamento da exclusão de conta (RF13, RNF02) e das preferências de notificação e opt-in de WhatsApp (RF01, RF19). RF59 passa a recusar o login de conta suspensa. CPF incluído entre os dados sensíveis (RNF03). Limites de segurança referenciados no RNF04. Glossário: papel ativo por conta e status da conta. Revisão de texto em RB12, RB19 e RNF13.

**Alterações da 1.2:** remoção do RF20 (listar sessões ativas) do escopo da fase 1 — a gestão de sessões e dispositivos deixa de ser requisito do produto. O encerramento de sessão continua coberto pelo RF10 (logout do dispositivo atual) e pelo RNF01. O número RF20 passa a não ser utilizado, conforme a regra de identificadores estáveis da seção 3.

**Alterações da 1.1:** separação entre edição unilateral do anúncio (RF26) e reagendamento consensual do serviço combinado (RF69, RB35, RB36). Novos parâmetros de reagendamento no RF68. Ajustes de consistência em RB08, RB09, RB17, RB27 e RB31. Complemento: RB35 (e RF69) admitem no máximo uma proposta após a data vigente, para o job de silêncio não ficar suspenso em cadeia.

------------------------------------------------------------------------

## 1.1 Atores

| Ator                         | Descrição                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------|
| **Usuário**                  | Pessoa física com conta única (CPF + e-mail). Pode alternar papéis.                                  |
| **Empregador**               | Papel que cria anúncios, recebe aplicações, conversa e escolhe um prestador.                         |
| **Prestador**                | Papel que vê o mural, aplica, conversa e executa o serviço se for escolhido.                         |
| **Prestador FREE**           | Prestador sem assinatura GOLD ativa. Teto de 4 serviços *escolhidos* por mês calendário.             |  
| **Prestador GOLD**           | Prestador com assinatura GOLD ativa. Combinações ilimitadas. Mesma visibilidade de mural que o FREE. |
| **Administrador**            | Operador interno que modera denúncias, avaliações e contas, e acompanha volumetria.                  |
| **Sistema**                  | Jobs, notificações, expiração, cobrança recorrente e auditoria.                                      |

## 1.2 O que o produto é

- Mural de demandas pontuais filtrado por categoria, raio e disponibilidade declarada.

- Match em duas etapas: **aplicação do prestador** e **escolha do empregador**.

- Chat in-app somente após a aplicação, para negociar escopo e valor.

- Liberação de telefone/WhatsApp e endereço completo somente após a escolha.

- Finalização em duas vias: o **solicitante valida** o serviço (presencialmente ou pela foto do prestador) **antes de pagar fora da plataforma**; se ninguém agir após a data, o sistema marca `Concluido`.

- Depois da combinação, a data acordada só muda por **proposta com aceite das duas partes** (reagendamento). O anúncio não volta ao mural e nenhuma cota é alterada.

- Assinatura recorrente GOLD como único produto pago da fase 1.

## 1.3 O que o produto não é (fase 1)

- Escrow, split, boleto ou gateway para pagar o serviço em si.

- Marketplace com busca/convite de prestadores pelo empregador.

- Rede de equipes (N prestadores no mesmo anúncio).

- KYC biométrico ou consulta Receita Federal além de formato/unicidade de CPF.

- Cadastro PJ / CNPJ.

- Destaque, ranking pago ou dados extras de mural para GOLD.

- Garantia, seguro, estorno ou mediação de pagamento/qualidade off-platform. Denúncia não transfere dinheiro.

------------------------------------------------------------------------

## 2. Glossário

| Termo                           | Definição                                                                                                                                                                                                                                                  |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Anúncio / Demanda / Serviço** | Pedido publicado pelo empregador, com categoria, descrição, fotos, data/hora, região e (após escolha) endereço.                                                                                                                                            |
| **Mural**                       | Lista/radar de anúncios em `AguardandoCandidatos` compatíveis com o prestador.                                                                                                                                                                             |
| **Dados básicos**               | O que aparece no mural **antes** de aplicar: descrição, fotos, nome de exibição, categoria, bairro/região. Sem endereço completo e sem telefone.                                                                                                           |
| **Aplicação**                   | Ato do prestador de se candidatar a um anúncio. Não consome cota. Libera o chat.                                                                                                                                                                           |
| **Candidato**                   | Prestador com aplicação `Pendente` naquele anúncio.                                                                                                                                                                                                        |
| **Escolha / Combinação**        | Ato do empregador de selecionar **um** candidato. Trava o anúncio, consome cota FREE, libera lead.                                                                                                                                                         |
| **Lead**                        | Acesso definitivo ao telefone/WhatsApp do empregador (e endereço completo) após a escolha.                                                                                                                                                                 |
| **Cota FREE**                   | Limite de 4 escolhas recebidas no mês calendário. Conta serviço em que o prestador FREE **foi escolhido**, não aplicações.                                                                                                                                 |
| **GOLD**                        | Assinatura recorrente do prestador que remove o teto de cota.                                                                                                                                                                                              |
| **Chat**                        | Mensageria in-app 1:1 entre empregador e um candidato, habilitada só após aplicar.                                                                                                                                                                         |
| **Check-out**                   | Prestador registra que terminou o trabalho e envia evidência fotográfica. Não libera pagamento na plataforma (não há pagamento na plataforma).                                                                                                             |
| **Reagendamento**               | Alteração consensual da data/hora de um serviço já `Combinado`. Depende de proposta de uma parte e aceite da outra (RF69). Não altera cota, não devolve o anúncio ao mural e não reabre aplicações.                                                        |
| **Proposta de reagendamento**   | Registro com data anterior, data proposta, justificativa, proponente e prazo de resposta. Enquanto pendente, suspende a conclusão por silêncio (RB09). Expira sem efeito se não respondida no prazo.                                                       |
| **Carência pós-reagendamento**  | Janela iniciada no aceite de um reagendamento (default 24h) durante a qual o cancelamento pelo empregador é classificado como `CanceladoTardio` (RB36).                                                                                                    |
| **CanceladoTardio**             | Motivo de cancelamento registrado quando o empregador cancela dentro da carência pós-reagendamento. O anúncio vai para o estado `Cancelado`; a cota **não** é estornada. É motivo, não estado: a máquina de estados não muda.                              |
| **Validação**                   | Ato do **solicitante** de confirmar que o serviço está feito — presencialmente (viu/testou no local) ou pela foto do check-out. A validação é o sinal para pagar o prestador **fora** do LIMIO. Marca `Concluido`.                                         |
| **Conclusão por silêncio**      | Se a data agendada **vigente** passou e ninguém moveu o anúncio, ou se houve check-out e o solicitante não validou no prazo, o sistema marca `Concluido`. Proposta de reagendamento pendente suspende essa conclusão (RF46, RB09).                         |
| **Denúncia de não pagamento**   | Prestador reporta que o solicitante não pagou o combinado. Não gera estorno nem cobrança pelo LIMIO; serve para moderação de conta e fica coberto pelos Termos de Uso.                                                                                     |
| **Papel ativo**                 | Visão corrente do usuário: Empregador ou Prestador. Vale para a conta inteira (não por aparelho) e é restaurado no login. No código, Empregador corresponde a `PapelUsuario.CONTRATANTE`.                                                                  |
| **Status da conta**             | `PENDENTE_VERIFICACAO` (conta criada, telefone ou e-mail ainda não confirmado), `ATIVA` (telefone e e-mail confirmados) e `BLOQUEADA` (conta suspensa, RF59). A conta excluída é identificada pela data de anonimização. Transições a confirmar pelo time. |

------------------------------------------------------------------------

## 3. Requisitos funcionais

Requisitos são testáveis. Cada RF descreve uma capacidade do sistema. Os identificadores são estáveis: um RF mantém seu número mesmo que seja inserido em uma seção temática diferente da ordem numérica, e um número retirado do escopo não é reaproveitado. Por isso o RF69 aparece na seção 3.6 e os números RF11 e RF20 não são utilizados.

### 3.1 Acesso, autenticação e identidade

- **RF01 — Cadastro universal:** o sistema permite criar conta informando nome, e-mail, celular, senha (RF70), CPF, data de nascimento e localização (cidade/UF), além do aceite obrigatório dos Termos de Uso e da Política de Privacidade. O celular aceita DDD + 9 dígitos começando por 9 e é gravado como `+55DDNNNNNNNNN`. Cidade/UF é escolhida por autocompletar com a lista do IBGE, e a API valida a UF entre as 27. O cadastro oferece opt-in de WhatsApp, **desmarcado por padrão e separado** do aceite dos Termos (RF19). Durante a confirmação, o usuário pode corrigir o celular ("Trocar número") e o e-mail ("Usar outro e-mail"). A conta é criada no envio do formulário, com papel ativo Empregador; a escolha de papel ocorre após o login, por alternância.

- **RF02 — Validação de maioridade:** o cadastro é recusado se a idade calculada for menor que 18 anos.

- **RF03 — Unicidade de identidade:** o sistema rejeita cadastro com CPF ou e-mail já existentes, ativos ou anonimizados recentemente segundo RB13.

- **RF04 — Formato de CPF:** o sistema valida dígitos verificadores e formato do CPF no cadastro.

- **RF05 — Login e-mail/senha:** autenticação com e-mail e senha, possível somente após a confirmação do telefone (RF06). Após sucesso, o sistema restaura o último papel ativo (ou Empregador, se nunca definido) e roteia ao dashboard correspondente. O papel ativo vale para a conta inteira, não por aparelho. Após **5 senhas erradas** para o mesmo e-mail em **15 minutos**, o login fica bloqueado por **15 minutos**. A mensagem de erro é sempre genérica, sem revelar se o e-mail existe.

- **RF06 — Confirmar telefone por OTP:** no cadastro (ou se o telefone ainda não estiver verificado), o sistema envia por SMS um código de **6 dígitos**, válido por **5 minutos**, com até **5 tentativas**. O reenvio é permitido a cada **60 segundos**, no máximo **5 vezes por hora** por telefone. O sistema só considera o cadastro utilizável para criar anúncio ou aplicar com telefone e e-mail confirmados.

- **RF07 — Confirmar e-mail:** o sistema envia por e-mail um **link de uso único, válido por 24 horas**, que abre uma página web servida pela própria API. O reenvio do link é permitido a cada 60 segundos, no máximo 5 vezes por hora. Login com senha pode ocorrer antes; criar anúncio e aplicar exigem e-mail confirmado.

- **RF08 — Recuperação de senha por e-mail:** o usuário solicita a redefinição informando o e-mail. A resposta é sempre genérica, exista ou não o e-mail (anti-enumeração). O sistema envia um **link de uso único, válido por 1 hora**, que abre a página web "Nova senha" servida pela API. São aceitos no máximo **3 pedidos por hora** por e-mail; acima disso, a resposta continua genérica e nada é enviado. Ao redefinir, **todas as sessões** da conta são encerradas e o usuário volta à tela de login.

- **RF09 — Alterar senha autenticado:** o usuário logado informa a senha atual e a nova senha (RF70). Senha atual incorreta é recusada, e a nova senha não pode ser igual à atual. Ao concluir, a sessão do aparelho atual é mantida com novos tokens, as sessões dos **outros aparelhos são encerradas** e o sistema envia o e-mail "Sua senha foi alterada. Não foi você?".

- **RF10 — Logout:** o usuário encerra a sessão no dispositivo atual.

- **RF70 — Política de senha:** a senha tem de **8 a 72 caracteres**, com pelo menos **1 letra e 1 número**; caractere especial não é obrigatório. A regra vale no cadastro (RF01), na redefinição (RF08) e na alteração (RF09). O app mostra os requisitos em tempo real e só libera o envio quando todos estão atendidos.

- **RF12 — Alternar papel:** usuário autenticado troca a visão entre Empregador e Prestador sem novo cadastro. Prestador exige perfil de atuação preenchido (RF18) antes de ver o mural ou aplicar.

- **RF13 — Encerrar conta (LGPD):** o usuário solicita a exclusão confirmando, por checkbox, que entende que a ação é irreversível (sem pedir senha). O sistema **apaga** CPF, data de nascimento, cidade/UF, localização do prestador, foto e demais arquivos do usuário (removidos do armazenamento, não só desvinculados) e **anonimiza** nome, e-mail, telefone, nome de exibição e endereços salvos; e-mail e telefone ficam livres para novo cadastro. O reuso do CPF fica bloqueado por 12 meses (RB13). O sistema encerra anúncios e aplicações abertos conforme RB27, encerra **todas as sessões** e registra auditoria.

### 3.2 Perfis

- **RF14 — Gerenciar perfil empregador:** edição de nome de exibição, foto, telefones, e-mail de contato e endereços salvos.

- **RF15 — Endereços salvos:** o empregador cadastra, edita, remove e marca um endereço padrão. Um anúncio referencia um endereço salvo ou um endereço avulso.

- **RF16 — Foto de perfil:** upload de imagem com validação de tipo/tamanho. A foto fica visível no mural (nome + foto) para candidatos e no perfil público.

- **RF17 — Perfil público:** qualquer usuário autenticado visualiza nome, foto, média de avaliações (se houver, RB11), quantidade de avaliações e histórico resumido de serviços concluídos (sem endereço/telefone de terceiros).

- **RF18 — Gerenciar perfil prestador:** especialidades (uma ou mais, incluindo `Outros`), raio de atendimento (km), município-base, e janelas de horário de atuação.

- **RF19 — Preferências de notificação:** o usuário habilita/desabilita Push, e-mail, SMS e WhatsApp de forma independente. Padrão de conta nova: **Push ligado**, **e-mail desligado** e **WhatsApp conforme o opt-in** do cadastro (RF01); o padrão do SMS ainda será definido. O WhatsApp só pode ser ligado com consentimento registrado (documento, versão, origem, IP e data); sem consentimento, nada é enviado por WhatsApp, e desligar interrompe os envios por esse canal. E-mails de segurança (senha alterada, exclusão de conta, novo login) são sempre enviados, independentemente das preferências. Se a permissão de push estiver negada no aparelho, o app avisa e oferece atalho para os ajustes do aparelho.

### 3.3 Dashboards

- **RF21 — Dashboard empregador:** lista anúncios do usuário com status, quantidade de candidatos, atalho para criar anúncio e atalho para chats ativos.

- **RF22 — Dashboard prestador (mural/radar):** lista anúncios compatíveis no raio, com dados básicos, atalhos para aplicações pendentes e serviços combinados.

- **RF23 — Dashboard administrativo:** volumetria de usuários, anúncios, aplicações, escolhas, assinaturas GOLD ativas, denúncias abertas e status operacional resumido.

### 3.4 Anúncios

- **RF24 — Criar anúncio:** formulário com categoria (incluindo `Outros`), descrição, data/hora pretendida, localização (endereço internamente; no mural só bairro/região), observações, e campos opcionais: tamanho do local, quantidade de pessoas, valor combinado informativo (vazio na criação). **Não exige** valor monetário.

- **RF25 — Anexar fotos ao anúncio:** o empregador envia uma ou mais fotos na criação ou enquanto o status for `AguardandoCandidatos`.

- **RF26 — Editar anúncio:** o empregador pode alterar descrição, categoria, fotos, campos opcionais e data/hora enquanto o anúncio estiver em `AguardandoCandidatos`. A partir de `Combinado`, a **edição unilateral** fica bloqueada. A alteração da data/hora após a combinação ocorre **exclusivamente pelo RF69**, que exige aceite da contraparte.

- **RF27 — Cancelar anúncio antes da escolha:** cancelamento livre em `AguardandoCandidatos`. Aplicações pendentes são encerradas (RB16).

- **RF28 — Publicar no mural:** ao criar, o anúncio entra em `AguardandoCandidatos` e fica visível aos prestadores compatíveis.

- **RF29 — Histórico e filtros:** empregador e prestador consultam histórico próprio com filtros de status e período.

- **RF30 — Expirar anúncio sem combinação:** job do sistema marca `Expirado` o anúncio em `AguardandoCandidatos` cuja data/hora agendada já passou e que **não possui nenhuma aplicação**. Se houver ao menos uma aplicação, este job não expira o anúncio (RB09).

### 3.5 Mural, match, aplicação e escolha

- **RF31 — Visualizar mural (dados básicos):** o prestador vê descrição, fotos, nome de exibição do empregador, foto, categoria, data/hora, bairro/região. **Não vê** endereço completo, telefone, e-mail nem WhatsApp.

- **RF32 — Motor de match:** o mural lista apenas anúncios cuja categoria está nas especialidades do prestador **ou** a categoria do anúncio é `Outros` **ou** o prestador possui `Outros`; e cuja localização está dentro do raio a partir do município-base/ponto de atuação do prestador. Horários declarados são filtro opcional de UX, não bloqueio rígido na fase 1.

- **RF33 — Aplicar para anúncio:** o prestador cria uma aplicação `Pendente`. Aplicar não consome cota. Não é permitido aplicar duas vezes no mesmo anúncio ativo.

- **RF34 — Desistir da aplicação:** o prestador, com aplicação `Pendente`, cancela a própria candidatura. Não há consumo de cota.

- **RF35 — Listar candidatos:** o empregador vê prestadores com aplicação `Pendente` (nome, foto, média se houver, especialidades).

- **RF36 — Recusar candidato:** o empregador recusa uma aplicação `Pendente`. A aplicação vai para `Recusada`. O chat daquele par encerra em somente leitura.

- **RF37 — Chat após aplicação:** ao aplicar, o sistema abre thread 1:1. Ambas as partes enviam texto (e, se suportado, imagem) enquanto a aplicação estiver `Pendente` ou `Escolhida` e o anúncio não estiver terminal.

- **RF38 — Escolher prestador:** o empregador seleciona **um** candidato. A operação é atômica: anúncio → `Combinado`; aplicação escolhida → `Escolhida`; demais `Pendente` → `Encerrada`; cota FREE consumida se aplicável; lead liberado.

- **RF39 — Encerrar demais aplicações:** após a escolha, candidatos não escolhidos deixam de ver o anúncio como aberto; chats respectivos ficam somente leitura; nenhum telefone é liberado para eles.

- **RF40 — Liberar lead:** somente o prestador `Escolhida` passa a ver telefone/WhatsApp e endereço completo do anúncio.

- **RF41 — Impedir aplicação com cota esgotada:** prestador FREE com 4 escolhas no mês calendário corrente não consegue aplicar. GOLD não tem esse bloqueio.

- **RF42 — Impedir escolha de prestador FREE sem saldo:** se, entre aplicar e a escolha, a cota do FREE esgotar, o sistema recusa a escolha desse candidato e informa o empregador.

### 3.6 Execução do serviço

- **RF43 — Iniciar serviço:** o prestador escolhido, com anúncio `Combinado`, marca início. Status → `EmAndamento`.

- **RF44 — Check-out com evidência fotográfica:** o prestador em `EmAndamento` (ou `Combinado`, se já executou sem marcar início) registra conclusão e envia ao menos uma foto. Status → `AguardandoValidacao`. A foto serve para o solicitante validar quando não estiver no local. **Não há pagamento na plataforma.**

- **RF45 — Validar serviço (solicitante):** o empregador, em `Combinado`, `EmAndamento` ou `AguardandoValidacao`, confirma que o serviço está feito. Validação presencial não exige foto. Validação à distância exige check-out com foto (RF44). A interface deixa explícito que, ao validar, o solicitante deve **pagar o prestador fora do LIMIO**. Status → `Concluido`.

- **RF46 — Conclusão automática por silêncio:** o sistema marca `Concluido` quando: (a) a data/hora agendada **vigente** passou, o anúncio está `Combinado` ou `EmAndamento` e ninguém moveu no prazo pós-agenda; ou (b) está `AguardandoValidacao` e o solicitante não validou no prazo. Não exige foto nem validação explícita nesse fallback. **Enquanto existir proposta de reagendamento pendente (RF69), o sistema não conclui o anúncio por silêncio: a avaliação fica suspensa até o aceite, a recusa ou a expiração da proposta (RB09).**

- **RF47 — Cancelar após combinação (empregador):** permitido apenas se faltar **pelo menos 24h** para a data/hora agendada **vigente** e o status for `Combinado` (não `EmAndamento` nem `AguardandoValidacao`). Estorna cota se o prestador era FREE (RB08, RB17). Exceção: se o cancelamento ocorrer dentro da carência posterior a um reagendamento aceito, aplica-se a **RB36** — o cancelamento é registrado com motivo `CanceladoTardio` e **não** há estorno de cota.

- **RF48 — Cancelar após combinação (prestador):** o prestador escolhido pode cancelar em `Combinado` ou `EmAndamento`. Cota **não** é estornada (RB18). Em `AguardandoValidacao` o prestador não cancela: o fluxo é validação, silêncio ou denúncia. O prestador escolhido que cancela após ter proposto ou aceito um reagendamento segue a regra geral: a cota permanece consumida (RB18). O motivo `CanceladoTardio` da RB36 **não** se aplica ao prestador, porque ele nunca recebe estorno — não há brecha econômica a fechar desse lado.

- **RF69 — Reagendar serviço combinado:** com o anúncio em `Combinado`, o empregador **ou** o prestador escolhido pode propor nova data/hora, informando justificativa obrigatória. O sistema notifica a contraparte e aguarda aceite. Com o **aceite**, a data/hora pretendida é atualizada, o anúncio **permanece em** `Combinado` e os prazos derivados (RB08 e RB09) passam a ser contados a partir da nova data. Com a **recusa** ou o decurso do prazo de resposta, a data original é mantida e a proposta é encerrada sem efeito. A proposta pode ser feita mesmo **depois de a data/hora vigente já ter passado**, desde que o anúncio ainda esteja em `Combinado`; enquanto a proposta estiver pendente, a conclusão por silêncio fica suspensa (RF46, RB09). Depois de a data vigente ter passado, é admitida no máximo **uma** proposta por serviço: recusada ou expirada essa proposta, o anúncio segue para a conclusão por silêncio (RB35). O reagendamento **não** devolve o anúncio ao mural, **não** reabre aplicações e **não** altera a cota em nenhuma hipótese. Em `EmAndamento`, `AguardandoValidacao` ou em estados terminais o reagendamento não é permitido.

- **RF49 — Denunciar não pagamento ou qualidade:** após `Concluido` (ou em `AguardandoValidacao`), prestador ou solicitante abre denúncia (RF57) por não pagamento, serviço não realizado ou fraude. A denúncia **não** altera o status para reabrir o serviço, **não** transfere dinheiro e **não** obriga o LIMIO a mediar o conflito off-platform (RB33).

- **RF50 — Registrar valor combinado (opcional):** qualquer uma das partes, após a escolha, pode informar um valor numérico meramente informativo. A plataforma não cobra nem valida se esse valor foi pago.

### 3.7 Notificações

- **RF51 — Push de nova demanda:** prestadores compatíveis recebem alerta de novo anúncio no raio, se a preferência estiver ativa.

- **RF52 — Notificações de aplicação e escolha:** empregador é avisado de nova aplicação; prestador é avisado de escolha, recusa ou encerramento; não escolhidos recebem aviso de que o anúncio foi combinado com outro.

- **RF53 — Notificações de status:** aviso de início, check-out, pedido de validação, validação, conclusão automática, cancelamento, expiração (só mural sem escolha), **proposta de reagendamento recebida, aceite de reagendamento, recusa de reagendamento e expiração da proposta sem resposta**.

- **RF54 — Notificações de assinatura:** recibo de cobrança GOLD, falha de pagamento da assinatura, cancelamento e downgrade.

### 3.8 Confiança, denúncia e administração

- **RF55 — Avaliação mútua opcional:** após `Concluido`, o sistema oferece nota 1–5 e comentário para ambas as partes. É possível pular. Não bloqueia o uso da plataforma.

- **RF56 — Cálculo de média:** a média aritmética é recalculada a cada nova avaliação e exibida só se existir ao menos uma nota (RB11).

- **RF57 — Central de denúncias:** usuário autenticado denuncia anúncio, chat, perfil ou serviço. Motivos incluem mau comportamento, fraude, serviço não realizado e **não pagamento do valor combinado fora da plataforma**. Evidência opcional. A denúncia não move dinheiro.

- **RF58 — Moderação administrativa:** admin analisa denúncia, histórico, chat e fotos; aplica advertência, oculta avaliação, suspende ou encerra conta. Admin **não** determina quem deve pagar o serviço nem transfere valores. Conflitos de pagamento/qualidade são off-platform (Termos de Uso).

- **RF59 — Suspensão de conta:** conta suspensa (status `BLOQUEADA`) não autentica: o login é recusado e o app exibe o aviso de conta suspensa. Os anúncios e aplicações abertos da conta são encerrados conforme RB27.

### 3.9 Financeiro e GOLD

- **RF60 — Cadastrar método de pagamento (GOLD):** prestador tokeniza cartão de crédito via gateway **somente para a assinatura GOLD**. A plataforma não armazena PAN/CVV. Esse método **não** paga o serviço combinado no chat.

- **RF61 — Assinar GOLD:** fluxo de adesão com cobrança recorrente. Ao confirmar pagamento, o prestador passa a GOLD imediatamente e deixa de ter teto de cota.

- **RF62 — Cancelar GOLD:** cancela a renovação. O prestador permanece GOLD até o fim do ciclo já pago; depois vira FREE (RB19).

- **RF63 — Atualizar método de pagamento:** o prestador substitui o token do cartão.

- **RF64 — Falha de pagamento:** o sistema registra falha, agenda retry (RNF09) e notifica. Após N tentativas parametrizáveis, faz downgrade para FREE.

- **RF65 — Consultar cota:** o prestador FREE vê quantas escolhas já ocorreram no mês e quantas restam (4 − usadas). GOLD vê “ilimitado”.

### 3.10 Auditoria e parâmetros

- **RF66 — Log de auditoria:** o sistema registra, de forma imutável, cadastro, login falho relevante, escolha, **proposta, aceite, recusa e expiração de reagendamento (com data anterior e data nova)**, cancelamento (com o motivo, incluindo `CanceladoTardio`), exclusão de conta, cobrança GOLD e ações administrativas.

- **RF67 — Catálogo de categorias:** admin (ou configuração) mantém categorias ativas. `Outros` não pode ser desativado (RB10).

- **RF68 — Parâmetros de negócio:** cota mensal (padrão 4), antecedência de cancelamento (24h), prazo pós-agenda para conclusão por silêncio (24h), prazo de validação após check-out (24h), `limite_reagendamentos` **— máximo de reagendamentos aceitos por serviço (default 2)**, `prazo_resposta_reagendamento` **— prazo para a contraparte responder a uma proposta (default 24h)**, `carencia_pos_reagendamento` **— janela após o aceite em que o cancelamento do empregador é classificado como tardio (default 24h)** e preço/ciclo GOLD são configuráveis sem novo deploy de regra hardcoded além dos defaults deste documento.

------------------------------------------------------------------------

## 4. Requisitos não funcionais

- **RNF01 — Autenticação:** JWT de acesso de curta duração + refresh token rotacionado. Logout invalida o refresh do dispositivo atual.

- **RNF02 — LGPD:** exclusão/anonimização irreversível de dados pessoais identificáveis (RF13). Contas inativas (sem login há 5 anos) entram no mesmo fluxo. Retenção: logs de auditoria por **5 anos**, que **não** são apagados no mesmo job de anonimização (RB14); registros de acesso por **6 meses** (Marco Civil da Internet, art. 15); histórico de consentimentos guardado. Uma rotina diária apaga os bloqueios de CPF já vencidos, os logs de auditoria com mais de 5 anos e as sessões encerradas há mais de 6 meses.

- **RNF03 — Criptografia:** TLS 1.2/1.3 em trânsito. AES-256 (ou equivalente do provedor) em repouso para dados sensíveis (**CPF**, telefone, endereço completo, tokens de pagamento). O bloqueio de reuso de CPF (RB13) guarda apenas o HMAC-SHA256 do CPF, com chave secreta mantida fora do código.

- **RNF04 — Segurança de aplicação:** proteção contra SQL injection, XSS, CSRF em web, IDOR em anúncio/chat/aplicação, enumeração de CPF e rate limit em login/recuperação de senha. Limites: login conforme RF05, código SMS conforme RF06, recuperação de senha conforme RF08. Erros de autenticação e de duplicidade de cadastro são sempre genéricos.

- **RNF05 — Auditoria:** trilha imutável (append-only) das ações de RF66.

- **RNF06 — Disponibilidade:** SLA de 99,5% mensal para API e app, excluídas janelas anunciadas.

- **RNF07 — Escalabilidade:** leitura do mural e escrita de aplicação/escolha dimensionáveis horizontalmente. A escolha (RF38) exige consistência forte / lock atômico.

- **RNF08 — Chat em tempo real:** WebSocket (ou equivalente) para entrega de mensagens com persistência.

- **RNF09 — Pagamentos da assinatura GOLD:** retry em fila para falhas transitórias do gateway; idempotência de webhook de cobrança. **Não se aplica** ao valor do serviço pontual.

- **RNF10 — Compatibilidade:** Android, iOS e web responsiva com os mesmos RFs.

- **RNF11 — CI/CD e testes:** pipeline com testes automatizados cobrindo no mínimo escolha atômica, cota, visibilidade de dados, validação do solicitante, conclusão por silêncio **e reagendamento — recontagem dos prazos de RB08/RB09 após o aceite, respeito ao** `limite_reagendamentos`**, suspensão da conclusão por silêncio com proposta pendente, e classificação como** `CanceladoTardio` **no cancelamento dentro da carência**.

- **RNF12 — Privacidade de geolocalização:** o mural nunca expõe lat/long exata nem logradouro antes da escolha.

- **RNF13 — Tempo de escolha:** a operação de escolha deve rejeitar concorrência (duas abas ou requisições do mesmo empregador escolhendo candidatos diferentes) com um único vencedor.

------------------------------------------------------------------------

## 5. Regras de negócio

Formato: **condição → ação → exceção**.

### 5.1 Modelo comercial

- **RB01 — Zero comissão e sem escrow:** SE o serviço for combinado, negociado, validado ou concluído, ENTÃO a plataforma não cobra, retém, transfere nem confirma o pagamento do trabalho. Exceção: nenhuma. A única cobrança é a assinatura GOLD. O pagamento do serviço ocorre fora (PIX, dinheiro, transferência etc.), após a validação do solicitante ou por acordo das partes.

- **RB02 — Sem valor obrigatório no anúncio:** SE o empregador cria o anúncio, ENTÃO o sistema não exige preço. Exceção: campo opcional informativo após a escolha (RF50), sem efeito financeiro.

- **RB03 — Papéis dinâmicos:** SE o usuário autenticado possui conta válida, ENTÃO pode atuar como empregador e, com perfil prestador completo, como prestador. Exceção: conta suspensa (RF59).

- **RB04 — GOLD só remove teto:** SE a assinatura GOLD está ativa, ENTÃO o prestador tem escolhas ilimitadas no mês. Exceção: GOLD não altera dados do mural, não dá prioridade e não antecipa telefone/endereço.

### 5.2 Chat, visibilidade e lead

- **RB05 — Chat só após aplicar:** SE não existe aplicação `Pendente` ou `Escolhida` daquele par, ENTÃO o chat não é criado. Exceção: nenhuma.

- **RB06 — Cota na escolha, não na aplicação:** SE o empregador escolhe um prestador FREE, ENTÃO incrementa a cota do mês calendário do prestador em 1. SE o prestador apenas aplica, ENTÃO a cota não muda.

- **RB07 — Lead somente para o escolhido:** SE a aplicação não está `Escolhida`, ENTÃO telefone, e-mail e endereço completo permanecem ocultos. Exceção: o próprio empregador sempre vê seus dados.

### 5.3 Cancelamento, cota e prazos

- **RB08 — Cancelamento do empregador após combinação:** SE o anúncio está `Combinado` E faltam **menos de 24h** para a data/hora agendada, ENTÃO o cancelamento do empregador é recusado. SE faltam ≥ 24h E status é `Combinado`, ENTÃO cancela e **estorna** a cota FREE. Exceção: em `EmAndamento` ou `AguardandoValidacao` o empregador não cancela por este fluxo (usa denúncia RF49). Exceção adicional: se o cancelamento ocorrer dentro de `carencia_pos_reagendamento` contada do aceite de um reagendamento, aplica-se a **RB36** — o cancelamento é registrado com motivo `CanceladoTardio`, sem estorno, ainda que a antecedência em relação à nova data seja ≥ 24h. A antecedência continua sendo medida sempre contra a **data vigente**, nunca contra a original.

- **RB09 — Expiração e conclusão por silêncio:**

  - SE `AguardandoCandidatos` E agora \> data/hora agendada E o anúncio **não tem nenhuma aplicação**, ENTÃO `Expirado`.

  - SE `AguardandoCandidatos` E agora \> data/hora agendada E existe ao menos uma aplicação, ENTÃO o anúncio **não** expira por esta regra (o empregador ainda pode escolher, recusar ou cancelar).

  - SE `Combinado` ou `EmAndamento` E agora \> data/hora agendada + prazo pós-agenda (default 24h) E ninguém validou, fez check-out nem cancelou, ENTÃO `Concluido` (silêncio).

  - SE `AguardandoValidacao` E o solicitante não validou no prazo (default 24h após o check-out), ENTÃO `Concluido`.

  - Após um reagendamento aceito (RB35), "data/hora agendada" significa sempre a **data vigente**, nunca a original.

  - SE existe proposta de reagendamento **pendente** no serviço, ENTÃO o job não conclui o anúncio por silêncio: a avaliação é adiada até o aceite, a recusa ou a expiração da proposta. Como a proposta expira em `prazo_resposta_reagendamento` (default 24h), a suspensão é limitada a essa janela.

  - Exceção: anúncio já `Concluido` ou `Cancelado` não é reprocessado. `Expirado` **não** se aplica após a escolha.

- **RB10 — Categoria Outros:** SE o catálogo de categorias for editado, ENTÃO `Outros` permanece ativo e selecionável em anúncio e em especialidades. Exceção: nenhuma.

- **RB11 — Média visível:** SE o usuário tem zero avaliações, ENTÃO o perfil público não exibe número de média (pode exibir “sem avaliações”). SE tem ≥ 1, ENTÃO exibe média com uma casa decimal.

- **RB12 — Escolha exclusiva e atômica:** SE duas requisições tentam escolher candidatos distintos no mesmo anúncio, ENTÃO apenas a primeira confirmada prevalece; a segunda recebe erro de conflito. Após o sucesso, não há segunda escolha. Exceção: nenhuma.

- **RB13 — Unicidade para não burlar cota:** SE CPF ou e-mail já existem, ENTÃO o cadastro é recusado. Conta excluída: o CPF **não** pode ser reutilizado por 12 meses (parametrizável) para reduzir conta-laranja de cota.

- **RB14 — Retenção de auditoria:** SE o usuário solicita exclusão, ENTÃO dados pessoais de perfil são anonimizados, MAS logs de RF66 permanecem pelo prazo LGPD de 5 anos, sem identificadores diretos quando tecnicamente possível (ID interno opaco).

### 5.4 Cota detalhada

- **RB15 — Ciclo da cota:** o contador FREE zera no dia 1 de cada mês, 00:00 America/Sao_Paulo. GOLD ativo não consome nem consulta teto.

- **RB16 — Cancelar anúncio antes da escolha:** SE o empregador cancela em `AguardandoCandidatos`, ENTÃO aplicações `Pendente` → `Encerrada`, chats somente leitura, **nenhuma cota é consumida**.

- **RB17 — Estorno por cancelamento do empregador:** SE o empregador cancela em `Combinado` dentro de RB08, ENTÃO a escolha daquele mês do prestador FREE é decrementada (mínimo 0). **EXCEÇÃO: não há decremento quando o cancelamento se enquadra na RB36 (**`CanceladoTardio`**).**

- **RB18 — Sem estorno se o prestador cancela:** SE o prestador escolhido cancela, ENTÃO a cota já consumida permanece consumida.

- **RB19 — Downgrade GOLD:** SE o prestador cancela a assinatura, ENTÃO permanece GOLD até `current_period_end` e depois vira FREE. Escolhas feitas enquanto ele era GOLD **não** contam para o teto FREE, mesmo no mesmo mês; apenas as escolhas feitas após o downgrade consomem as 4. Exceção: nenhuma.

- **RB20 — Bloqueio de aplicação por cota:** SE prestador é FREE E escolhas_no_mês ≥ 4, ENTÃO RF33 é recusado com mensagem para assinar GOLD. Aplicações já `Pendente` de meses anteriores não são apagadas, mas RF42 impede nova escolha se o saldo acabou no intervalo.

### 5.5 Match, aplicação e execução

- **RB21 — Compatibilidade de mural:** o anúncio só entra no mural do prestador se (categoria ∈ especialidades OU categoria = `Outros` OU prestador tem `Outros`) E distância ≤ raio. Prestador sem perfil completo (RF18) não vê mural.

- **RB22 — Uma aplicação por par:** SE já existe aplicação não terminal (`Pendente`/`Escolhida`) daquele prestador naquele anúncio, ENTÃO nova aplicação é recusada. Após `Recusada`/`Encerrada`/`desistência`, o prestador **pode aplicar de novo** no mesmo anúncio se ele ainda estiver `AguardandoCandidatos`.

- **RB23 — Desistência:** SE o prestador desiste com aplicação `Pendente`, ENTÃO status `Encerrada` por desistência, chat somente leitura, cota inalterada. Não pode desistir se já `Escolhida` (usa RF48).

- **RB24 — Recusa do empregador:** SE o empregador recusa um candidato, ENTÃO os demais permanecem. Recusar todos não escolhe ninguém; o anúncio segue `AguardandoCandidatos`.

- **RB25 — Um prestador por anúncio:** um anúncio `Combinado` não aceita nova aplicação nem segunda escolha.

- **RB26 — Início, check-out e validação:** o prestador `Escolhida` inicia (RF43) e/ou faz check-out com ≥ 1 foto (RF44). O **solicitante** valida (RF45) presencialmente (sem foto) ou pela foto. Validação → `Concluido` e é o momento em que o app orienta o pagamento **fora** da plataforma. O prestador não marca `Concluido` sozinho; só envia a foto e aguarda validação ou silêncio (RF46).

- **RB27 — Encerramento em cascata:** SE a conta é suspensa ou excluída, ENTÃO anúncios `AguardandoCandidatos` → `Cancelado`; `Combinado`/`EmAndamento` → `Cancelado` (tratado como cancelamento da parte que saiu: se saiu o prestador, RB18; se saiu o empregador em `Combinado` com ≥24h, RB17; se \<24h, cancela mesmo assim por impossibilidade operacional e **não** estorna — registrar em auditoria). `AguardandoValidacao` → `Concluido` por silêncio não se aplica neste caso: vira `Cancelado` por saída de conta. Propostas de reagendamento pendentes envolvendo o usuário que sai são encerradas sem efeito.

- **RB28 — Avaliação:** só após `Concluido`. Uma avaliação por par por serviço. Pular não gera nota. Comentário sem nota é recusado; nota sem comentário é aceita.

- **RB29 — Chat dos não escolhidos:** na escolha ou recusa, a thread fica somente leitura. Histórico permanece para as partes e para admin em denúncia.

- **RB30 — Fotos do anúncio:** visíveis no mural (dados básicos). Não substituem evidência de check-out.

- **RB31 — Data do anúncio:** a data/hora agendada deve ser no futuro no momento da criação. Edição em `AguardandoCandidatos` também exige futuro. A nova data/hora proposta em reagendamento (RF69) igualmente deve ser futura, verificada no momento da proposta **e** no momento do aceite (RB35).

- **RB32 — Autoaplicação:** o usuário **não** pode aplicar em anúncio criado por ele mesmo (mesmo UUID de usuário, papéis diferentes).

- **RB33 — Sem mediação de pagamento:** SE houver disputa sobre pagamento, qualidade ou “não fiz / não pagou”, ENTÃO as partes usam denúncia (RF49/RF57) e resolvem o conflito **fora** da plataforma, conforme Termos de Uso. O LIMIO não segura valor, não estorna, não marca “pago” e não decide o mérito financeiro. Denúncia pode gerar advertência/suspensão de conta (RF58), nunca transferência de dinheiro.

- **RB34 — Ordem validar → pagar:** SE o solicitante valida (RF45), ENTÃO o sistema considera o serviço feito e exibe orientação de pagamento off-platform. SE o solicitante pagar antes de validar (combinado presencial), ENTÃO ainda assim deve validar no app para fechar o ciclo; o LIMIO não verifica se o PIX ocorreu.

### 5.6 Reagendamento

- **RB35 — Efeito do reagendamento aceito:** SE a proposta de reagendamento é aceita pela contraparte, ENTÃO a nova data/hora substitui a anterior, o anúncio permanece em `Combinado` e os prazos de RB08 e RB09 passam a ser contados a partir da nova data. EXCEÇÕES: a nova data/hora deve ser futura no momento da proposta e no momento do aceite; existe no máximo **uma** proposta pendente por serviço; o número de reagendamentos aceitos por serviço não pode exceder `limite_reagendamentos` (default 2); a proposta expira sem efeito se não houver resposta dentro de `prazo_resposta_reagendamento` (default 24h) ou se o anúncio deixar de estar `Combinado` antes da resposta. A cota não é alterada em nenhuma hipótese. Depois de a data vigente ter passado, é admitida no máximo **uma** proposta de reagendamento por serviço: recusada ou expirada essa proposta, o anúncio segue para a conclusão por silêncio na execução seguinte do job.

- **RB36 — Carência pós-reagendamento:** SE o empregador cancela o anúncio dentro de `carencia_pos_reagendamento` (default 24h) contada do **aceite** de um reagendamento, ENTÃO o cancelamento é registrado com motivo `CanceladoTardio`, **sem estorno de cota**, independentemente da antecedência em relação à nova data — afastando a RB17. EXCEÇÃO: esta regra **não cria permissão de cancelamento**; se faltarem menos de 24h para a data vigente, o cancelamento continua sendo recusado pela RB08. A regra aplica-se somente ao empregador: o prestador nunca recebe estorno (RB18), de modo que o mesmo incentivo não existe do lado dele.
