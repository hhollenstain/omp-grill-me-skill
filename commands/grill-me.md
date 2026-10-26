---
description: Interview a loose idea in rounds until every decision is settled. Writes no files.
argument-hint: "[idea]"
---

Run the grilling interview. Follow `skill://grilling`.

Ask with the `ask` tool. A question printed in your reply does not give the user a turn. Each round is one `ask` call for every decision that is ready now: 2–5 options, the tradeoff in `description`, and `recommended` set to the option you would pick. Do not add "Other"; the picker adds it. After you call `ask`, stop until it returns. Then call `ask` again for the new frontier, or restate the shared understanding and wait if nothing is left.

Write no files. Do not implement anything.

The idea to grill:

$ARGUMENTS

If that idea is empty, the first `ask` is only what they want to grill.
