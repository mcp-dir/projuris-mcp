# Projuris ADV

### Projuris ADV for Claude, ChatGPT and AI agents

Wrapper for the official Projuris ADV REST API (legal practice management): cases, people (clients/parties), tasks (deadlines/appointments), updates, timesheet, files (GED), fee contracts, subjects, court notices, service records, finance (income/expenses) and users. Read, search and create/update over REST. Authenticates with the client_id/secret provided by support when the API is contracted (Premium plans) plus your Projuris ADV username and password. Generic tools cover all 757 API resources.

- 📊 **32 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Projuris ADV`, URL `https://api.mcp.ai/p_projuris`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=projuris&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9wcm9qdXJpcyJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=projuris&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_projuris%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_projuris
```

---

## 32 tools

| Tool | Description |
|---|---|
| `projuris_request` | Escape hatch: chamada REST crua à API Projuris ADV. |
| `projuris_get` | GET genérico em qualquer recurso REST do Projuris ADV. |
| `projuris_consulta` | Busca genérica: POST /<recurso>/consulta com `filtro` (corpo). |
| `projuris_consulta_processo` | Busca Processos/casos (judicial e extrajudicial) por filtro (POST /processo/consulta). |
| `projuris_get_processo` | Busca um(a) Processos/casos (judicial e extrajudicial) por código (GET /processo/{codigo}). |
| `projuris_consulta_pessoa` | Busca Pessoas (clientes, partes, advogados, contatos) por filtro (POST /pessoa/consulta). |
| `projuris_get_pessoa` | Busca um(a) Pessoas (clientes, partes, advogados, contatos) por código (GET /pessoa/{codigo}). |
| `projuris_create_pessoa` | Cria um(a) Pessoas (clientes, partes, advogados, contatos) (POST /pessoa). |
| `projuris_update_pessoa` | Atualiza um(a) Pessoas (clientes, partes, advogados, contatos) (PUT /pessoa). |
| `projuris_consulta_tarefa` | Busca Tarefas (compromissos, prazos, providências) por filtro (POST /tarefa/consulta-com-paginacao). |
| `projuris_create_tarefa` | Cria um(a) Tarefas (compromissos, prazos, providências) (POST /tarefa). |
| `projuris_consulta_andamento` | Busca Andamentos/movimentações do processo por filtro (POST /andamento/consulta-geral). |
| `projuris_create_andamento` | Cria um(a) Andamentos/movimentações do processo (POST /andamento). |
| `projuris_consulta_apontamento_horas` | Busca Apontamento de horas (timesheet) por filtro (POST /apontamento-horas/consulta). |
| `projuris_get_apontamento_horas` | Busca um(a) Apontamento de horas (timesheet) por código (GET /apontamento-horas/{codigo}). |
| `projuris_create_apontamento_horas` | Cria um(a) Apontamento de horas (timesheet) (POST /apontamento-horas). |
| `projuris_update_apontamento_horas` | Atualiza um(a) Apontamento de horas (timesheet) (PUT /apontamento-horas). |
| `projuris_get_arquivo` | Busca um(a) Arquivos/documentos (GED). |
| `projuris_consulta_contrato` | Busca Contratos (honorários) por filtro (POST /contrato/consulta). |
| `projuris_consulta_assunto` | Busca Assuntos/matérias por filtro (POST /assunto/consulta). |
| `projuris_get_assunto` | Busca um(a) Assuntos/matérias por código (GET /assunto/{codigo}). |
| `projuris_consulta_intimacao` | Busca Intimações/publicações por filtro (POST /intimacao/consulta). |
| `projuris_get_intimacao` | Busca um(a) Intimações/publicações por código (GET /intimacao/{codigo}). |
| `projuris_consulta_atendimento` | Busca Atendimentos (CRM/relacionamento) por filtro (POST /atendimento/consulta). |
| `projuris_get_atendimento` | Busca um(a) Atendimentos (CRM/relacionamento) por código (GET /atendimento/{codigo}). |
| `projuris_create_atendimento` | Cria um(a) Atendimentos (CRM/relacionamento) (POST /atendimento). |
| `projuris_consulta_receita_despesa` | Busca Financeiro: receitas e despesas por filtro (POST /receita-despesa/consulta). |
| `projuris_get_receita_despesa` | Busca um(a) Financeiro: receitas e despesas por código (GET /receita-despesa/{codigo}). |
| `projuris_consulta_usuario` | Busca Usuários do escritório por filtro (POST /usuario/consulta). |
| `projuris_get_usuario` | Busca um(a) Usuários do escritório por código (GET /usuario/{codigo}). |
| `projuris_list_webhook` | Lista Webhooks de integração (GET /webhook). |
| `projuris_create_webhook` | Cria um(a) Webhooks de integração (POST /webhook). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_projuris` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
