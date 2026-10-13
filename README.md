# Patentext Agent Plugins

Plugins that connect users' agents to Patentext workflows, starting with patent strategy.

This repository is an initial scaffold. The MCP server configurations are empty; installing the plugin does not yet connect it to Patentext.

## Repository layout

- `.agents/plugins/marketplace.json`: Codex marketplace catalog.
- `.claude-plugin/marketplace.json`: Claude Code marketplace catalog.
- `plugins/patentext/`: shared Patentext plugin, client manifests, MCP configuration, and skills.

Both marketplace catalogs point to `./plugins/patentext`.

## Complete the setup

- Configure the production MCP endpoint and OAuth settings in the plugin's MCP files.
- Expand the strategy skill and add branding assets.
- Add client-specific installation and sign-in instructions here.
- Verify a fresh installation, sign-in, and strategy conversation in each supported client.

Keep the plugin name and version aligned across both plugin manifests. Keep credentials out of this repository.

## Documentation

- [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins)
- [Claude Code plugin reference](https://code.claude.com/docs/en/plugins-reference)
- [Claude Code marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
