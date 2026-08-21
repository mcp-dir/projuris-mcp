---
name: projuris-mcp
description: Skill da REST API do Projuris ADV na MCP.AI: 32 endpoints em /api/projuris. Wrapper da API REST oficial do Projuris ADV (gestão jurídica): processos, pessoas (clientes/partes), tarefas (prazos/compromissos), andamentos, apontamento de horas (timesheet), arquivos (GED), contratos de honorários, assuntos, intimações, atendimentos, financeiro (receitas/despesas) e usuários. Leitura, busca e criação/edição via REST. Autenticação com client_id/secret fornecidos pelo suporte ao contratar a API (planos Premium) + usuário e senha do Projuris ADV. Tools genéricas cobrem os 757 recursos da API. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Projuris ADV — REST API skill

Você tem acesso à **Projuris ADV** REST API na MCP.AI.

> Wrapper da API REST oficial do Projuris ADV (gestão jurídica): processos, pessoas (clientes/partes), tarefas (prazos/compromissos), andamentos, apontamento de horas (timesheet), arquivos (GED), contratos de honorários, assuntos, intimações, atendimentos, financeiro (receitas/despesas) e usuários. Leitura, busca e criação/edição via REST. Autenticação com client_id/secret fornecidos pelo suporte ao contratar a API (planos Premium) + usuário e senha do Projuris ADV. Tools genéricas cobrem os 757 recursos da API.

## Base URL

```
https://api.mcp.ai/api/projuris
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/projuris/consulta \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"recurso":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/projuris/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (32)

#### `projuris_consulta`

Busca genérica: POST /<recurso>/consulta com `filtro` (corpo). _(POST /api/projuris/consulta)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `recurso` | string | Sim | Recurso REST (kebab-case), ex.: processo, pessoa, intimacao. |
| `filtro` | object | Não | Critérios de busca (corpo). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_andamento`

