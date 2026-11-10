---
source: own
---

# One branch per piece of work, reviewed where it was done

**Rule:** each piece of work is one branch created from an up-to-date `main`, and one PR. The work
is reviewed in the folder where it was done. A worktree is fine as long as it's open in the
editor.

**Why:** the review only works if the editor shows the diff. The older rule (main folder, never a
worktree) kept work visible but blocked running agents in parallel.

**How:** `git checkout main && git pull && git checkout -b <branch>`, or `git worktree add` from an
up-to-date `main` and open that folder in the editor. Leave the branch checked out when done.

Source: own, first written down in [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
