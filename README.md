<img src="plugins/patentext/assets/icon.png" alt="Patentext" width="64" />

# Patentext Agent Plugins

Connect your AI agent to [Patentext](https://patentext.com) to build your company's patent strategy, record and disclose inventions, and review patent drafts.

The Patentext plugin lets your agent do the following:

- See what's waiting on you in Patentext.
- Take part in the strategy interview and in invention disclosure interviews.
- Record inventions and add the documents that describe them.
- Read patent application drafts that your law firm shares for review, and reply to their comments.

The plugin includes the connection to Patentext and skills that guide your agent through each task.

You'll need a Patentext Lab account in your organization, and a current version of Codex or Claude Code with plugin support. Some tools depend on your Patentext plan: invention disclosures need Starter or Enterprise, and concept discovery needs Enterprise.

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

Complete the browser sign-in with the account you use for Patentext. If asked to choose an organization, select the one you want to work in, then return to your agent.

To check the connection, ask: **"What's waiting on me in Patentext?"** Your agent should show an overview of your Patentext work or explain any remaining access issue.

## Try it

Once connected, ask your agent to use Patentext:

> Show me where we left off with our Patentext strategy.

> Help me continue our patent strategy interview in Patentext.

> I built a new gripper controller. Record it in Patentext with our design doc and start its disclosure.

> Continue the disclosure interview for the gripper controller.

> Read the patent draft that's in review and summarize the open comments.

When your agent sends a message to the strategy agent or a disclosure agent, Patentext shows it in that conversation as sent by you through MCP. Some responses take a few minutes; your agent can check for the result while the Patentext agent works.

## Other MCP-compatible agents

For an agent that supports remote MCP servers with OAuth, add a connection using:

| Setting | Value |
| --- | --- |
| Server URL | `https://server.patentext.com/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth using your Patentext account |

Follow your agent's instructions for adding a remote MCP server and completing sign-in. A direct connection provides all the Patentext tools; the plugin also includes the skills.

## Help

- **The plugin is missing:** check that you added the Patentext marketplace, then reopen your agent's plugin browser.
- **Patentext tools are unavailable:** check that the plugin is installed and enabled, complete sign-in, and start a new chat.
- **You cannot access your organization:** confirm that you signed in with the same account you use in Patentext Lab and have access to the intended organization.
- **A tool reports `SubscriptionRequired`:** your organization's Patentext plan doesn't include that feature.
- **Sign-in has expired:** reconnect Patentext through your agent's connection settings. In Claude Code, use `/mcp` to re-authenticate.

For installation problems, [open an issue](https://github.com/Patentext/patentext-agent-plugins/issues) with your agent's name, version, and the error message. Keep credentials and confidential invention details out of public issues.
