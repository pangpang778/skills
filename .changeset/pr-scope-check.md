---
"mattpocock-skills": patch
---

pr: add a Scope check section. The Summary comes from the primary source, never inferred from the diff, so nothing verified that the branch delivers that scope. A branch cut from the wrong base carries other work in its commit ancestry; the merge ships it and the body still reads docs-only. Before writing the body, `git log <target>..HEAD --oneline` and `git diff <target>...HEAD --stat` must confirm the branch delivers exactly the primary source's scope; on mismatch, recreate the branch from `<target>`. Relates to #1331.
