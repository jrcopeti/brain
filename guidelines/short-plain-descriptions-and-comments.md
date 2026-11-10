---
source: own
---

# Short, plain descriptions and comments

**Rule:** descriptions (docblocks on functions, types, modules) and comments are plain statements
of fact, with no hedging and no narrating, and at most three lines.

**Why:** a reader should get the contract or the trap without looking anything up, and without
wading through history that belongs in the commit message.

**How:** a description says what the code does, then what it guarantees. It doesn't say the problem
the code was born from or how it works inside. A comment goes only on a line a competent reader
would misread or "fix" (a trap, a constraint, a choice that isn't obvious), and says what the line
achieves and what breaks without it. Never repeat what the code says. Longer reasoning goes in a
design doc or the plan, with a one-line pointer in the code. Old code doesn't have to meet this
yet.

Source: own, first written down in [sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md](../sources/2026-11-10-agents-md-rules-every-project-vs-this-project-only.md)
