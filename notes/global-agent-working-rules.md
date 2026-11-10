# Global agent working rules

Working rules for coding agents that hold in every project: stage the work and stop until a
commit is asked for after the diff exists, one branch per piece of work off a fresh `main`, reviewed
in the folder where the work happened (a worktree is fine when it is open in the editor), small
one-concern PRs split before coding, green checks before staging, terse descriptions and
comments, and a plan plus devlog per piece of work.

Why it matters: these are candidates for global guidelines, so no repo has to repeat them. Each
becomes a guideline only when the user states it.

The branch rule was changed by the user on 2026-11-10 (source: own). The original said "main tree,
no worktree" because the editor only showed the main tree. That blocks running agents in parallel.

Source: [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
