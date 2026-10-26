---
name: grilling
description: Interview the user in rounds about a plan, decision, or idea until nothing is left assumed. Use when the user wants to stress-test their thinking or uses a grill trigger phrase.
---

# Grilling

Interview the user until you share an understanding of the idea. The interview is interactive: each round is an `ask` tool call, and that call is what gives the user a turn.

A question written in your reply does not pause. Do not print the round as chat text. Do not implement, edit files, or draft a plan. If plan mode is on, stay in the interview.

## Each round

The frontier is every decision whose prerequisites are already settled. Ask that whole set in one `ask` call. A question that depends on another question in this same call belongs to a later round.

Call `ask` like this, then stop until it returns:

```json
{
  "questions": [
    {
      "id": "storage",
      "header": "Storage",
      "question": "Which storage should this use?",
      "options": [
        { "label": "SQLite", "description": "One file, no extra service." },
        { "label": "Postgres", "description": "Shared server, more moving parts." }
      ],
      "recommended": 0
    }
  ]
}
```

- Give each question 2–5 real options. Short `label`, the tradeoff in `description`.
- `recommended` is the index of the option you would pick. Word the question so choosing it accepts that recommendation.
- Do not add an "Other" option. The picker adds "Other (type your own)" itself.
- Look up facts yourself. Do not spend an `ask` on something you can read from the repo, docs, or a tool.

## After the user answers

Recompute the frontier from the `ask` results. If any decision is still open, call `ask` again with only that new frontier. If the frontier is empty, restate the shared understanding in a short message and stop. Do nothing else until the user confirms it.

If the user chooses "Chat about this", talk about that point, then return to `ask` for whatever is still unsettled.
