---
name: review
description: Read a patent application draft that the law firm shared for review in Patentext, and its comment threads, when the user asks about their patent drafts or reviews.
---

# Patentext Draft Review

Use the connected Patentext MCP tools to read a patent application draft and its comments.

If the tools are unavailable, explain that the Patentext connection must be configured and authenticated before continuing.

## Workflow

1. Call `list_patent_projects` and look for phase `IN_REVIEW`. `get_patent_project` shows a project's abstract, independent claims, and inventor review status.
2. Call `read_patent_application` with the project's `matterId`. Long drafts arrive in parts: pass `nextStartAt` from the previous result as `startAt` to keep reading.
3. Call `read_patent_application_comments` with the same `matterId` for the open comment threads. Pass `includeResolved` to see resolved ones too.

Replying to comments and approving a draft happen in Patentext Lab. Help the user prepare a reply, then send them to the draft's `labUrl`.
