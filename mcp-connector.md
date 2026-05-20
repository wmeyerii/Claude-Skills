# MCP Connector — Industrial Real Estate & Fund Management

Connect Claude to external tools for industrial real estate workflows.

## Key Integrations
| Tool | Purpose |
|------|---------|
| Airtable | Prospect tracking and deal pipeline |
| Notion | Deal documentation and knowledge base |
| Google Drive | File storage and financial models |
| Gmail | LP correspondence and vendor invoices |
| Google Calendar | Scheduling and deadline tracking |
| Slack | Team coordination and updates |
| DocuSign | Document execution |
| Make.com | Workflow automation |
| Supabase | Custom database applications |

## Setup Process
Add to `~/.claude/settings.json` under `mcpServers`:
```json
{
  "mcpServers": {
    "[tool-name]": {
      "command": "[command]",
      "args": ["[args]"],
      "env": {
        "API_KEY": "[your-api-key]"
      }
    }
  }
}
```
Restart Claude Code, then use `/use-mcp` to verify connection.

## Common Workflows

**Deal Pipeline:** Search prospects and update deal statuses in Airtable

**Document Management:** Locate and organize lease files and memos in Google Drive

**LP Communication:** Draft updates in Claude and send documents for DocuSign signature

**Deadline Tracking:** Monitor lease expirations in Airtable and schedule follow-ups in Google Calendar

## Troubleshooting
Most connection issues stem from configuration errors, authentication problems, or unrecognized tools — verify settings or run `/mcp-management`.
