---
source: conversation
captured_at: 2026-11-13T23:57:56Z
captured_by: agent
note: "Saved so later lessons and reruns of the guide don't hit the same walls"
fetch: text-only
---

Gotchas from M8 lesson 8.2 setup on tania-box, 2026-11-14.

1. The guide's free OpenRouter models are retired: inclusionai/ling-3.0-flash-sante:free and apodex/apodex-1.1-mini:free both return HTTP 404 "no provider serves this model anymore".
   With training turned off (paid and free), these free models made real tool calls on 2026-11-14: cohere/north-mini-code:free (chosen as Tania's main model) and inclusionai/ling-3.2-flash:free (candidate fallback for lesson 8.3).
   nvidia/nemotron-3-ultra-550b-a55b:free gave a 404 "Free model training violation"; google/gemma-4-31b-it:free gave a 429.
   To find current candidates, query OpenRouter's public models API (/api/v1/models) and keep ids ending in ":free" whose supported_parameters include "tools". Test each with one hermes chat call.

2. `limactl shell <vm> cmd...` sends the command over SSH, which joins the arguments and re-parses them: nested quotes break ("unexpected EOF while looking for matching") and $vars expand too early.
   Fix: send multi-line scripts over stdin (limactl shell tania-box sudo -iu agent bash -l <<'EOF' ... EOF), or put a script file on the VM and run it by absolute path. Commands for the human (secret entry) use a script file on the VM: /home/agent/set-openrouter-key.sh.

3. Hermes installed as v0.23.1 (stable), newer than the guide's last verified v0.22.3. Check config keys against the official docs.

4. On the 4 GiB VM, terminal.container_memory is set to 3072, below host RAM, instead of the excerpt's 4096.
