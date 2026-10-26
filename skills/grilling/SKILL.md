---
name: grilling
description: Interview the user in rounds about a plan, decision, or idea until nothing is left assumed. Use when the user wants to stress-test their thinking or uses a grill trigger phrase.
---

# Grilling

Interview the user until the two of you share an understanding of the idea. This session is stateless: write no files, leave no glossary, and do not implement, edit, or draft a plan. If plan mode is on, stay in the interview. Plan mode is for later.

Map the idea as a design tree. Every decision branches into the decisions that hang off it.

Work the tree in rounds. The frontier is every decision whose prerequisites are already settled: the questions you can ask now without guessing at an answer you have not heard. Ask the whole frontier in one round. Number each question and give your recommended answer. Then stop and wait.

Format a round like this:

```
❓ **Q1** - **<question title>**: <question body. A question may be several paragraphs and may include choices.>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body>

➡️ <your recommended answer>
```

Word each question so "yes" accepts your recommended answer.

Each round of answers reshapes the tree. Settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier before the next round. A question whose answer depends on another question still open in this round belongs to a later round.

Finding facts is your job, never the user's. When a frontier question needs something you can look up in the repo, the docs, or with a tool, look it up. If you can dispatch a subagent, do that and do not block the rest of the round on it: questions downstream of that lookup wait, and you ask the rest of the frontier now. The decisions belong to the user. Put each one to them and wait.

The session is done when the frontier is empty: every branch has been visited, and nothing important is still an unspoken assumption. Restate the shared understanding and wait for the user to confirm it. Do not act on the idea until they confirm.
