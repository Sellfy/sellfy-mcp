# Installing the Sellfy MCP server

This is a hosted (remote) MCP server. There is nothing to download, build or run, and no API key.

- URL: `https://api.sellfy.com/mcp`
- Transport: streamable HTTP
- Auth: OAuth. The user signs in to Sellfy in the browser and clicks Allow.

## Steps for an agent

1. Add a remote MCP server named `sellfy` with the URL above and HTTP (streamable) transport. Do not add headers or an API key.
2. Ask the user to complete the sign-in. A browser window opens on Sellfy; they log in, check the store name and click Allow. You cannot do this step for them.
3. Check the connection by calling `get_store_info`. It returns the store name and currency.
4. Report: `Sellfy connected: <store name> (<currency>)`.

If the user has no Sellfy account, they can start a 14-day free trial at https://sellfy.com/ (the server works during the trial).

Client-specific commands (Claude Code, Codex CLI, Cursor, VS Code, Gemini CLI): https://api.sellfy.com/agent-setup.md
