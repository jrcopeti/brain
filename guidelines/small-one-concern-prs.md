---
source: own
---

# Small PRs, one concern each

**Rule:** a PR is sized to be reviewed in one sitting: one concern per branch.

**Why:** a big PR doesn't get a real review. Small PRs that are green on their own can be merged,
or reverted, one at a time.

**How:** split a step with several concerns into sub-branches `1a`, `1b`… before writing code.
Each is green and mergeable on its own, with dependencies going one way. Write the split into
the plan and say it in a line. A sub-branch may leave a temporary bridge, named in the plan, for
the next one to remove. If a branch grows past its concern partway through, stop, propose a
split, and move the rest to the next sub-branch.

Source: own, first written down in [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
