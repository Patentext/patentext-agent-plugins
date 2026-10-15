---
name: disclosure
description: Record an invention in Patentext, add its design documents, and take part in its invention disclosure interview when the user wants to protect something they built or continue a disclosure.
---

# Patentext Invention Disclosure

Use the connected Patentext MCP tools to record an invention and prepare it for the patent attorney.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Record an invention

1. Call `list_inventions` and check whether the invention is already recorded. If it is, use its `inventionId`.
2. If it isn't recorded, call `create_invention` with a short title, a technical summary, the technical field, and its maturity. Leave `publicDisclosureStatus` as `UNKNOWN` unless the user told you whether the invention was shown, sold, or published.
3. Call `add_knowledge` with each document that describes the invention, such as a design doc or README, and pass its `inventionId`. The disclosure agent reads these documents.

## Take part in the disclosure interview

1. Call `start_invention_disclosure` with the `inventionId`. It resumes the invention's unfinished disclosure or starts one, and returns a `disclosureId`.
2. Call `read_conversation` with target `{"kind":"disclosure","disclosureId":"DISCLOSURE_ID"}` to catch up. Replace `DISCLOSURE_ID` with the returned `disclosureId`.
3. Use `send_message` with the same target for a free-text answer, or `answer_questions` when the disclosure agent is waiting for questionnaire answers.
4. When a result reports `running`, follow its `next` instructions until the turn finishes or the user asks to stop.

Disclosure answers shape the patent application. Answer only from what the user and their documents say, and ask the user about any technical detail you don't know. Patentext shows your messages as sent by the user through MCP.

Invention details are confidential until the patent application is filed. Don't put them in public repositories, issues, or chat channels unless the user asks you to.
