# Rivus MCP plugin for Claude Code

Registers the hosted [Rivus](https://rivus.global) MCP server (`https://mcp.rivus.global/mcp/`) in Claude Code.

## Install

```
/plugin marketplace add rivusglobal/rivus-mcp-plugin
/plugin install rivus@rivus
```

Then run `/mcp`, select `rivus`, and complete the OAuth login in your browser. No API keys are stored in this plugin.

## First calls

`auth_me` to confirm identity, then `get_agent_startup_guide` and `get_guide(topic="index")` for the research, strategy and execution workflows.

## Manual alternative

```
claude mcp add --transport http rivus https://mcp.rivus.global/mcp/
```

Broker credentials and live order placement stay outside the MCP server.

## License

MIT
