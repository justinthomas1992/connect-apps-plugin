---
description: Show which connected apps (MCP servers) are available and working
---

List the MCP servers provided by the connect-apps-plugin and check each one:

1. For each server in this plugin's `.mcp.json`, say whether its tools are available in this session.
2. If a server needs sign-in, tell the user to run `/mcp` and authenticate it.
3. Finish with a short table: app, status (connected / needs auth / failed), and what it can do.
