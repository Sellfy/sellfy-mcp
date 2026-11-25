<p align="center"><img src="assets/sellfy-logo-400.png" width="96" alt="Sellfy"></p>

# Sellfy MCP Server

Run your Sellfy store from the AI assistant you already use. Describe what you want, and the assistant does it in Sellfy: list a product, set up a discount, check what sold, draft an email. Nothing goes live until you say so.

- **Server URL:** `https://api.sellfy.com/mcp`
- **Transport:** streamable HTTP
- **Sign-in:** OAuth in your browser. No API keys, nothing to register first.
- **Plans:** every Sellfy plan, including the 14-day free trial.

This repository holds the setup guide, registry metadata and logo. The server itself is hosted by Sellfy, so there is nothing to install or run.

More: [sellfy.com/mcp](https://sellfy.com/mcp/?utm_source=github&utm_medium=mcp-directory) · [Tool reference](https://api.sellfy.com/#tag/mcp-server) · [Agent setup guide](https://api.sellfy.com/agent-setup.md)

## Connect

| App | How |
|---|---|
| **Claude** | One click from the [Claude directory](https://claude.ai/directory/sellfy-mcp), or Settings → Connectors → Add custom connector → paste the URL. Then switch Sellfy on in the chat (+ → Connectors). |
| **ChatGPT** | Open Sellfy in the [ChatGPT app directory](https://chatgpt.com/plugins/plugin_asdk_app_6ad8ab3e0df48191bbc8842243876037), connect it, then sign in to Sellfy and click Allow. Or add it by hand: chatgpt.com/plugins → + → Add custom MCP server → name it Sellfy → paste the URL → sign in. Then type `@` in a chat and pick Sellfy. |
| **Claude Code** | `claude mcp add --transport http sellfy https://api.sellfy.com/mcp`, then `/mcp` → Authenticate. |
| **Cursor** | Add to `~/.cursor/mcp.json`: `{ "mcpServers": { "sellfy": { "url": "https://api.sellfy.com/mcp" } } }`, then click "Needs login". |
| **VS Code** | `code --add-mcp '{"name":"sellfy","type":"http","url":"https://api.sellfy.com/mcp"}'` |
| **Codex CLI** | `codex mcp add sellfy --url https://api.sellfy.com/mcp`, then `codex mcp login sellfy`. |
| **Gemini CLI** | `gemini extensions install https://github.com/Sellfy/sellfy-mcp`, or `gemini mcp add --transport http --scope user sellfy https://api.sellfy.com/mcp`, then `/mcp auth sellfy`. |
| **Perplexity, Lovable, Replit, Le Chat** | Add a custom MCP connector with the URL above and OAuth. Step-by-step: [sellfy.com/mcp](https://sellfy.com/mcp/#connect). |

In company workspaces an admin may need to allow custom connectors first.

## What you can ask it to do

- "Add a new digital product called Golden Hour Presets at $24, attach the ZIP I gave you, write a description in the style of my other products, and leave it unpublished."
- "Make a 25% off code GOLDENHOUR that works on everything until Sunday night."
- "How did last month compare to the month before, and which product made the most?"
- "Which of my products have no image or no description?"
- "Set up Black Friday: 30% off everything from the 27th to the 1st, swap the homepage banner in a draft, and draft the announcement email."

It covers products (digital, physical, subscription, print-on-demand), files, variants, media, license keys, discounts, orders, customers, reviews, sales stats, email campaigns, storefront pages and shipping profiles.

## What it won't do

- **It can't email your buyers.** Campaigns stay drafts; you send them from the Sellfy dashboard. Test emails go only to you.
- **It doesn't publish on its own.** New products start unpublished, and storefront edits go into a draft you preview first.
- **It can't delete products or discounts, and it can't refund or move money.**
- **It can't overwrite a change made at the same time.** Storefront edits are checked against the latest version.
- **You stay in control.** Disconnect any time; changing your Sellfy password ends every connection.

## Data and limits

Read tools can return orders, customers and reviews, including buyer names and email addresses. What a tool returns goes to the AI provider you connected, under their terms. Sellfy's own data handling: [sellfy.com/privacy](https://sellfy.com/privacy/).

Two OAuth scopes: `mcp:read` and `mcp:write`. Sessions expire after 30 days unused or 180 days total. Rate limit: 120 requests per minute across all connected clients.

[![M8ven Score](https://m8ven.ai/badge/mcp/sellfy-sellfy-mcp-1886mo?v=b63613fdcedeb46620a45bb841cfe580)](https://m8ven.ai/mcp/sellfy-sellfy-mcp-1886mo?s=readme)

## Support

[Sellfy Help Center](https://docs.sellfy.com/) · [Terms](https://sellfy.com/terms/) · [Privacy](https://sellfy.com/privacy/)
