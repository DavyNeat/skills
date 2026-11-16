---
name: research
description: Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo. Use when the user wants a topic researched, docs or API facts gathered, or reading legwork delegated to a background agent.
---

Spin up a **background agent** to do the research, so you keep working while it reads.

Its job:

1. Investigate the question against **primary sources** (official docs, source code, specs, first-party APIs), not a secondary write-up of them. Follow every claim back to the source that owns it.
2. Write the findings to a single Markdown file, citing each claim's source.
3. Save it where the repo already keeps such notes; match the existing convention, and if there is none, put it somewhere sensible and say where.

## Quick answers in chat

When the question is small enough to answer inline (a price, a plan comparison, "is there a tool for X"), skip the background agent and the file, but keep the source discipline:

- Read the vendor's own page (pricing page, help center, docs) before you state a fact that drives a recommendation. Review and comparison sites summarize unevenly and drop caveats, so a claim built on them can flip the recommendation and force a correction later.
- If you only read secondary sources, say so in one sentence and name the page the user should check.
- When a later turn shows an earlier answer was wrong, correct it plainly in the next reply; do not let the wrong claim stand.

For questions about giving agents access to sensitive accounts (money, health, identity), use the evaluation in `references/agent-data-access.md`.
