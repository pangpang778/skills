---
name: to-intent
description: Turn a pasted chat log or raw problem report into a structured intent published to the project tracker - for feedback from someone who cannot write specs themselves.
disable-model-invocation: true
---

`to-spec` synthesizes a conversation you have already had. `to-intent` is the earlier move: someone hands you raw material - a pasted support chat, a verbal problem report, a wall of feedback - and you turn it into requirements without inventing anything.

The division of labor: `to-intent` captures what the material settles and names what it leaves open; `grill-with-docs` works the decisions; `to-spec` synthesizes. Intent questions are requirements, not design decisions - if a question turns out to be one, it rides to `grill-with-docs` with its grade attached.

The agent asks, records, and drafts. The human confirms wording, submits, and decides. The agent never decides for anyone.

## The conversation

1. Restate the problem in one sentence, then show a five-section inventory: what is known and what is missing, per section.
2. Ask every gap as one numbered batch. The contributor answers by number ("1 yes; 2 not sure"). An unknown answer is never pressed into a guess - it is recorded as an open question.
3. Re-inventory. Remaining gaps become the next batch. One round = one batch.
4. Soft prompt at round 6 ("draft with current clarity?"), hard stop at round 12. An early exit is never blocked: thin sections surface as longer open questions, and review is the gate that rejects them - not the interview.

## Completion gate

All five sections must pass:

- **Problem**: observable phenomena, no solution embedded.
- **Goal**: one sentence, no qualifiers, names entities and relations.
- **Users and systems**: real names for users and systems; unknowns become open questions.
- **Constraints**: boundaries, limits, and non-goals explicit.
- **Open questions**: non-empty, or an explicit "none".

## The intent

```markdown
---
title: <one-line title>
author: <name>
date: <YYYY-MM-DD>
status: draft | in-review | accepted | rejected
round: 1
---

## Problem

## Goal

## Users and Systems

## Constraints

## Open Questions

- [blocking | non-blocking] <question>
```

The test for `blocking`: can the intent still be accepted without answering it? No - blocking. Yes - non-blocking (tracked, may ride along into development).

## Publishing

Publish the intent to the project's issue tracker (the tracker and triage vocabulary come from `/setup-matt-pocock-skills`), and apply the project's needs-review triage label. The tracker is the only record source; the file mirrors status only.

If rejected, revise and resubmit under the next round number in the same thread - rounds accumulate, history stays traceable.

An accepted intent is the front of the pipeline, not a substitute for it: its blocking questions go to `grill-with-docs` before any spec work, its non-blocking questions ride along, and `to-spec` consumes what settles - the problem, goal, constraints, and open questions it would otherwise have to extract from a conversation nobody had.
