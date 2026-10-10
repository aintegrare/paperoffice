# Instalação — PaperOffice AI neste projeto

Este repositório não contém código de aplicação: é a página de apresentação da
PaperOffice AI. "Instalar" o projeto significa conectar o servidor MCP remoto
(Model Context Protocol) e as skills de agente ao seu cliente de IA. Os arquivos
abaixo fazem isso para quem abrir esta pasta no Claude Code.

## O que está configurado

| Arquivo | Função |
|---------|--------|
| `.mcp.json` | Servidor MCP `paperoffice` em `https://mcp.paperoffice.ai/claude` (HTTP, OAuth 2.1). Nenhuma chave fica no repositório. |
| `.claude/settings.json` | Registra o marketplace `paperoffice-ai/paperoffice-skills` e habilita o plugin `paperoffice-skills` (skills: integração de API, extração de faturas, OCR, documentos, descoberta de tools). |

## Passos na sua máquina

1. Crie uma conta gratuita em <https://app.paperoffice.ai> (necessária para o login OAuth).
2. Abra a pasta no Claude Code e execute `claude`. Aprove o servidor MCP de projeto
   quando solicitado; o navegador abre o login da PaperOffice.
3. Confirme com `claude mcp list` (status deve ser *Connected*) e `/plugin` para ver
   o plugin `paperoffice-skills` instalado.

## Alternativa sem OAuth (headless, CI, Cursor)

Gere um token de usuário (`po_ut_`) ou de grupo (`po_gt_`) em
*Account → API* no app e use o endpoint `/dms`:

```bash
claude mcp add --transport http --scope user paperoffice-dms \
  https://mcp.paperoffice.ai/dms \
  --header "Authorization: Bearer po_ut_..."
```

Chaves `po_sk_` e `po_pk_` são rejeitadas pelo servidor MCP.

## Outros clientes

Configurações prontas para Claude Desktop, ChatGPT, Cursor, Windsurf e Grok:
<https://github.com/paperoffice-ai/paperoffice-mcp-setup>.
