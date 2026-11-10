---
source: https://conventionalbranch.org/
captured_at: 2026-11-10T21:20:35Z
captured_by: agent
note: "for branch naming rules"
fetch: text-only
---

Conventional Branch v1.1.0 (CC BY 4.0). A close restatement of the page as fetched on 2026-11-10, not verbatim.

## Summary

A structured naming convention for Git branches, so they're readable and actionable. It suggests prefixes but lets teams define their own. Goals: purpose-driven names, CI/CD integration (pipelines can act on branch type, e.g. auto-deploy from release branches), team collaboration.

## Structure

    <type>/<description>

## Types

Purpose:
- feature/ (alias feat/): new features. feature/add-login-page
- bugfix/ (alias fix/): bug fixes. bugfix/fix-header-bug, fix/header-bug
- hotfix/: urgent fixes. hotfix/security-patch
- release/: preparing a release. release/v1.2.0
- chore/: non-code tasks such as dependency or doc updates. chore/update-dependencies

AI agent source (new in v1.1.0, marks branches made by AI coding agents):
- ai/ (any agent), claude/ (Claude Code), codex/ (OpenAI Codex), copilot/ (GitHub Copilot), cursor/ (Cursor)

Trunk branches have no prefix: main, master, develop.

## Rules

1. Lowercase a-z, digits 0-9, hyphens between words. No special characters, underscores or spaces. Dots are allowed in the description, usually for versions (release/v1.2.0, chore/upgrade-node-v20.11).
2. No consecutive, leading or trailing hyphens or dots in the description.
3. Clear and concise, describing the work's purpose.
4. Include ticket numbers when applicable: feature/issue-123-new-login.

## Grammar (ABNF)

    branch-name     = trunk-branch / prefixed-branch
    trunk-branch    = "main" / "master" / "develop"
    prefixed-branch = type "/" description
    type            = "feature" / "feat" / "bugfix" / "fix" / "hotfix" / "release" / "chore" / "ai" / "copilot" / "cursor" / "claude" / "codex"
    description     = desc-segment *("-" desc-segment)
    desc-segment    = 1*(ALPHA / DIGIT) *("." 1*(ALPHA / DIGIT))

## Examples

Valid: feature/add-login-page, feat/add-login-page, fix/header-bug, hotfix/security-patch, release/v1.2.0, chore/upgrade-node-v20.11, feature/issue-123-new-login, ai/refactor-auth-flow, claude/security-patch

Invalid: Feature/Add-Login (uppercase), feature/new--login (double hyphen), feature/-new-login (leading hyphen), feature/new-login- (trailing hyphen), release/v1.-2.0 (hyphen next to dot), fix/header bug (space), fix/header_bug (underscore), unknown/some-task (unknown type)

## FAQ notes

- Prefixes come from git-flow (c. 2010); the spec adds a fixed type set, a grammar and a validation regex (spec.json).
- Fewer types than Conventional Commits on purpose. Teams may add their own (e.g. experiment/) in their validator config; those are outside the spec.
- Lowercase is required because macOS and Windows file systems are case-insensitive for refs.
- Long-lived branches like staging or production are outside the grammar.
- Tooling: commit-check, commit-check-action.
