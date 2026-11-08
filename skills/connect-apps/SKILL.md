---
name: connect-apps
description: Use when the user wants to read from or act in a connected app (Notion, Linear, Slack, Gmail, Google Drive) through this plugin's MCP servers, or asks which apps are connected.
---

# Connect apps

This plugin connects Claude Code to external apps through MCP servers listed in `.mcp.json`.

## How to work
1. Find the app's tools (named `mcp__<server>__*`). If they are missing, the server may need sign-in: tell the user to run `/mcp`.
2. Read before you write: look up IDs, pages or issues with search/list tools instead of guessing.
3. Before any write action (creating, updating, sending, deleting), state exactly what will change and get the user's confirmation.
4. Report results with links when the tool returns them.

## Adding a new app
Add an entry under `mcpServers` in `.mcp.json`:

```json
"app-name": { "type": "http", "url": "https://example.com/mcp" }
```

Then restart Claude Code and run `/mcp` to authenticate.
