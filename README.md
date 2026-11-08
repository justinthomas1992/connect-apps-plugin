# connect-apps-plugin

Claude Code plugin for connecting apps via MCP servers, skills and commands.

## Contents
| Path | Purpose |
|---|---|
| `.claude-plugin/plugin.json` | Plugin manifest |
| `.mcp.json` | App connections (MCP servers): Notion, Linear, Slack, Gmail, Google Drive |
| `commands/apps-status.md` | `/apps-status` – check which apps are connected |
| `skills/connect-apps/SKILL.md` | How Claude should use the connected apps safely |

## Try it locally
```bash
git clone https://github.com/justinthomas1992/connect-apps-plugin
claude --plugin-dir ./connect-apps-plugin
```
Inside Claude Code: run `/mcp` to sign in to each app, then `/apps-status`.

## Add another app
Add an entry to `.mcp.json`:
```json
"app-name": { "type": "http", "url": "https://example.com/mcp" }
```

## License
MIT

## Sign-in notes
Each app signs in with OAuth the first time you run `/mcp`. Slack and the Google
servers (Gmail, Drive) may only accept pre-approved clients; if sign-in fails for
one of them, connect that app as a connector at claude.ai instead and remove its
entry from `.mcp.json`.
