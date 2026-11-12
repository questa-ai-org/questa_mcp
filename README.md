# Questa Privacy MCP

**Anonymize and redact PII before it reaches AI models. GDPR, HIPAA, EU AI Act.**

Privacy-first [Model Context Protocol](https://modelcontextprotocol.io/) server for anonymization and redaction of personal and sensitive data before agents or models see it. Streamable HTTP at `https://api.questa-ai.com/mcp`. Authenticate with OAuth 2.1 or a revocable `qmc_*` connector key. Entity maps stay on Questa infrastructure. Works with Claude, Cursor, Cline, VS Code, and ChatGPT custom connectors.

- **Remote URL:** `https://api.questa-ai.com/mcp`
- **Transport:** Streamable HTTP
- **Homepage:** [questa-ai.com](https://www.questa-ai.com)
- **Privacy policy:** [questa-ai.com/privacy](https://www.questa-ai.com/privacy)
- **Registry name:** `com.questa-ai/questa`

This repository is the public listing and install surface. The hosted runtime is Questa SaaS — not the Blackbox product.

## Tools

| Tool | Purpose |
|------|---------|
| `anonymize_document` | Anonymize text or files under GDPR, HIPAA, EU AI Act, or a custom entity list. Returns placeholders plus `entity_map` / `map_id` for authorized reverse-mapping. |
| `redact_pii` | Inline redaction by entity type for contracts, emails, and transcripts. |
| `list_allowed_commands` | Commands and tools allowed for the current SaaS role. |

## Example

Input:

```text
Please review the MSA for Acme Corp. Contact Jane Doe at jane.doe@acme.com or +1 415-555-0199.
```

After `anonymize_document` (GDPR):

```text
Please review the MSA for [ORGANIZATION_1]. Contact [PERSON_NAME_1] at [EMAIL_1] or [PHONE_NUMBER_1].
```

The response includes `entity_map` and `map_id`. Keep those on your side if you need to restore originals later. Do not send the original document to the model.

## Install

Create a connector key (`qmc_*`) in Questa Platform → **Integrations → Questa MCP**, or complete browser OAuth when the client prompts.

### Cursor / Claude Desktop

```json
{
  "mcpServers": {
    "questa": {
      "url": "https://api.questa-ai.com/mcp",
      "headers": {
        "Authorization": "Bearer qmc_live_…"
      }
    }
  }
}
```

OAuth clients can omit `headers` and complete the consent flow instead.

### VS Code

Command Palette → **MCP: Add Server** → HTTP, then paste `https://api.questa-ai.com/mcp`. Or add the same JSON block to `.vscode/mcp.json`.

### Cline

Cline can install from this README or from [`llms-install.md`](./llms-install.md). Use the JSON block above.

### Claude.ai custom connector

Settings → Connectors → Add custom connector → paste `https://api.questa-ai.com/mcp` → complete OAuth, device code, or paste a `qmc_*` key.

### ChatGPT

Use ChatGPT on the web. Developer Mode is not needed.

1. Open [chatgpt.com/plugins](https://chatgpt.com/plugins) → plus (**+**) button → **Add custom MCP server**. Do not choose **Create plugin**.
2. Name `Questa`. Connection: **Server URL** → `https://api.questa-ai.com/mcp`.
3. Authentication: **OAuth** → tick **I understand and want to continue** → **Create as a plugin**.
4. Sign in to Questa when ChatGPT asks, and approve access.
5. Install the plugin, start a new chat, type `@` and select Questa.

OpenAI limits custom MCP servers by plan: Business, Enterprise and Edu workspaces can run every tool; Pro is documented as read-only tools.

## Auth

| Mode | How |
|------|-----|
| Browser OAuth | Client discovers `/.well-known/oauth-protected-resource` on `api.questa-ai.com` |
| Device code | Approve at the Questa device pairing page |
| Connector key | `Authorization: Bearer qmc_live_…` |

Unauthenticated `/mcp` returns `401` with `WWW-Authenticate` so clients can start OAuth.

## Pricing

Questa hosted API is a commercial SaaS product. Request an evaluation key from [questa-ai.com](https://www.questa-ai.com) or `techsupport@questa.solutions`. Self-hosting is available under a separate license.

## Privacy and compliance

- Anonymize **before** content reaches a vendor model.
- Entity maps (original PII) stay on Questa infrastructure, not in client config.
- Tool access follows the signed-in SaaS role (`tools.text`, `tools.file`).
- Positioning: privacy MCP, PII anonymization MCP, GDPR MCP, redaction MCP, HIPAA, EU AI Act.

## Directory listings

See [LISTINGS.md](./LISTINGS.md) for registry and marketplace status.

## License

This repository is documentation and install manifests for the hosted Questa Privacy MCP. The hosted service and anonymizer are proprietary. See [LICENSE](./LICENSE).
