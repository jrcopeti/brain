---
source: own
---

# pnpm for new projects

**Rule:** new projects use pnpm, never npm. Existing projects keep whichever
package manager they already use; npm or pnpm are both fine there.

**Why:** my own rule.

**How:** scaffold with `pnpm create …` / `pnpm init`, commit `pnpm-lock.yaml`, and never
add a `package-lock.json`. In an existing repo, follow the lockfile that is already there.

Source: own
