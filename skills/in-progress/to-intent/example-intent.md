---
title: Absorb the real gaps from mattpocock/skills into the shipyard
author: pangpang778
date: 2026-09-24
status: accepted
round: 1
---

## Problem

Observed while comparing upstream skill releases against local coverage:

1. Agent-written PR descriptions vary in quality and lack a reviewable evidence structure.
2. The retrospective that runs at the end of a delivery pipeline collects environment lessons from an incomplete category list - tool cost, dead steering instructions, and information-access gaps are not systematically asked.
3. Plain coding sessions (no delivery pipeline) have no retrospective mechanism at all.
4. When implementing a spec, exploration work is re-done inside every implementer context instead of done once and shared.

## Goal

Absorb the four identified gaps from upstream skills into the local skill set so that both pipeline runs and plain sessions produce reviewable PR bodies, complete environment lessons, and non-duplicated exploration.

## Users and Systems

- Users: agent operators running the local harness (maintainers and plugin consumers).
- Systems: the local harness's skills (`launch`, `drydock`, new `careen` and `pr` skills); upstream reference `github.com/mattpocock/skills`.

## Constraints

- Absorb gaps only, no duplicate truths: one upstream skill overlaps ~90% with the local pipeline and is not adopted; only its exploration-notes pattern is extracted.
- Absorbed concepts are rewritten in the local vocabulary, never copied verbatim; upstream credits are preserved.
- The new retrospective skill is propose-only: per-line veto, and a doc-discipline checklist gates every write.
- The PR body skill is copied into the local skill set so the pipeline's pointer is not a dead path.

## Open Questions

- [non-blocking] Should the retrospective skill's suggestions about the global config file also respect the thin-entry budget (max five hot entries)?
- [non-blocking] Does this repo track upstream updates to the absorbed skills, or is the absorbed copy frozen at the current snapshot?
