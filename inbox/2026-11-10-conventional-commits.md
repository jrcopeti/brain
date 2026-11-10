---
source: https://www.conventionalcommits.org/en/v1.0.0/#summary
captured_at: 2026-11-10T21:20:21Z
captured_by: agent
note: "for commit rules"
fetch: text-only
---

Conventional Commits 1.0.0 (CC BY 3.0). Text as fetched on 2026-11-10.

## Summary

A lightweight convention on top of commit messages: rules for an explicit commit history, which makes automated tools easier to write. It dovetails with SemVer by describing features, fixes and breaking changes in commit messages.

Structure:

    <type>[optional scope]: <description>

    [optional body]

    [optional footer(s)]

1. fix: patches a bug (PATCH in SemVer).
2. feat: introduces a new feature (MINOR in SemVer).
3. BREAKING CHANGE: a footer `BREAKING CHANGE:`, or a `!` after the type/scope, introduces a breaking API change (MAJOR in SemVer). Can be part of any type.
4. Types other than fix: and feat: are allowed, e.g. @commitlint/config-conventional (Angular convention) recommends build:, chore:, ci:, docs:, style:, refactor:, perf:, test:, and others.
5. Footers other than `BREAKING CHANGE: <description>` may be provided, following a convention similar to git trailer format.

Additional types are not mandated and have no implicit SemVer effect (unless they include a BREAKING CHANGE). A scope goes in parentheses, e.g. `feat(parser): add ability to parse arrays`.

## Specification (RFC 2119 key words)

1. Commits MUST be prefixed with a type (a noun: feat, fix, etc.), followed by the OPTIONAL scope, OPTIONAL !, and REQUIRED terminal colon and space.
2. The type feat MUST be used when a commit adds a new feature.
3. The type fix MUST be used when a commit represents a bug fix.
4. A scope MAY be provided after a type. It MUST be a noun describing a section of the codebase, in parentheses, e.g. `fix(parser):`.
5. A description MUST immediately follow the colon and space. It is a short summary of the code changes.
6. A longer body MAY follow the description. It MUST begin one blank line after the description.
7. The body is free-form and MAY have any number of newline-separated paragraphs.
8. One or more footers MAY follow one blank line after the body. Each footer MUST be a word token, then ":<space>" or "<space>#", then a string value (git trailer convention).
9. A footer token MUST use "-" in place of whitespace, e.g. Acked-by. Exception: BREAKING CHANGE MAY be used as a token.
10. A footer value MAY contain spaces and newlines; parsing MUST stop at the next valid token/separator pair.
11. Breaking changes MUST be indicated in the type/scope prefix or as a footer entry.
12. As a footer, a breaking change MUST be the uppercase text BREAKING CHANGE, a colon, a space, and a description.
13. In the prefix, a breaking change MUST be a ! immediately before the :. If ! is used, the BREAKING CHANGE: footer MAY be omitted and the description SHALL describe the breaking change.
14. Types other than feat and fix MAY be used, e.g. `docs: update ref docs`.
15. The units of information MUST NOT be treated as case-sensitive by implementors, except BREAKING CHANGE, which MUST be uppercase.
16. BREAKING-CHANGE MUST be synonymous with BREAKING CHANGE as a footer token.

## Example

    fix: prevent racing of requests

    Introduce a request id and a reference to latest request. Dismiss
    incoming responses other than from latest request.

    Remove timeouts which were used to mitigate the racing issue but are
    obsolete now.

    Reviewed-by: Z
    Refs: #123
