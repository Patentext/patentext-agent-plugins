---
name: strategy
description: Read or continue a Patentext patent strategy conversation when the user asks to work with their organization's Patentext strategy agent.
---

# Patentext Strategy

Use the connected Patentext MCP tools to work with the user's existing strategy conversation.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Workflow

1. Call `get_ip_strategy_workspace` to see the current strategy state: its phase, the phase outputs delivered so far, and the strategy interview's `threadId`. Call `get_revenue_sources` and `get_business_differentiators` for what the strategy has recorded about the business.
2. Call `read_agent_thread` with that `threadId` to catch up before contributing.
3. Use `send_agent_message` with the same `threadId` for a free-text response, or `answer_questionnaire` when the agent is waiting for questionnaire answers.
4. When a result reports `running` or `queued`, follow its `next` instructions and continue reading with the supplied `afterMessageId` and `waitSeconds` until the turn finishes or the user asks to stop.

Use facts the user has supplied about their company. Ask for missing information rather than inventing business details. Keep messages to the Patentext agent within the user's requested scope.
