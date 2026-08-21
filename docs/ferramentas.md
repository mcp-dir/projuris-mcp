# Ferramentas

Projuris ADV expõe 32 ferramentas.

### 1. `projuris_request`
**Input**: `method`, `path`, `query` (opcional), `body` (opcional)

Escape hatch: chamada REST crua à API Projuris ADV.

### 2. `projuris_get`
**Input**: `path`, `query` (opcional)

GET genérico em qualquer recurso REST do Projuris ADV.

### 3. `projuris_consulta`
**Input**: `recurso`, `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca genérica: POST /<recurso>/consulta com `filtro` (corpo).

### 4. `projuris_consulta_processo`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Processos/casos (judicial e extrajudicial) por filtro (POST /processo/consulta).

### 5. `projuris_get_processo`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Processos/casos (judicial e extrajudicial) por código (GET /processo/{codigo}).

### 6. `projuris_consulta_pessoa`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Pessoas (clientes, partes, advogados, contatos) por filtro (POST /pessoa/consulta).

### 7. `projuris_get_pessoa`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Pessoas (clientes, partes, advogados, contatos) por código (GET /pessoa/{codigo}).

### 8. `projuris_create_pessoa`
**Input**: `data`

Cria um(a) Pessoas (clientes, partes, advogados, contatos) (POST /pessoa).

### 9. `projuris_update_pessoa`
**Input**: `data`

Atualiza um(a) Pessoas (clientes, partes, advogados, contatos) (PUT /pessoa).

### 10. `projuris_consulta_tarefa`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Tarefas (compromissos, prazos, providências) por filtro (POST /tarefa/consulta-com-paginacao).

### 11. `projuris_create_tarefa`
**Input**: `data`

Cria um(a) Tarefas (compromissos, prazos, providências) (POST /tarefa).

### 12. `projuris_consulta_andamento`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Andamentos/movimentações do processo por filtro (POST /andamento/consulta-geral).

### 13. `projuris_create_andamento`
**Input**: `data`

Cria um(a) Andamentos/movimentações do processo (POST /andamento).

### 14. `projuris_consulta_apontamento_horas`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Apontamento de horas (timesheet) por filtro (POST /apontamento-horas/consulta).

### 15. `projuris_get_apontamento_horas`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Apontamento de horas (timesheet) por código (GET /apontamento-horas/{codigo}).

### 16. `projuris_create_apontamento_horas`
**Input**: `data`

Cria um(a) Apontamento de horas (timesheet) (POST /apontamento-horas).

### 17. `projuris_update_apontamento_horas`
**Input**: `data`

Atualiza um(a) Apontamento de horas (timesheet) (PUT /apontamento-horas).

### 18. `projuris_get_arquivo`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Arquivos/documentos (GED).

### 19. `projuris_consulta_contrato`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Contratos (honorários) por filtro (POST /contrato/consulta).

### 20. `projuris_consulta_assunto`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Assuntos/matérias por filtro (POST /assunto/consulta).

### 21. `projuris_get_assunto`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Assuntos/matérias por código (GET /assunto/{codigo}).

### 22. `projuris_consulta_intimacao`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Intimações/publicações por filtro (POST /intimacao/consulta).

### 23. `projuris_get_intimacao`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Intimações/publicações por código (GET /intimacao/{codigo}).

### 24. `projuris_consulta_atendimento`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Atendimentos (CRM/relacionamento) por filtro (POST /atendimento/consulta).

### 25. `projuris_get_atendimento`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Atendimentos (CRM/relacionamento) por código (GET /atendimento/{codigo}).

### 26. `projuris_create_atendimento`
**Input**: `data`

Cria um(a) Atendimentos (CRM/relacionamento) (POST /atendimento).

### 27. `projuris_consulta_receita_despesa`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Financeiro: receitas e despesas por filtro (POST /receita-despesa/consulta).

### 28. `projuris_get_receita_despesa`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Financeiro: receitas e despesas por código (GET /receita-despesa/{codigo}).

### 29. `projuris_consulta_usuario`
**Input**: `filtro` (opcional), `pagina` (opcional), `quantidade_registros` (opcional)

Busca Usuários do escritório por filtro (POST /usuario/consulta).

### 30. `projuris_get_usuario`
**Input**: `codigo`, `query` (opcional)

Busca um(a) Usuários do escritório por código (GET /usuario/{codigo}).

### 31. `projuris_list_webhook`
**Input**: `pagina` (opcional), `quantidade_registros` (opcional), `query` (opcional)

Lista Webhooks de integração (GET /webhook).

### 32. `projuris_create_webhook`
**Input**: `data`

Cria um(a) Webhooks de integração (POST /webhook).

## Prompts de exemplo

```
Busque no Projuris os processos com andamento nos últimos 7 dias
Encontre a pessoa (cliente) X no Projuris e mostre os processos vinculados
Crie um apontamento de horas no Projuris vinculado ao processo Y
```
