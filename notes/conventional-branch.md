# Conventional Branch

A branch naming format: `<type>/<description>`, all lowercase, words joined by single hyphens, dots
only in versions. Types: `feature`/`feat`, `bugfix`/`fix`, `hotfix`, `release`, `chore`, plus (since
v1.1.0) agent prefixes such as `claude/`, `codex/` or `ai/` for branches an AI agent made. `main`,
`master` and `develop` have no prefix. Include the ticket number when there is one:
`feature/issue-123-new-login`.

Why it matters: a branch name says what the work is, and CI can act on the type (deploy from
`release/`). The agent prefixes fit the [one branch per piece of work](../guidelines/one-branch-per-piece-of-work.md)
guideline. This is the candidate for a branch-naming rule, which isn't a guideline yet.

Source: [sources/2026-11-10-conventional-branch.md](../sources/2026-11-10-conventional-branch.md) (https://conventionalbranch.org/)
