---
name: review
description: Read a patent application draft that the law firm shared for review in Patentext, and reply to its comment threads, when the user asks about their patent drafts or reviews.
---

# Patentext Draft Review

Use the connected Patentext MCP tools to read a patent application draft and its comments.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Workflow

1. Call `get_overview` to find drafts waiting for review. To find a specific project, call `list_patent_projects` and look for phase `IN_REVIEW`.
2. Call `read_patent_draft` with the project's `matterId`. Long drafts arrive in parts: pass `nextStartAt` from the previous result as `startAt` to keep reading. Open comment threads arrive with the first part.
3. To answer a comment, call `reply_to_comment` with the `matterId`, the `threadId`, and the reply. The law firm sees the reply under the user's name, so confirm the wording with the user first.

Approving a draft is the user's decision. To approve it, send the user to the draft's `labUrl`.
