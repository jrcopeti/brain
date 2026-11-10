# Conventional Commits

A commit message format: `<type>[optional scope]: <description>`, then an optional body and
footers, each after a blank line. `fix` is a bug fix (a SemVer patch), `feat` a new feature (a
minor), and a `!` before the colon or a `BREAKING CHANGE:` footer marks a breaking change (a
major). Other types (`docs`, `refactor`, `test`, `chore`, `ci`…) are allowed and don't affect
the version.

Why it matters: commit history becomes something a machine can read, so changelogs and version
bumps can be generated from it. It's the candidate for a commit-message rule, which isn't a
guideline yet.

Source: [sources/2026-11-10-conventional-commits.md](../sources/2026-11-10-conventional-commits.md) (https://www.conventionalcommits.org/en/v1.0.0/)
