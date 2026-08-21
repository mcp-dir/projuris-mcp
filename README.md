# Projuris ADV

### Projuris ADV para Claude, ChatGPT e agentes de IA

Wrapper da API REST oficial do Projuris ADV (gestão jurídica): processos, pessoas (clientes/partes), tarefas (prazos/compromissos), andamentos, apontamento de horas (timesheet), arquivos (GED), contratos de honorários, assuntos, intimações, atendimentos, financeiro (receitas/despesas) e usuários. Leitura, busca e criação/edição via REST. Autenticação com client_id/secret fornecidos pelo suporte ao contratar a API (planos Premium) + usuário e senha do Projuris ADV. Tools genéricas cobrem os 757 recursos da API.

- 📊 **32 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Projuris ADV` e **URL** `https://api.mcp.ai/p_projuris`.

### Cursor

[➕ Instalar Projuris ADV no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=projuris&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9wcm9qdXJpcyJ9)

### VS Code (Copilot Chat)

[➕ Instalar Projuris ADV no VS Code](vscode:mcp/install?name=projuris&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_projuris%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_projuris
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Busque no Projuris os processos com andamento nos últimos 7 dias
Encontre a pessoa (cliente) X no Projuris e mostre os processos vinculados
Crie um apontamento de horas no Projuris vinculado ao processo Y
```

---

## 32 ferramentas disponíveis

| Tool | Descrição |
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

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_projuris`.


---

## Suporte

- 📧 [projuris@mcp.ai](mailto:projuris@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/projuris-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_projuris` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
