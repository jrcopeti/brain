---
source: own
---

# Green before staging

**Rule:** before staging, typecheck, unit tests and build pass, and e2e passes when the change
touches a flow the e2e tests cover. The tests ship in the same PR as the work, and a bug fix
starts with a failing test.

**Why:** a reviewer should only ever look at a diff that already works. A failing test first
proves the fix fixes the bug.

**How:** run the project's own scripts for each check. A web change that's visible is also checked
in a browser at 1440, 768 and 390 wide, with `prefers-reduced-motion: reduce`, and the console
checked for errors.

Source: own, first written down in [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
