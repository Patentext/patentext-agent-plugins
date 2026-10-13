# Patentext

Connect your agent to the Patentext strategy agent to read and continue your organization's patent strategy conversation.

## Package contents

- `plugin.json`: portable plugin metadata used by Codex.
- `mcp.json`: portable MCP connection configuration.
- `.claude-plugin/plugin.json`: Claude Code plugin metadata.
- `.mcp.json`: Claude Code MCP connection configuration.
- `skills/strategy/SKILL.md`: shared instructions for strategy conversations.
- `assets/`: plugin branding assets.

## Connection setup

The MCP server maps are intentionally empty until the production endpoint and authentication configuration are confirmed.

Add a `patentext` entry under `mcpServers` in both MCP files. The portable format uses `type: "streamable-http"`; Claude Code uses `type: "http"`. Point both at the same hosted Patentext MCP endpoint.

Configure OAuth for each supported client and document the tested sign-in flow. Users authenticate with their own Patentext accounts; do not include access tokens or client secrets in the package.

## To expand

- Supported clients and installation steps.
- Sign-in and organization selection.
- Example strategy prompts.
- Troubleshooting and support links.
