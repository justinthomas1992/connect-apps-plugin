---
name: connect-apps
description: Use when the user wants to read from or act in a connected app (Notion, Linear, Slack, Gmail, Google Drive) through this plugin's MCP servers, or asks which apps are connected.
---

# Connect apps

This plugin connects Claude Code to external apps through MCP servers listed in `.mcp.json`.

## Finding an app's tools
Tools from a plugin's MCP servers are prefixed with the plugin name:

```
mcp__plugin_connect-apps-plugin_<server>__<tool>
```

For example, Notion tools look like `mcp__plugin_connect-apps-plugin_notion__notion-search`.

The same app may also be connected as a claude.ai connector, whose tools look like
`mcp__<App_Name>__<tool>` (for example `mcp__Gmail__search_threads`). Either source is fine to use.

If a tool is listed only by name and not yet loaded, load it (for example with ToolSearch) before calling it.

## How to work
1. Find the app's tools as described above. If none are present, the server may need sign-in: tell the user to run `/mcp` and authenticate it.
2. Read before you write: look up IDs, pages or issues with search/list tools instead of guessing.
3. Before any write action (creating, updating, sending, deleting), state exactly what will change and get the user's confirmation.
4. Report results with links when the tool returns them.

## Adding a new app
Add an entry under `mcpServers` in `.mcp.json`:

```json
"app-name": { "type": "http", "url": "https://example.com/mcp" }
```

Then restart Claude Code and run `/mcp` to authenticate. Only add URLs from the app's own documentation.
