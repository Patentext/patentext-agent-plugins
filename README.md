<img src="plugins/patentext/assets/icon.png" alt="Patentext" width="64" />

# Patentext Agent Plugins

Connect your AI agent to [Patentext](https://patentext.com) to build and continue your company's patent strategy.

The Patentext plugin lets your agent catch up on your strategy conversation, contribute information about your business, and answer the strategy agent's follow-up questions. It includes the connection to Patentext and a skill that guides your agent through the conversation.

You'll need a Patentext Lab account with access to your organization's strategy workspace, and a current version of Codex or Claude Code with plugin support.

## Install

Choose your agent below. The plugin connects to Patentext's hosted service; there is no server to run locally.

### Codex

Add the Patentext marketplace from your terminal:

```sh
codex plugin marketplace add Patentext/patentext-agent-plugins
```

Then install the plugin:

1. Open the plugin browser: enter `/plugins` in Codex CLI, or open **Plugins** in the desktop app.
2. Choose the **Patentext** marketplace and install **patentext**.
3. Start a new chat and follow the sign-in steps below.

See [OpenAI's plugin guide](https://learn.chatgpt.com/docs/plugins) for more about installing and managing plugins.

### Claude Code

Run these commands in your terminal:

```sh
claude plugin marketplace add Patentext/patentext-agent-plugins
claude plugin install patentext@patentext-agent-plugins
```

Start a new Claude Code session, then follow the sign-in steps below.

See [Claude Code's marketplace guide](https://code.claude.com/docs/en/plugin-marketplaces) for more about plugin installation.

## Connect your Patentext account

The plugin uses your Patentext sign-in. You do not need to create or paste an API key.

- **Codex:** follow the connection prompt when installing or first using Patentext.
- **Claude Code:** enter `/mcp`, select the Patentext server, and follow the authentication flow.

Complete the browser sign-in with the account you use for Patentext. If asked to choose an organization, select the one whose strategy you want to work on, then return to your agent.

To check the connection, ask: **"Use Patentext to show me the current state of our patent strategy."** Your agent should retrieve the strategy workspace or explain any remaining access issue.

## Try it

Once connected, ask your agent to use Patentext:

> Show me where we left off with our Patentext strategy.

> Help me continue our patent strategy interview in Patentext.

> Summarize our Patentext strategy conversation and the questions still outstanding.

When you ask your agent to contribute answers, those messages become part of your organization's strategy conversation in Patentext. Some strategy responses take a few minutes; your agent can check for the result while the strategy agent works.

## Other MCP-compatible agents

For an agent that supports remote MCP servers with OAuth, add a connection using:

| Setting | Value |
| --- | --- |
| Server URL | `https://server.patentext.com/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth using your Patentext account |

Follow your agent's instructions for adding a remote MCP server and completing sign-in. A direct connection provides the strategy tools; the plugin also includes the strategy skill.

## Help

- **The plugin is missing:** check that you added the Patentext marketplace, then reopen your agent's plugin browser.
- **Patentext tools are unavailable:** check that the plugin is installed and enabled, complete sign-in, and start a new chat.
- **You cannot access your organization:** confirm that you signed in with the same account you use in Patentext Lab and have access to the intended organization.
- **Sign-in has expired:** reconnect Patentext through your agent's connection settings. In Claude Code, use `/mcp` to re-authenticate.

For installation problems, [open an issue](https://github.com/Patentext/patentext-agent-plugins/issues) with your agent's name, version, and the error message. Keep credentials and confidential invention details out of public issues.
