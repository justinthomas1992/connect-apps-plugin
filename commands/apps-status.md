---
description: Show which connected apps (MCP servers) are available and working
---

List the MCP servers provided by the connect-apps-plugin and check each one:

1. For each server in this plugin's `.mcp.json` (notion, linear, slack, gmail, google-drive), look for tools named `mcp__plugin_connect-apps-plugin_<server>__*`. Also note if the same app is available as a claude.ai connector (tools named like `mcp__Notion__*` or `mcp__Gmail__*`).
2. If a server has no tools, it most likely needs sign-in: tell the user to run `/mcp` and authenticate it. If `/mcp` shows it as failed, say so.
3. Finish with a short table: app, status (connected / connected via claude.ai / needs auth / failed), and what it can do.

Example output:

| App | Status | What it can do |
|---|---|---|
| Notion | connected | Search, read and edit pages and databases |
| Linear | needs auth | Run `/mcp` to sign in |
| Gmail | connected via claude.ai | Search, read and draft email |
