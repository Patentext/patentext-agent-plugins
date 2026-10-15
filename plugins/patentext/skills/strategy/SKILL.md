---
name: strategy
description: Read or continue a Patentext patent strategy conversation when the user asks to work with their organization's Patentext strategy agent.
---

# Patentext Strategy

Use the connected Patentext MCP tools to work with the user's existing strategy conversation.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Workflow

1. Call `get_strategy_workspace` to see the current strategy state, including the revenue sources and differentiators recorded so far.
2. Call `read_conversation` with target `{"kind":"strategy"}` to catch up before contributing.
3. Use `send_message` with the same target for a free-text response, or `answer_questions` when the strategy agent is waiting for questionnaire answers.
4. When a result reports `running`, follow its `next` instructions and continue reading with the supplied `afterMessageId` and `waitSeconds` until the turn finishes or the user asks to stop.

Use facts the user has supplied about their company. Ask for missing information rather than inventing business details. Keep messages to the strategy agent within the user's requested scope.
