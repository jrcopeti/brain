---
source: conversation
captured_at: 2026-11-10T20:31:17Z
captured_by: agent
note: "create a md file with the lines and marks to me to use in the brain repo"
fetch: text-only
edited: "2026-11-10 — lines specific to one project removed at the user's request; only the every-project rules remain"
---

# AGENTS.md rules that hold for every project

The lines of a project's `AGENTS.md` that hold for every project. The project-only lines were removed.

## Intro
- Rules for any agent working in this repository. What the code, `package.json` and the README already say isn't repeated here.

## Working agreement
- Never run `git commit`, `git push`, or `gh pr create` on your own initiative.
- Finish the work, `git add` it so it shows up in the VS Code diff, say what changed, and stop there. (this assumes VS Code everywhere)
- Every diff is reviewed in the editor before it becomes a commit.
- No exceptions for "it's only docs", "it's only a config file", or a change you are confident about.
- The review comes first even when the instruction that started the work mentioned committing.
- A sentence written before the diff existed cannot approve a diff nobody has seen yet.
- "Make the change", "do X", "branch off and do X" aren't permission to commit.
- "Write the plan, then commit and push it" authorises the work but not the commit.
- Only "commit", "push" or "open a PR" given after the changes are staged counts as permission, and only for that diff.
- Permission doesn't carry across steps, branches or turns. Ask again each time.
- If something genuinely has to be committed before it can be reviewed, say so and wait.
- Code review findings are reported, not fixed: severity, scenario and a proposed fix for each, then stop. "Commit and review" doesn't authorise fixes.
- Work in the main working tree, on the branch (`git checkout -b` in the repo root), not in a separate worktree.
- Work done in a detached worktree cannot be reviewed, because the editor never sees it.
- A worktree that's genuinely needed is for verification only; the change itself lands in the main tree.
- Leave the branch checked out when you are done.
- Anything outward-facing (pushing, PR bodies, PR comments, repository settings, deploys): same rule, ask first. Reading is always fine.
- Check which database the connection string resolves to before running anything that writes.

## Per-branch checklist
- Every piece of work is one branch off `main`, one PR.
- `git checkout main && git pull && git checkout -b <branch>` in the repo root, not a worktree.
- Before touching styling, read the project's design notes.
- Do the work and write its tests in the same PR, a failing test first for a bug.
- Green before staging: typecheck, unit tests, build, and e2e when the change touches a covered flow.
- A visible change is verified in a browser at 1440, 768 and 390 wide, with `prefers-reduced-motion: reduce`, and the console checked for errors. (every web project)
- Update the work's plan (`docs/<topic>/PLAN.md`) and its `DEVLOG.md` if it has one.
- Stage the work and stop. No commit, no push, no PR. Leave the branch checked out.

## Keep PRs small
- A PR is sized to be reviewed in one sitting: one concern per branch.
- A step spanning several concerns is split into sub-branches `1a`, `1b`, …, each green and mergeable on its own, dependencies going one way.
- Split before writing code: write the split into the step's `PLAN.md` and say it in a line.
- A sub-branch may leave a temporary bridge for the next one, named in the plan so the next branch removes it.
- If a branch grows past its concern mid-work, stop, propose a split, and move the rest to the next sub-branch.

## Descriptions and code comments
- Write them assertively: plain statements of fact, no hedging, no narrating.
- A description (docblock on a function, type or module) says what it does and what it guarantees, in that order; not the problem it was born from, not how it works inside.
- A comment goes only on a line a competent reader would misread or "fix": a trap, a constraint, a non-obvious decision. It says what the line achieves and what breaks without it. Clear lines get none.
- Both are up to three lines, complete enough that the reader needn't look anything up. Never what the code already says, never how it got there (that is the commit message and the plan).
- Longer reasoning goes in a design doc or the plan, with a one-line pointer in the code.

## Docs
- `docs/<topic>/PLAN.md`: one folder and plan per piece of work, tracked. Read the relevant plan at the start of a task and keep it updated; churn is expected. New work gets a new folder.
- A devlog records what a plan's branches built, each review's findings and what was measured, new entries last. The plan says what comes next; what a branch leaves open and is worth doing goes in both.
- Rules only one folder needs go in that folder's own `AGENTS.md`, with a `CLAUDE.md` beside it that imports it, since Claude Code won't load it otherwise.
- A durable decision goes beside what it governs, in one of the docs above.
- A plan records its work and where it stands, and a devlog's index each finished branch's state; nothing else repeats status.

## CLAUDE.md
- `CLAUDE.md` contains `@AGENTS.md`.
