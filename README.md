# connect-apps-plugin

Claude Code plugin for connecting apps via MCP servers, skills and commands.

## Contents
| Path | Purpose |
|---|---|
| `.claude-plugin/plugin.json` | Plugin manifest |
| `.mcp.json` | App connections (MCP servers): Notion, Linear to start |
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