Busca Andamentos/movimentações do processo por filtro (POST /andamento/consulta-geral). _(POST /api/projuris/consulta/andamento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_apontamento_horas`

Busca Apontamento de horas (timesheet) por filtro (POST /apontamento-horas/consulta). _(POST /api/projuris/consulta/apontamento/horas)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_assunto`

Busca Assuntos/matérias por filtro (POST /assunto/consulta). _(POST /api/projuris/consulta/assunto)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_atendimento`

Busca Atendimentos (CRM/relacionamento) por filtro (POST /atendimento/consulta). _(POST /api/projuris/consulta/atendimento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_contrato`

Busca Contratos (honorários) por filtro (POST /contrato/consulta). _(POST /api/projuris/consulta/contrato)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_intimacao`

Busca Intimações/publicações por filtro (POST /intimacao/consulta). _(POST /api/projuris/consulta/intimacao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_pessoa`

Busca Pessoas (clientes, partes, advogados, contatos) por filtro (POST /pessoa/consulta). _(POST /api/projuris/consulta/pessoa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_processo`

Busca Processos/casos (judicial e extrajudicial) por filtro (POST /processo/consulta). _(POST /api/projuris/consulta/processo)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_receita_despesa`

Busca Financeiro: receitas e despesas por filtro (POST /receita-despesa/consulta). _(POST /api/projuris/consulta/receita/despesa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_tarefa`

Busca Tarefas (compromissos, prazos, providências) por filtro (POST /tarefa/consulta-com-paginacao). _(POST /api/projuris/consulta/tarefa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_consulta_usuario`

Busca Usuários do escritório por filtro (POST /usuario/consulta). _(POST /api/projuris/consulta/usuario)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `filtro` | object | Não | Critérios de busca (corpo da consulta). |
| `pagina` | integer | Não |  |
| `quantidade_registros` | integer | Não |  |

#### `projuris_create_andamento`

Cria um(a) Andamentos/movimentações do processo (POST /andamento). _(POST /api/projuris/create/andamento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade andamento. |

#### `projuris_create_apontamento_horas`

Cria um(a) Apontamento de horas (timesheet) (POST /apontamento-horas). _(POST /api/projuris/create/apontamento/horas)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade apontamento-horas. |

#### `projuris_create_atendimento`

Cria um(a) Atendimentos (CRM/relacionamento) (POST /atendimento). _(POST /api/projuris/create/atendimento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade atendimento. |

#### `projuris_create_pessoa`

Cria um(a) Pessoas (clientes, partes, advogados, contatos) (POST /pessoa). _(POST /api/projuris/create/pessoa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade pessoa. |

#### `projuris_create_tarefa`

Cria um(a) Tarefas (compromissos, prazos, providências) (POST /tarefa). _(POST /api/projuris/create/tarefa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade tarefa. |

#### `projuris_create_webhook`

Cria um(a) Webhooks de integração (POST /webhook). _(POST /api/projuris/create/webhook)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da entidade webhook. |

#### `projuris_get`

GET genérico em qualquer recurso REST do Projuris ADV. _(POST /api/projuris/get)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `path` | string | Sim | Caminho relativo a /adv-service (começa com /). |
| `query` | object | Não | Query params. |

#### `projuris_get_apontamento_horas`

Busca um(a) Apontamento de horas (timesheet) por código (GET /apontamento-horas/{codigo}). _(POST /api/projuris/get/apontamento/horas)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em apontamento-horas. |
| `query` | object | Não |  |

#### `projuris_get_arquivo`

Busca um(a) Arquivos/documentos (GED). _(POST /api/projuris/get/arquivo)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em arquivo. |
| `query` | object | Não |  |

#### `projuris_get_assunto`

Busca um(a) Assuntos/matérias por código (GET /assunto/{codigo}). _(POST /api/projuris/get/assunto)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em assunto. |
| `query` | object | Não |  |

#### `projuris_get_atendimento`

Busca um(a) Atendimentos (CRM/relacionamento) por código (GET /atendimento/{codigo}). _(POST /api/projuris/get/atendimento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em atendimento. |
| `query` | object | Não |  |

#### `projuris_get_intimacao`

Busca um(a) Intimações/publicações por código (GET /intimacao/{codigo}). _(POST /api/projuris/get/intimacao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em intimacao. |
| `query` | object | Não |  |

#### `projuris_get_pessoa`

Busca um(a) Pessoas (clientes, partes, advogados, contatos) por código (GET /pessoa/{codigo}). _(POST /api/projuris/get/pessoa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em pessoa. |
| `query` | object | Não |  |

#### `projuris_get_processo`

Busca um(a) Processos/casos (judicial e extrajudicial) por código (GET /processo/{codigo}). _(POST /api/projuris/get/processo)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em processo. |
| `query` | object | Não |  |

#### `projuris_get_receita_despesa`

Busca um(a) Financeiro: receitas e despesas por código (GET /receita-despesa/{codigo}). _(POST /api/projuris/get/receita/despesa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em receita-despesa. |
| `query` | object | Não |  |

#### `projuris_get_usuario`

Busca um(a) Usuários do escritório por código (GET /usuario/{codigo}). _(POST /api/projuris/get/usuario)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `codigo` | string | Sim | Código do recurso em usuario. |
| `query` | object | Não |  |

#### `projuris_list_webhook`

Lista Webhooks de integração (GET /webhook). _(POST /api/projuris/list/webhook)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `pagina` | integer | Não | Página (0-based). |
| `quantidade_registros` | integer | Não | Itens por página (máx 200). |
| `query` | object | Não | Query params extras conforme a API oficial. |

#### `projuris_request`

Escape hatch: chamada REST crua à API Projuris ADV. _(POST /api/projuris/request)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `method` | string | Sim | Método HTTP. (GET, POST, PUT, DELETE, PATCH) |
| `path` | string | Sim | Caminho relativo a /adv-service (começa com /). |
| `query` | object | Não | Query params. |
| `body` | object | Não | Corpo JSON (POST/PUT/PATCH). |

#### `projuris_update_apontamento_horas`

Atualiza um(a) Apontamento de horas (timesheet) (PUT /apontamento-horas). _(POST /api/projuris/update/apontamento/horas)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da atualização (inclua o código do registro em apontamento-horas). |

#### `projuris_update_pessoa`

Atualiza um(a) Pessoas (clientes, partes, advogados, contatos) (PUT /pessoa). _(POST /api/projuris/update/pessoa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | object | Sim | Corpo da atualização (inclua o código do registro em pessoa). |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_projuris` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
