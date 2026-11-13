---
source: conversation
captured_at: 2026-11-13T23:14:10Z
captured_by: agent
note: "Saved so the next Claude Code session (run from the kit folder) can continue lesson 8.2"
fetch: text-only
---

M8 Hermes setup (lesson 8.2) for the AI employee "Tania" — decisions and progress, 2026-11-14.

Decisions:
- Server: Lima VM `tania-box` on the Mac (Ubuntu 24.04.5, 4 CPU, 4 GiB RAM, 40 GiB disk). Created with --mount-none, so the VM cannot read Mac files such as trip-ai's .env (production database). Reach it with `limactl shell tania-box`. Runs only while the Mac is awake.
- Agent name: Tania.
- Main model: an OpenRouter free model (no ChatGPT plan). Free tier is 50 requests/day until 10 USD of credits are bought.

Progress:
- Done: Step 1, user `agent` created with linger=yes.
- Not done: Step 1 packages (git PPA, gh, Docker + rootless extras, disable root docker), then Steps 1b, 2, 3, 4, 5, 6, 7, 11.

Gotcha: run the Doctor Agent (Claude Code) from ~/code/ai-agent-engineer-course-kit, not from ~/code/ticket-bay. TicketBay's guard-network.sh PreToolUse hook blocks curl, literal URLs and environment-looking commands, which the server setup needs.
