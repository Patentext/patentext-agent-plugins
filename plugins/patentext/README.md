# Patentext

Connect your agent to the Patentext strategy agent to read and continue your organization's patent strategy conversation.

## Package contents

- `.codex-plugin/plugin.json`: OpenAI compatibility manifest, explicitly referencing the shared skill and MCP configuration.
- `.claude-plugin/plugin.json`: Claude Code plugin metadata.
- `.mcp.json`: shared remote MCP connection configuration for OpenAI clients and Claude Code.
- `mcp.json`: equivalent connection settings in the portable Agent Plugins MCP format.
- `skills/strategy/SKILL.md`: shared instructions for strategy conversations.
- `assets/`: plugin branding assets.

The package uses the supported OpenAI compatibility layout because the local Codex 0.162.0 loader discovered the strategy skill but reported no MCP servers with a root portable `plugin.json`. Using `.codex-plugin/plugin.json` with `mcpServers: "./.mcp.json"` restored server discovery. Keep the root portable manifest absent while this workaround is needed.

## Connection setup

The production endpoint is `https://server.patentext.com/mcp`, using Streamable HTTP and OAuth. Users authenticate with their own Patentext accounts; do not include access tokens or client secrets in the package.

Keep the endpoint synchronized in both MCP files. The portable format uses `type: "streamable-http"`; `.mcp.json` uses `type: "http"`. The server publishes OAuth discovery metadata for clients to initiate sign-in.

See the [installation and usage guide](../../README.md) for customer instructions. Plugin discovery has been checked with the local loader; a complete desktop sign-in and strategy-tool call still needs verification.
