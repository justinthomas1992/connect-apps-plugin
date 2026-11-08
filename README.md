# connect-apps-plugin

Claude Code plugin for connecting apps via MCP servers, skills and commands.

## Contents
| Path | Purpose |
|---|---|
| `.claude-plugin/plugin.json` | Plugin manifest |
| `.claude-plugin/marketplace.json` | Lets this repo be added as a plugin marketplace |
| `.mcp.json` | App connections (MCP servers): Notion, Linear, Slack, Gmail, Google Drive |
| `commands/apps-status.md` | `/apps-status` – check which apps are connected |
| `skills/connect-apps/SKILL.md` | How Claude should use the connected apps safely |

## Install

### From the marketplace (recommended)
Inside Claude Code:
```
/plugin marketplace add justinthomas1992/connect-apps-plugin
/plugin install connect-apps-plugin@connect-apps-plugin
```

### Locally, for development
```bash
git clone https://github.com/justinthomas1992/connect-apps-plugin
claude --plugin-dir ./connect-apps-plugin
```

Then, inside Claude Code: run `/mcp` to sign in to each app, then `/apps-status`.

## Sign-in notes
Each app signs in with OAuth the first time you run `/mcp`.

Slack and the Google servers (Gmail, Drive) may only accept pre-approved clients.
If sign-in fails for one of them, connect that app as a connector at
claude.ai (Settings → Connectors) instead, and remove its entry from `.mcp.json`
so `/mcp` stops reporting it as failed. The `connect-apps` skill and `/apps-status`
recognise apps connected either way.

## Add another app
Add an entry to `.mcp.json`, using the MCP URL from the app's own documentation:
```json
"app-name": { "type": "http", "url": "https://example.com/mcp" }
```
Then restart Claude Code, run `/mcp` to sign in, and add the app to the lists in
`skills/connect-apps/SKILL.md` and `commands/apps-status.md`.

## Releasing changes
Bump `version` in both `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`
whenever you change the plugin; installed copies only update when the version changes.

## License
MIT
