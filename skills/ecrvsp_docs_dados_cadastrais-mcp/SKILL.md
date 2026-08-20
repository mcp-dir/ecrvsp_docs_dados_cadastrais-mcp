---
name: ecrvsp_docs_dados_cadastrais-mcp
description: Skill da REST API do ECRVSP Documentos: Alteração de Dados Cadastrais na MCP.AI: 1 endpoint em /api/ecrvsp_docs_dados_cadastrais. ECRVSP Documentos: Alteração de Dados Cadastrais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# ECRVSP Documentos: Alteração de Dados Cadastrais — REST API skill

Você tem acesso à **ECRVSP Documentos: Alteração de Dados Cadastrais** REST API na MCP.AI.

> ECRVSP Documentos: Alteração de Dados Cadastrais, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/ecrvsp_docs_dados_cadastrais
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
curl -X POST https://api.mcp.ai/api/ecrvsp_docs_dados_cadastrais/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"a3":"...","a3_pin":"...","login_cpf":"...","login_senha":"...","categoria":"...","codigo_banco":"...","data_contabil":"...","nsu_prodesp":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/ecrvsp_docs_dados_cadastrais/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `ecrvsp_docs_dados_cadastrais_consultar`

ECRVSP Documentos: Alteração de Dados Cadastrais, consulta em fonte oficial. _(POST /api/ecrvsp_docs_dados_cadastrais/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `a3` | string | Sim | Parâmetro de consulta "a3". |
| `a3_pin` | string | Sim | Parâmetro de consulta "a3_pin". |
| `login_cpf` | string | Sim | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Sim | Parâmetro de consulta "login_senha". |
| `chassi` | string | Não | Parâmetro de consulta "chassi". |
| `placa` | string | Não | Parâmetro de consulta "placa". |
| `categoria` | string | Sim | Parâmetro de consulta "categoria". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `codigo_banco` | string | Sim | Parâmetro de consulta "codigo_banco". |
| `data_contabil` | string | Sim | Parâmetro de consulta "data_contabil". |
| `nsu_prodesp` | string | Sim | Parâmetro de consulta "nsu_prodesp". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_ecrvsp_docs_dados_cadastrais` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
