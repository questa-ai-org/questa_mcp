# Install Questa Privacy MCP

Remote Streamable HTTP server. Do not run a local Node process.

## Server

- Name: questa
- Title: Questa Privacy MCP
- URL: https://api.questa-ai.com/mcp
- Transport: streamable-http
- Auth: OAuth 2.1 (browser or device code) or `Authorization: Bearer qmc_*`

## One-block config (Cursor, Claude Desktop, Cline, VS Code)

```json
{
  "mcpServers": {
    "questa": {
      "url": "https://api.questa-ai.com/mcp",
      "headers": {
        "Authorization": "Bearer qmc_live_YOUR_KEY"
      }
    }
  }
}
```

Replace `qmc_live_YOUR_KEY` with a connector key from Questa Platform → Integrations → Questa MCP.

If the client supports MCP OAuth, omit `headers` and complete the consent flow when prompted.

## After install

1. Call `list_allowed_commands` to confirm the session.
2. Call `anonymize_document` with sample text and `regime: "GDPR"` before sending any document to a model.
3. Keep `map_id` / `entity_map` if the user needs reverse-mapping later.

## Do not

- Do not clone this repo and run a local stdio server. There is no local package to start.
- Do not use test hosts (`test-api.questa-ai.com`) in public client config.
- Do not list or call tools that are not on the live server.
