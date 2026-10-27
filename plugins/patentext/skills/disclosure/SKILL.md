---
name: disclosure
description: Record an invention in Patentext and take part in its invention disclosure interview when the user wants to protect something they built or continue a disclosure.
---

# Patentext Invention Disclosure

Use the connected Patentext MCP tools to record an invention and prepare it for the patent attorney.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Record an invention

1. Call `list_inventions` and check whether the invention is already recorded. If it is, use its `inventionId`.
2. If it isn't recorded, call `send_agent_message` with `threadId` null, and describe the invention: a short title, a technical summary, its technical field, and how mature it is. Include the relevant parts of its design documents. Ask the Patentext agent to record it. Say whether the invention was shown, sold, or published only if the user told you.

## Take part in the disclosure interview

1. Find the invention's disclosure interview: call `get_invention` and use the `threadId` of its unfinished disclosure. If it has none, ask the Patentext agent, in your conversation from the previous step, to open the invention's disclosure interview; it replies with the interview's `threadId`.
2. Call `read_agent_thread` with that `threadId` to catch up.
3. Use `send_agent_message` with the same `threadId` for a free-text answer, or `answer_questionnaire` when the agent is waiting for questionnaire answers.
4. When a result reports `running` or `queued`, follow its `next` instructions until the turn finishes or the user asks to stop.
5. Call `read_invention_disclosure` to read what the interview has captured so far, or the finished disclosure package.

Disclosure answers shape the patent application. Answer only from what the user and their documents say, and ask the user about any technical detail you don't know. Patentext shows your messages as sent by the user through MCP.

Invention details are confidential until the patent application is filed. Don't put them in public repositories, issues, or chat channels unless the user asks you to.
