# LinkDeal MCP Server

Find B2B leads from LinkedIn post engagement, enrich contact details, and deliver to Slack -- all through natural language with any MCP-compatible AI agent.

## What it does

LinkDeal surfaces people actively reacting to LinkedIn posts at target companies or around keywords. Your AI agent can:

- Find leads by company domain or keyword
- Search semantically by ICP description
- Enrich leads with business email and phone
- Unlock recent posts and top commenters for outreach context
- Send leads directly to Slack
- Manage searches, saved searches and billing

## Quickstart

1. Sign up at [app.linkdeal.ai](https://app.linkdeal.ai) and go to Settings to generate an API key
2. Add the config below to your AI client
3. Ask your agent to find leads in natural language

## Configuration

### Claude Desktop

```json
{
  "mcpServers": {
    "linkdeal": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://app.linkdeal.ai/api/mcp",
        "--header",
        "Authorization: Bearer YOUR_API_KEY"
      ]
    }
  }
}
```

### Cursor / Codex

```json
{
  "mcpServers": {
    "linkdeal": {
      "url": "https://app.linkdeal.ai/api/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

Replace YOUR_API_KEY with the key from Settings. Keys start with ld_

## Available Tools (18)

| Tool | Description |
|------|-------------|
| find_leads_by_company | Find leads who reacted to posts at a company domain |
| find_leads_by_keyword | Find leads reacting to posts about a keyword this week |
| find_leads_by_natural_language | Semantic ICP search -- describe your ideal customer |
| enrich_lead | Unlock business email and phone for a lead |
| get_lead_recent_posts | Get a lead's own recent posts sorted by engagement |
| enrich_lead_comments | Unlock top commenters on the post a lead reacted to |
| send_leads_to_slack | Send specific leads to your Slack channel |
| send_all_leads_to_slack | Send all leads from a search to Slack |
| setup_slack_webhook | Save a Slack webhook URL to your account |
| disconnect_slack_webhook | Remove the saved Slack webhook |
| get_search_history | Retrieve past searches with filters |
| save_search | Save search parameters for quick reuse |
| get_credits | Check current credit balance and subscription status |
| top_up_credits | Top up credits using your saved payment method |
| get_billing_info | Get full subscription and pricing details |
| get_subscription_plans | Get all available plans and trial details |
| cancel_subscription | Cancel subscription at end of current period |
| reactivate_subscription | Undo a cancellation |

## Pricing

Plans start at £19/month with a 5-day free trial and 50 credits included.

| Action | Credits |
|--------|---------|
| Pipeline search | 5 per post scanned |
| ICP semantic search | 5 flat |
| Contact enrichment | 15 per lead |
| Recent posts unlock | 5 per lead |
| Comment unlock | 10 per lead |

## Technical Details

- MCP URL: https://app.linkdeal.ai/api/mcp
- Transport: HTTP with Server-Sent Events (SSE), stateless
- Auth: Bearer token via Authorization header
- SDK: @modelcontextprotocol/sdk v1.29.0

## Example Prompts

"Find me 10 leads at hubspot.com who reacted to LinkedIn posts this week"

"Search for VP of Sales at B2B SaaS companies in the UK using Salesforce"

"Enrich the top 5 leads from my last search and send them to Slack"

## Links

- Website: https://linkdeal.ai
- App: https://app.linkdeal.ai
- MCP docs: https://linkdeal.ai/mcp
