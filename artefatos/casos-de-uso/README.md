# Casos de uso

- **Diagrama:** [`diagrama-casos-de-uso.png`](diagrama-casos-de-uso.png) (card [ETI-17](https://kaueamaral96.atlassian.net/browse/ETI-17))
- **Especificação:** [`especificacao-casos-de-uso.pdf`](especificacao-casos-de-uso.pdf), com finalidade, atores, pré-condições, fluxo principal e fluxos alternativos de cada caso de uso (cards [ETI-8](https://kaueamaral96.atlassian.net/browse/ETI-8) e [ETI-24](https://kaueamaral96.atlassian.net/browse/ETI-24))
- **Planilha de trabalho:** [Google Sheets](https://docs.google.com/spreadsheets/d/1kWNyoly5FkJhXvtluj5rvOOADmTCcx7xr4R0tdRfUdw/edit?usp=sharing)
- **Página no Confluence:** [Documentação de Casos de Uso](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/7667713)

## Atores

| Ator | Papel |
| --- | --- |
| Visitante | Ainda sem conta; pode se cadastrar. |
| Usuário | Pessoa com conta única (CPF + e-mail), que alterna entre os papéis abaixo. |
| Empregador | Publica anúncios, escolhe o prestador e valida o serviço. |
| Prestador (FREE ou GOLD) | Vê o mural, se candidata e executa o serviço. |
| Administrador | Analisa denúncias, aplica sanções e acompanha o dashboard. |
| Sistema | Rotinas automáticas: expiração, conclusão por silêncio, cobrança do GOLD. |

## Casos de uso por área

| Área | Casos de uso |
| --- | --- |
| Acesso e identidade | Cadastrar conta universal · Recusar cadastro duplicado · Confirmar telefone por OTP · Confirmar e-mail · Login com e-mail e senha · Recuperar senha por e-mail · Alterar senha autenticado · Logout do dispositivo · Alternar papel Empregador/Prestador · Encerrar conta |
| Perfis | Gerenciar perfil empregador · Gerenciar perfil prestador · Visualizar perfil público e reputação · Enviar foto de perfil · Configurar preferências de notificação |
| Anúncio | Criar anúncio de serviço (sem valor) · Anexar fotos ao anúncio · Editar anúncio antes da escolha · Cancelar anúncio antes da escolha · Publicar no mural geográfico · Expirar anúncio sem combinação · Consultar histórico com filtros |
| Mural e candidatura | Visualizar mural com dados básicos · Filtrar mural por categoria, raio e Outros · Aplicar para um serviço · Desistir da aplicação · Empregador listar candidatos · Recusar um candidato · Conversar no chat após aplicar |
| Escolha e cota | Empregador escolhe um prestador · Encerrar demais aplicações após a escolha · Consumir cota FREE na escolha · Bloquear aplicação com cota esgotada |
| Assinatura GOLD | Assinar plano GOLD · Cadastrar ou atualizar método de pagamento · Cancelar assinatura GOLD · Falha de cobrança e retry |
| Execução do serviço | Prestador iniciar serviço · Prestador marcar conclusão com foto · Solicitante validar o serviço (presencial ou pela foto) · Empregador cancelar após combinação (≥ 24h) · Prestador cancelar após ser escolhido · Conclusão automática por silêncio · Propor reagendamento do serviço · Responder proposta de reagendamento |
| Confiança e moderação | Avaliar a outra parte · Pular avaliação · Exibir média somente com avaliações · Registrar denúncia · Admin moderar denúncia e suspender conta · Dashboard administrativo |

## Diferenças conhecidas em relação ao código

A especificação é de agosto. No código, alguns nomes mudaram:

- O status inicial do anúncio é `PUBLICADO` (no documento, "AguardandoCandidatos"), e "Combinado" não é um status: é o anúncio `PUBLICADO` com uma candidatura `ESCOLHIDA`.
- A candidatura pendente é `ENVIADA` (no documento, "Pendente").
- A conta é criada antes do SMS, e não depois (decisão do grupo no ETI-30).

Os diagramas de atividade de 27/10 ([`../atividade/`](../atividade/)) já estão com os nomes do código.
