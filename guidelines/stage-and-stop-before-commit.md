---
source: own
---

# Stage the work and stop before committing

**Rule:** an agent finishes the work, stages it (`git add`), says what changed, and stops. Only
"commit", "push" or "open a PR" said after the diff is staged counts as permission, and only
for that diff. Anything outward-facing (pushes, PR bodies and comments, repository settings,
deploys) needs the same permission first. Reading is always fine.

**Why:** every diff gets reviewed before it becomes a commit. An instruction written before the
diff existed can't approve a diff nobody has seen.

**How:** "do X" or "write the plan, then commit it" allows the work, not the commit. Permission
doesn't carry over to the next step, branch or turn. Docs and config changes get no exception.
Code review findings are reported (severity, scenario, proposed fix), not fixed. If something
really has to be committed before review, say so and wait.

**Exception:** this brain repo. Its AGENTS.md says to always leave it pushed with `node sync.mjs`.

Source: own, first written down in [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
