# Diagrama de classes

- **Diagrama:** [`diagrama-de-classes.png`](diagrama-de-classes.png)
- **Card:** [ETI-9](https://kaueamaral96.atlassian.net/browse/ETI-9) · Criação de Diagrama de Classes (concluído na Sprint 4)
- **Versão de referência:** 06/10/2026. Junto com o DER, é a referência do modelo de dados do projeto.

## Como o diagrama aparece no código

As classes de domínio viram entidades JPA dentro do módulo dono delas (ver [system design](../../system-design/system-design.md#5-back-end-monolito-modular-por-domínio)):

| Módulo | Entidades no código |
| --- | --- |
| `auth` | `Usuario`, `Sessao`, `TentativaLogin`, `VerificacaoContato`, `CpfBloqueado` |
| `perfil` | `PerfilEmpregador`, `EnderecoSalvo`, `PerfilPrestador`, `Categoria`, `JanelaAtendimento`, `Midia` |
| `anuncio` | `Anuncio`, `Aplicacao`, `Reagendamento` |
| `notificacao` | `PreferenciaNotificacao` |
| `comum` | `LogAuditoria` |

As classes de chat, avaliação, denúncia, assinatura GOLD e notificações enviadas entram no código nas Sprints 6 e 7.
