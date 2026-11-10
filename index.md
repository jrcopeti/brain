# Index

Read this first. One line per file: what it is, so you know whether to open it.

## Intents
- [Example app: public launch](intents/example-app-public-launch.md) — the goal, why, and the check that says it's done.

## Guidelines
- [Integration tests use a real database](guidelines/integration-tests-real-database.md) — never mock the database in integration tests; start a real one in a container.
- [pnpm for new projects](guidelines/pnpm-for-new-projects.md) — new projects use pnpm, never npm; existing projects may keep either.
- [Stage the work and stop before committing](guidelines/stage-and-stop-before-commit.md) — agents stage and stop; only a "commit"/"push"/"PR" given after the diff counts as permission; the brain repo is exempt.
- [One branch per piece of work](guidelines/one-branch-per-piece-of-work.md) — one branch off a fresh main, one PR, reviewed in the folder where it was done; a worktree is fine when open in the editor.
- [Small PRs, one concern each](guidelines/small-one-concern-prs.md) — one concern per branch; split into 1a, 1b… before coding.
- [Green before staging](guidelines/green-before-staging.md) — typecheck, tests, build (and e2e when covered) pass first; a bug fix starts with a failing test.
- [Short, plain descriptions and comments](guidelines/short-plain-descriptions-and-comments.md) — what it does and guarantees; comments only on lines a reader would misread; at most three lines.
- [A plan and a devlog for each piece of work](guidelines/plan-and-devlog-per-piece-of-work.md) — a tracked docs/<topic>/PLAN.md plus a devlog; status lives only there.
- [Test behavior, not implementation](guidelines/test-behavior-not-implementation.md) — test through the public API; a refactor that changes no behavior must not break a test.

## Decisions
- [2026-01-15 Postgres as the default database](decisions/2026-01-15-postgres-default-database.md) — new projects start on Postgres unless there is a reason not to.

## Projects
- [Example app](projects/example-app.md) — what it is, where it runs, its status.

## Notes
- [Global agent working rules](notes/global-agent-working-rules.md) — where the six agent working-rule guidelines came from, and the change to the branch rule.
- [Why mocks hide database bugs](notes/why-mocks-hide-database-bugs.md) — the failure modes a mocked database misses, with the source.
