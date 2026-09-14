---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

Use /tdd where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use /code-review to review the work.

Commit your work to the current branch.

Close out the work on the tracker. When the work came from published tickets, close each ticket it completes (as completed) with one comment carrying the pointer a reader needs to verify the work: the PR link, or the commit on the branch when no PR exists. Do not close the parent spec or other issues the tickets referenced — closing those is the maintainer's call. Without this step the tickets stay open on `ready-for-agent` after their work has shipped, and the frontier fills with already-done work.
