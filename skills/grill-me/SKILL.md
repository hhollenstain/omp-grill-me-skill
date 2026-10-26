---
name: grill-me
description: Start a stateless grilling interview for a loose idea. Invoke only when the user asks to grill something.
disable-model-invocation: true
---

Run the grilling interview on the idea the user just gave you. If they have not named one, your first `ask` is only "what should we grill?", then start the interview.

Follow `skill://grilling`. The part that matters: ask with the `ask` tool, never by printing questions. Each round is one `ask` call containing every decision that is ready now. Stop when that call is made. When it returns, either call `ask` again with the new frontier or, if nothing is left, restate the shared understanding and wait. Write no files and do not implement anything.
