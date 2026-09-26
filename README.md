<div align="center">

<img src="assets/logo.png" alt="PaperOffice AI" width="200">

**Document Operations for Companies and AI Agents**

300+ API/MCP tools · Remote MCP server · EU hosted

[![Website](https://img.shields.io/badge/Website-paperoffice.ai-00bcd4?style=for-the-badge&logo=globe&logoColor=white)](https://paperoffice.ai)
[![API Docs](https://img.shields.io/badge/API_Docs-Postman-ff6c37?style=for-the-badge&logo=postman&logoColor=white)](https://api.paperoffice.ai/latest/docs/postman)
[![MCP Server](https://img.shields.io/badge/MCP_Server-Live-8b5cf6?style=for-the-badge&logo=zap&logoColor=white)](https://paperoffice.ai/en/developer/mcp/)

</div>

---

## What is PaperOffice AI?

PaperOffice AI is the document operations layer for a company account: capture,
understand, approve and archive documents, and let AI agents do the same work
through one REST API and one MCP server. OCR, zero-shot extraction,
classification, e-signatures, knowledge graph, workflows and audit trails run in
PaperOffice's own EU data centers.

## Quick start

### MCP — connect your AI client

Paste the URL for your client. Claude, ChatGPT and Grok sign in with OAuth 2.1;
Cursor and headless clients send a PaperOffice **user or group token**
(`po_ut_` / `po_gt_`) from [app.paperoffice.ai](https://app.paperoffice.ai).
System keys (`po_sk_`) and publishable keys (`po_pk_`) are rejected by the MCP
server.

| Client | URL |
|--------|-----|
| Claude Desktop / Anthropic Directory | `https://mcp.paperoffice.ai/claude` |
| ChatGPT | `https://mcp.paperoffice.ai/chatgpt` |
| Cursor / Windsurf | `https://mcp.paperoffice.ai/cursor` |
| Grok | `https://mcp.paperoffice.ai/grok` |
| Headless DMS (canonical) | `https://mcp.paperoffice.ai/dms` |
| Everything, all modules | `https://mcp.paperoffice.ai/mcp-full` |

```json
{
  "mcpServers": {
    "paperoffice": {
      "url": "https://mcp.paperoffice.ai/cursor",
      "headers": { "Authorization": "Bearer po_ut_..." }
    }
  }
}
```

Every tool description starts with `READ-ONLY.`, `WRITES DATA.` or
`DESTRUCTIVE.`, so the model knows the effect before it calls.

> Ready-made configs for every client: [paperoffice-mcp-setup](https://github.com/paperoffice-ai/paperoffice-mcp-setup)

### Registry, marketplaces and skills

| Where | What |
|-------|------|
| [Official MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=paperoffice) | `io.github.paperoffice-ai/paperoffice-mcp` — clients that read the registry find PaperOffice by name |
| Cursor Marketplace | [paperoffice-cursor-plugin](https://github.com/paperoffice-ai/paperoffice-cursor-plugin) — MCP + five Agent Skills |
| xAI Plugin Marketplace (Grok Build) | [paperoffice-grok-plugin](https://github.com/paperoffice-ai/paperoffice-grok-plugin) |
| Claude Code plugin / claude.ai skills | [paperoffice-skills](https://github.com/paperoffice-ai/paperoffice-skills) — how an agent should work with the API and the MCP tools |

### REST API — paste the docs into your AI

```text
https://api.paperoffice.ai/latest/docs/llms.txt
```

The guide is generated live from the API catalog. Tell your assistant what you
need and it writes the call:

```bash
curl -X POST https://api.paperoffice.ai/latest/job/add/paperoffice_aiocr___generate \
  -H "Authorization: Bearer $PAPEROFFICE_API_KEY" \
  -F "file=@invoice.pdf" \
  -F "ocr_mode=text"
```

## Developer resources

| Resource | Description |
|----------|-------------|
| [MCP documentation](https://paperoffice.ai/en/developer/mcp/) | Endpoints, auth, scopes |
| [llms.txt](https://api.paperoffice.ai/latest/docs/llms.txt) | Machine-readable API guide for agents |
| [Postman collection](https://api.paperoffice.ai/latest/docs/postman) | Live, generated from the catalog |
| [API examples](https://paperoffice.ai/en/developer/cookbook/) | Copy-paste prompts and recipes |
| [Cookbook repository](https://github.com/paperoffice-ai/cookbook) | 38 recipes in Python, Node and curl, 8 AI prompts, MCP setup guides |
| [Agent Skills](https://github.com/paperoffice-ai/paperoffice-skills) | Procedures for agents: integration, invoices, OCR, documents, tool discovery |
| [Get an API key](https://app.paperoffice.ai) | Free account |
| [Partner program](https://paperoffice.ai/en/partner/) | Reseller and integration partners |

## Platform highlights

- **Document AI** — OCR in 120+ languages, zero-shot IDP, classification, bounding boxes
- **Headless DMS** — search, read, upload, move, version, tag, sign; bring your own storage
- **Workflow AI** — tasks, human-in-the-loop approvals, webhooks, automation
- **Intelligence** — knowledge graph, entities, analytics
- **Compliance** — e-signatures, redaction, retention, audit trails, GoBD/GDPR

## Connect

- [paperoffice.ai](https://paperoffice.ai)
- [info@paperoffice.ai](mailto:info@paperoffice.ai)
- Own Tier III data centers in Spain and Germany · GDPR

---

<div align="center">
<sub>PaperOffice — document management since 2002</sub>
</div>
