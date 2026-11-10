# AGENTS.md rules: every project vs one project

The trip-planner repo's `AGENTS.md`, sorted line by line: which rules hold for every
project and which only make sense in that repo. It's a list of candidate guidelines,
not a set of guidelines yet.

**Holds for every project:**
- **Review before commit:** stage the work and stop. Only "commit", "push" or "open a PR"
  said after the diff is staged counts as permission, for that diff only. Ask before
  anything outward-facing.
- **Main tree, not a worktree:** work on a branch in the main working tree, since the
  editor can't review a detached worktree.
- **Small PRs:** one concern per branch, split into `1a`, `1b`… before writing code,
  with the split written in the plan.
- **Green before staging:** typecheck, unit tests, build, and e2e when the change
  touches a covered flow. A bug fix starts with a failing test.
- **Assertive descriptions:** comments only on lines a reader would misread, up to
  three lines.
- **Plans and devlogs:** one `docs/<topic>/PLAN.md` per piece of work, plus a devlog.
  Folder-specific rules go in that folder's own `AGENTS.md`, with a `CLAUDE.md` beside it
  that imports it.

**Only that repo:** its `.env` points at production, the e2e seed deletes trips,
`npm run lint` is broken, and the docs it names (`docs/design-notes.md`,
`docs/testing.md`, the grounded-agent plan).

Why it matters: these lines are the raw material for global guidelines. Each one becomes
a guideline only when the user says so.

Source: [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
