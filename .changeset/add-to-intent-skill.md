---
"mattpocock-skills": patch
---

Add the `to-intent` skill (in-progress bucket, user-invoked). It is the entry point the `to-spec` family was missing for material nobody has interviewed yet: a contributor pastes a raw chat log or problem report, the agent runs numbered batch questioning until a five-section intent passes a completion gate (observable problem, one-sentence goal, real names, explicit constraints, open questions - unknowns are never guessed into answers), then publishes it to the project tracker under the needs-review triage label. Rejections revise and resubmit under the next round number. An accepted intent feeds the pipeline - blocking questions to `grill-with-docs`, the rest to `to-spec`. Adapted from oh-my-claudecode's `intent` skill by pangpang778 (credited in the skill's `CREDITS.md`); the multi-role review records were flattened for this repo's single-owner workflow.
