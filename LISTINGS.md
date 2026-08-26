# Directory listings — Questa Privacy MCP

Public repo: https://github.com/questa-ai-org/questa_mcp  
MCP URL: https://api.questa-ai.com/mcp  
Registry name: `com.questa-ai/questa`

| Wave | Directory | Submit URL | Cost | Status | Notes |
|------|-----------|------------|------|--------|-------|
| A | Official MCP Registry | `mcp-publisher publish` | Free | Blocked — need DNS / `.well-known` | `server.json` validates. Run login+publish after TXT on `questa-ai.com` |
| A | Glama | Auto-index then claim | Free | Pending ingest | No `questa-ai-org/questa_mcp` listing yet. Claim after crawl |
| A | Smithery | https://smithery.ai/new | Free | Needs publisher login | Sign-in wall (email / Google / GitHub) |
| A | MCP Market | https://mcpmarket.com/submit | Free queue | Submitted 2026-08-26 | Confirmation: Success. Email `techsupport@questa.solutions`. Pay $29 if queue is too slow |
| A | mcp.so | https://mcp.so | Free / $39 | Pending claim | No listing yet. Claim after crawl |
| A | Cline Marketplace | https://github.com/cline/mcp-marketplace | Free | Submitted | https://github.com/cline/mcp-marketplace/issues/2329 |
| B | Claude Connectors | https://claude.ai/admin-settings/directory/submissions/new | Team plan | Needs Claude Team org | Press Publish after approval |
| B | ChatGPT Plugin / Apps | ChatGPT Plugins | — | After Connect works on prod | Developer Mode first |
| B | Cursor Marketplace | https://cursor.com/marketplace/publish | Free | Needs Cursor publisher login | This repo is the plugin source |
| B | VS Code / GitHub MCP Registry | Official registry | Free | Follows official publish | Extensions `@mcp` |
| B | Docker MCP Catalog | https://github.com/docker/mcp-registry | Free | PR opened | https://github.com/docker/mcp-registry/pull/4788 |
| C | PulseMCP | Ingest / hello@pulsemcp.com | Free | Pending ingest | Email if missing 7 days after registry publish |
| C | mcpservers.org | https://mcpservers.org/submit | Free | Submitted 2026-08-26 | Confirmation: review within 12 hours. Email `techsupport@questa.solutions` |
| C | MCPFind | https://mcpfind.org/submit | Free | Needs submit | Submit page timed out from this session |
| C | awesome-mcp-servers | https://github.com/punkpeye/awesome-mcp-servers | Free | PR opened | https://github.com/punkpeye/awesome-mcp-servers/pull/12917 |
| C | mcp.directory | https://mcp.directory/submit | Free | Pending ingest | hello@mcp.directory to claim |
| C | ClaudePluginHub | Submit repo URL | Free | Pending | |
| — | MCPize | — | Skip | Skipped | Would re-host PII |
| — | LobeHub | — | Skip | Skipped | Over-broad GitHub OAuth |
| — | Blackbox MCP | — | — | Do not list | Separate product |

## Official registry — commands after DNS

```bash
# Add TXT on questa-ai.com:
# questa-ai.com. IN TXT "v=MCPv1; k=ed25519; p=PUBLIC_KEY"

cd /Users/manish/Documents/Work/Questa/questa-privacy-mcp
mcp-publisher login dns --domain questa-ai.com --private-key <HEX>
mcp-publisher publish
curl "https://registry.modelcontextprotocol.io/v0.1/servers?search=com.questa-ai/questa"
```

Or host `https://questa-ai.com/.well-known/mcp-registry-auth` and use `mcp-publisher login http`.

## Owner actions still required

1. DNS TXT on `questa-ai.com` (or `.well-known/mcp-registry-auth`), then `mcp-publisher publish`.
2. Sign in and publish on Smithery, Claude Connectors, Cursor Marketplace, ChatGPT.
3. Claim Glama / mcp.so / PulseMCP after they ingest.
4. Reviewer SaaS account + `qmc_*` key on production.
