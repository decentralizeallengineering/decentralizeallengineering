# decentralizeallengineering

Small, tested, Apache-2.0 tools from running a fleet of Claude Code agents and local LLMs on our own hardware every day. Mostly standard-library Python. Each repo stands alone.

## Run a fleet of Claude Code agents

| repo | what it does |
|---|---|
| [supra-orchestrator](https://github.com/decentralizeallengineering/supra-orchestrator) | Run a fleet of Claude Code agent sessions from one orchestrator: order ledger, cadence, escalation |
| [fleetwarden](https://github.com/decentralizeallengineering/fleetwarden) | Guardrail hooks and a session launcher for running many Claude Code sessions: cadence, agent routing, protected dirs, rm and wait guards, intent injection. |
| [hushwire](https://github.com/decentralizeallengineering/hushwire) | Cut cross-session agent messages: status-only gate, digests, message stats |
| [tickwise](https://github.com/decentralizeallengineering/tickwise) | Adaptive tick intervals for long-running agent sessions: slow down when nothing changes, speed up on change |
| [diplomat](https://github.com/decentralizeallengineering/diplomat) | One idle agent session per machine: watch, triage alarms, relieve load, CPU efficiency |
| [escalator](https://github.com/decentralizeallengineering/escalator) | Cheap-first patch pipeline: a local model drafts, a gate checks, a reviewer reviews, a stronger model fixes on red. |
| [landbot](https://github.com/decentralizeallengineering/landbot) | Local merge queue for AI-agent branches: batch, gate, bisect, land. No CI service needed. |
| [opsledger](https://github.com/decentralizeallengineering/opsledger) | Turn a big multi-part order into deduped, deconflicted asks with evidence-backed status and a percent-complete ledger. |
| [oldest-asks](https://github.com/decentralizeallengineering/oldest-asks) | Find what a person asked their agents for that was never delivered, oldest first, with at most 5 Haiku workers |

## Keep agents honest and on task

| repo | what it does |
|---|---|
| [intentpin](https://github.com/decentralizeallengineering/intentpin) | Pin the person's own words into every Claude Code session start and compaction, newest wins |
| [anti-lobotomy](https://github.com/decentralizeallengineering/anti-lobotomy) | Audit a Claude Code setup for silent context loss: compactions, truncated reads, silent model rewrites, rule bloat and alarm noise. |
| [donegate](https://github.com/decentralizeallengineering/donegate) | Claude Code Stop hook: no 'done' without a test run after the last edit; replies kept short |
| [zoomout](https://github.com/decentralizeallengineering/zoomout) | Step back when an agent is stuck: how top practitioners would approach it, then continue, pivot or simplify |
| [freshlook](https://github.com/decentralizeallengineering/freshlook) | Escalate a project to a fresh, independent auditor that sees only code and intent; ranks complexity to remove |
| [breakthroughs](https://github.com/decentralizeallengineering/breakthroughs) | 3-10 cheap agents brainstorm anything that could work on a project; one stronger agent scores reliability |

## Spend fewer tokens

| repo | what it does |
|---|---|
| [turnthrift](https://github.com/decentralizeallengineering/turnthrift) | Fewer turns, shorter replies: burst runs many reads in one call; hooks nudge batching and brevity in Claude Code. |
| [leanagents](https://github.com/decentralizeallengineering/leanagents) | Route Claude Code subagents to small-prompt agent types and cheaper models automatically |
| [autocontext](https://github.com/decentralizeallengineering/autocontext) | Let an agent pick its own context window and autocompact threshold from measured cost and re-reads |
| [pacekeeper](https://github.com/decentralizeallengineering/pacekeeper) | Claude Code usage pacing: 5h and 7d meters from the status line, %/hour targets, budgets, spend by project, and a wind-down hook. |
| [qsum](https://github.com/decentralizeallengineering/qsum) | Extractive digests of long files through a local OpenAI-compatible endpoint. |
| [codeindex](https://github.com/decentralizeallengineering/codeindex) | Fast local code index for agents to find symbols and files without an LLM. |

## Hardware, VMs and local LLMs

| repo | what it does |
|---|---|
| [llm-rig](https://github.com/decentralizeallengineering/llm-rig) | Run local LLM servers in libvirt VMs with GPU passthrough: bring up, provision, status, benchmark. |
| [vmlease](https://github.com/decentralizeallengineering/vmlease) | Lease-based libvirt VM orchestration for agent fleets: agents lease, a reaper reclaims, no hand virsh |
| [gpu-handoff](https://github.com/decentralizeallengineering/gpu-handoff) | Hand a passthrough GPU between a libvirt VM and the Linux host at runtime, no reboot: precheck, dry-run, rollback |
| [modelstage](https://github.com/decentralizeallengineering/modelstage) | Staged rollout of local LLM model files (GGUF) across machines: sha-verified, health-gated switch, automatic rollback |
| [gsched](https://github.com/decentralizeallengineering/gsched) | GPU airtime scheduler with leases, plus a queue wrapper that books GPU time. |
| [jobq](https://github.com/decentralizeallengineering/jobq) | One door for heavy jobs across nodes, each run in its own cgroup slice with limits and a queue. |
| [rigwatch](https://github.com/decentralizeallengineering/rigwatch) | Homelab GPU and VM safety: temperature guards, VM and GPU leases, RAM guard, heavy-job enforcer, and a boot check for LLM containers that started without CUDA. |
| [nascare](https://github.com/decentralizeallengineering/nascare) | NAS care on Linux: heat policy, spin-down, SMART and pool health, ZFS error-growth alerts. |
| [corsair-fans](https://github.com/decentralizeallengineering/corsair-fans) | Temperature-driven fan control for a Corsair Commander Core on Linux, using the liquidctl CLI. |

Contributions: see each repo's CONTRIBUTING.md. License: Apache-2.0.
