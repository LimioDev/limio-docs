# Diagrama Entidade-Relacionamento (DER)

- **Diagrama:** [`der.png`](der.png)
- **Card:** [ETI-10](https://kaueamaral96.atlassian.net/browse/ETI-10) · Criação de Diagrama Entidade-Relacionamento
- **Página no Confluence:** [Documentação do DER](https://kaueamaral96.atlassian.net/wiki/spaces/~71202081061b4b9b5c4bbea63b29ec57d232c6/pages/7962625), com o modelo conceitual e o físico
- **Versão de referência:** 06/10/2026

## Tabelas que já existem no banco

O banco é criado pelas migrations do Flyway em `limio-api/src/main/resources/db/migration/` (`V1` a `V19` em 27/10).

| Módulo | Tabelas |
| --- | --- |
| `auth` | `usuario`, `sessao`, `tentativa_login`, `verificacao_contato`, `cpf_bloqueado` |
| `perfil` | `perfil_empregador`, `endereco_salvo`, `perfil_prestador`, `prestador_categoria`, `categoria`, `janela_atendimento`, `midia` |
| `anuncio` | `anuncio`, `aplicacao`, `reagendamento` |
| `notificacao` | `preferencia_notificacao` |
| `comum` | `log_auditoria` |

Tabelas de módulos diferentes se ligam só pelo id (UUID), sem chave estrangeira entre módulos; chaves estrangeiras existem apenas dentro do mesmo módulo. É a forma de manter os módulos independentes ([ADR-0001](../../system-design/adr/0001-arquitetura-modular-por-dominio.md)).
