<p align="center"><img src="assets/logo.svg" width="96" alt="Rivus logo"></p>

# Rivus MCP plugin

Connects AI coding agents to the hosted [Rivus](https://rivus.global) MCP server (`https://mcp.rivus.global/mcp/`): alpha research, ML research, strategy backtests and paper trading. Works with Claude Code, Codex, Cursor, Gemini CLI, VS Code, Windsurf and Claude Desktop. No API keys are stored here; each client signs in to Rivus through OAuth.

## Install

**Claude Code**
```
/plugin marketplace add rivusglobal/rivus-mcp-plugin
/plugin install rivus@rivus
```
Then `/mcp` → `rivus` to log in. Without the plugin: `claude mcp add --transport http rivus https://mcp.rivus.global/mcp/`

**Codex**: install this repo as a plugin, or add to `~/.codex/config.toml`:
```toml
[mcp_servers.rivus]
url = "https://mcp.rivus.global/mcp/"
```
then `codex mcp login rivus`.

**Cursor**: install as a plugin, or add to `.cursor/mcp.json`:
```json
{ "mcpServers": { "rivus": { "url": "https://mcp.rivus.global/mcp/" } } }
```

**Gemini CLI**: `gemini extensions install https://github.com/rivusglobal/rivus-mcp-plugin`

**VS Code** (`.vscode/mcp.json`):
```json
{ "servers": { "rivus": { "type": "http", "url": "https://mcp.rivus.global/mcp/" } } }
```

**Windsurf** (`~/.codeium/windsurf/mcp_config.json`):
```json
{ "mcpServers": { "rivus": { "serverUrl": "https://mcp.rivus.global/mcp/" } } }
```

**Claude Desktop and other stdio-only clients**:
```json
{ "mcpServers": { "rivus": { "command": "npx", "args": ["-y", "mcp-remote", "https://mcp.rivus.global/mcp/"] } } }
```

## First calls

`auth_me` to confirm identity, then `get_agent_startup_guide` and `get_guide(topic="index")`.

Broker credentials and live order placement stay outside the MCP server.

## License

MIT
