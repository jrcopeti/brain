---
source: conversation
captured_at: 2026-11-10T20:31:17Z
captured_by: agent
note: "create a md file with the lines and marks to me to use in the brain repo"
fetch: text-only
---

# AGENTS.md rules: every project vs this project only

Each sentence or bullet of the trip-planner repo's `AGENTS.md` (/workspace), marked **every project**
(belongs in a global file) or **this project only** (stays in that repo). Mixed lines are split, the
general rule first.

## Intro
- Rules for any agent working in this repository. What the code, `package.json` and the README already say isn't repeated here. — **every project**

## Working agreement
- Never run `git commit`, `git push`, or `gh pr create` on your own initiative. — **every project**
- Finish the work, `git add` it so it shows up in the VS Code diff, say what changed, and stop there. — **every project** (this assumes VS Code everywhere)
- Every diff is reviewed in the editor before it becomes a commit. — **every project**
- No exceptions for "it's only docs", "it's only a config file", or a change you are confident about. — **every project**
- The review comes first even when the instruction that started the work mentioned committing. — **every project**
- A sentence written before the diff existed cannot approve a diff nobody has seen yet. — **every project**
- "Make the change", "do X", "branch off and do X" aren't permission to commit. — **every project**
- "Write the plan, then commit and push it" authorises the work but not the commit. — **every project**
- Only "commit", "push" or "open a PR" given after the changes are staged counts as permission, and only for that diff. — **every project**
- Permission doesn't carry across steps, branches or turns. Ask again each time. — **every project**
- If something genuinely has to be committed before it can be reviewed, say so and wait. — **every project**
- Code review findings are reported, not fixed: severity, scenario and a proposed fix for each, then stop. "Commit and review" doesn't authorise fixes. — **every project**
- Work in the main working tree, on the branch (`git checkout -b` in the repo root), not in a separate worktree. — **every project**
- Work done in a detached worktree cannot be reviewed, because the editor never sees it. — **every project**
- A worktree that's genuinely needed is for verification only; the change itself lands in the main tree. — **every project**
- Leave the branch checked out when you are done. — **every project**
- Anything outward-facing (pushing, PR bodies, PR comments, repository settings, deploys): same rule, ask first. Reading is always fine. — **every project**
- Check which database the connection string resolves to before running anything that writes. — **every project**
- `npm run dev` and a bare `npx prisma db push` use `.env.local`'s, then `.env`'s `DATABASE_URL`; on the owner's machine that is `.env`'s, which is production. — **this project only**
- `npm run seed:e2e` deletes every trip in `E2E_DATABASE_URL`. — **this project only**
- `ALLOW_REMOTE_E2E_SEED=1` lets the seed, the push script and `trip-journey.spec.ts` write to a remote host. Don't set it unless asked. — **this project only**

## Per-branch checklist
- Every piece of work is one branch off `main`, one PR. — **every project**
- `git checkout main && git pull && git checkout -b <branch>` in the repo root, not a worktree. — **every project**
- Before touching styling, read the project's design notes. — **every project**
- …`docs/design-notes.md`, at least "Building a page" and "Gotchas that cost real time". — **this project only**
- Do the work and write its tests in the same PR, a failing test first for a bug. — **every project**
- Read `docs/testing.md` before writing tests. — **this project only**
- Green before staging: typecheck, unit tests, build, and e2e when the change touches a covered flow. — **every project**
- The script names `npm run typecheck`, `npm test`, `npm run build`, `npm run test:e2e`. — **this project only** (unless every project uses these names)
- `npm run lint` is broken and is not a signal. — **this project only**
- A visible change is verified in a browser at 1440, 768 and 390 wide, with `prefers-reduced-motion: reduce`, and the console checked for errors. — **every project** (every web project)
- …hydration errors. — **this project only** (every project if all are Next.js/React SSR)
- In Claude Code, the `verify-in-browser` skill has the steps. — **this project only** (tied to this repo's e2e database and fixtures)
- Update the work's plan (`docs/<topic>/PLAN.md`) and its `DEVLOG.md` if it has one. — **every project**
- …and `docs/design-notes.md` when the visual system changed. — **this project only**
- Stage the work and stop. No commit, no push, no PR. Leave the branch checked out. — **every project**

## Keep PRs small
- A PR is sized to be reviewed in one sitting: one concern per branch. — **every project**
- A step spanning several concerns is split into sub-branches `1a`, `1b`, …, each green and mergeable on its own, dependencies going one way. — **every project**
- Split before writing code: write the split into the step's `PLAN.md` and say it in a line. — **every project**
- A sub-branch may leave a temporary bridge for the next one, named in the plan so the next branch removes it. — **every project**
- If a branch grows past its concern mid-work, stop, propose a split, and move the rest to the next sub-branch. — **every project**

## Descriptions and code comments
- Write them assertively: plain statements of fact, no hedging, no narrating. — **every project**
- These rules are for what you write; older code doesn't all meet them yet. — **this project only**
- A description (docblock on a function, type or module) says what it does and what it guarantees, in that order; not the problem it was born from, not how it works inside. — **every project**
- The example: "Reduces OpenWeather's list to one reading per trip day…" — **this project only** (a global file wants a neutral example)
- A comment goes only on a line a competent reader would misread or "fix": a trap, a constraint, a non-obvious decision. It says what the line achieves and what breaks without it. Clear lines get none. — **every project**
- The example: "Without `.utc()` dayjs would use the server's zone." — **this project only**
- Both are up to three lines, complete enough that the reader needn't look anything up. Never what the code already says, never how it got there (that is the commit message and the plan). — **every project**
- Longer reasoning goes in a design doc or the plan, with a one-line pointer in the code. — **every project**
- …`docs/design-notes.md` as that doc. — **this project only**

## Docs
- `docs/design-notes.md`: the `sorbet` design system. Read it before styling anything. — **this project only**
- `docs/testing.md`: how tests are written here. Read it before writing one. — **this project only**
- `docs/generation.md`: the trip generation's state, as tables. Change them with the code. — **this project only**
- `README.md`: the architecture, running locally, CI. — **this project only**
- `docs/<topic>/PLAN.md`: one folder and plan per piece of work, tracked. Read the relevant plan at the start of a task and keep it updated; churn is expected. New work gets a new folder. — **every project**
- The plan in flight is `docs/grounded-agent/PLAN.md`; the others are records. — **this project only**
- A devlog records what a plan's branches built, each review's findings and what was measured, new entries last. The plan says what comes next; what a branch leaves open and is worth doing goes in both. — **every project**
- `docs/grounded-agent/DEVLOG.md` as that devlog. — **this project only**
- Rules only one folder needs go in that folder's own `AGENTS.md`, with a `CLAUDE.md` beside it that imports it, since Claude Code won't load it otherwise. — **every project**
- The folders `e2e/`, `prisma/`, `src/app/api/`. — **this project only**
- A durable decision goes beside what it governs, in one of the docs above. — **every project**
- A plan records its work and where it stands, and a devlog's index each finished branch's state; nothing else repeats status. — **every project**

## CLAUDE.md
- `CLAUDE.md` contains `@AGENTS.md`. — **every project**
