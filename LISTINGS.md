# Directory listings — Questa Privacy MCP

Public repo: https://github.com/questa-ai-org/questa_mcp  
MCP URL: https://api.questa-ai.com/mcp  
Registry name: `com.questa-ai/questa`

| Wave | Directory | Submit URL | Cost | Status | Notes |
|------|-----------|------------|------|--------|-------|
| A | Official MCP Registry | `mcp-publisher publish` | Free | Blocked — DNS / `.well-known` namespace proof | Publish `server.json` after TXT on `questa-ai.com` |
| A | Glama | Auto-index then claim | Free | Pending ingest | Claim after registry + this repo is public |
| A | Smithery | https://smithery.ai/new | Free | Needs publisher login | Remote URL + this GitHub repo |
| A | MCP Market | https://mcpmarket.com/submit | Free / $29 | Needs form + email | Pay $29 if free queue is weeks |
| A | mcp.so | https://mcp.so | Free / $39 | Needs claim | Pay $39 only if stub is wrong |
| A | Cline Marketplace | https://github.com/cline/mcp-marketplace | Free | Pending issue | Logo + this README / `llms-install.md` |
| B | Claude Connectors | https://claude.ai/admin-settings/directory/submissions/new | Team plan | Needs Claude Team org | Press Publish after approval |
| B | ChatGPT Plugin / Apps | ChatGPT Plugins | — | After Connect works on prod | Developer Mode first |
| B | Cursor Marketplace | https://cursor.com/marketplace/publish | Free | Needs Cursor publisher login | This repo is the plugin source |
| B | VS Code / GitHub MCP Registry | Official registry | Free | Follows Wave A | Extensions `@mcp` |
| B | Docker MCP Catalog | https://github.com/docker/mcp-registry | Free | Pending PR | Remote OAuth accepted |
| C | PulseMCP | Ingest / hello@pulsemcp.com | Free | Pending ingest | Email if missing after 7 days |
| C | mcpservers.org | https://mcpservers.org/submit | Free / $39 | Needs form | Skip $39 unless stuck |
| C | MCPFind | https://mcpfind.org/submit | Free | Needs submit | |
| C | awesome-mcp-servers | https://github.com/punkpeye/awesome-mcp-servers | Free | Pending PR | Security / Privacy section |
| C | mcp.directory | https://mcp.directory/submit | Free | Pending ingest | hello@mcp.directory to claim |
| C | ClaudePluginHub | Submit repo URL | Free | Pending | |
| — | MCPize | — | Skip | Skipped | Would re-host PII |
| — | LobeHub | — | Skip | Skipped | Over-broad GitHub OAuth |
| — | Blackbox MCP | — | — | Do not list | Separate product |

## Owner actions still required

1. Add DNS TXT on `questa-ai.com` (`v=MCPv1; k=ed25519; p=…`) or host `https://questa-ai.com/.well-known/mcp-registry-auth`.
2. Run `mcp-publisher login dns --domain questa-ai.com` then `mcp-publisher publish` from this repo.
3. Sign in and submit Smithery, MCP Market, mcp.so, Claude, Cursor, ChatGPT.
4. Confirm a reviewer SaaS account + `qmc_*` key on production.
