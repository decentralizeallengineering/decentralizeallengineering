# decentralizeallengineering

Small, tested tools for working with coding agents (Claude Code mostly), office files and a homelab LLM rig. Built while developing, used every day. Most are one standard-library Python package; all are Apache-2.0, have CI and a tagged release.

## Start here

| repo | what it does | try it |
|---|---|---|
| [codeindex](https://github.com/decentralizeallengineering/codeindex) | Local code index for agents: where a symbol is defined, who calls it, which tests cover it. Skill plus MCP server. | `claude plugin install codeindex@decentralizeallengineering` |
| [zoomout](https://github.com/decentralizeallengineering/zoomout) | When an agent is stuck, restate the goal and choose: continue, pivot or simplify. | `claude plugin install zoomout@decentralizeallengineering` |
| [pacekeeper](https://github.com/decentralizeallengineering/pacekeeper) | Claude Code usage pacing from the real 5h and 7d meters: targets, spend by project, a wind-down hook. | `pip install git+https://github.com/decentralizeallengineering/pacekeeper` |

The two plugin lines need this marketplace once:

    claude plugin marketplace add decentralizeallengineering/decentralizeallengineering

Python tools install with `pip install git+https://github.com/decentralizeallengineering/<repo>`; single-file tools say so in their README.

## Agent quality and evals

| repo | what it does |
|---|---|
| [donegate](https://github.com/decentralizeallengineering/donegate) | Stop hook: no "done" unless a test ran after the last edit. |
| [taskmine](https://github.com/decentralizeallengineering/taskmine) | Mine benchmark tasks from git history: tests red at the parent, green at the fix. |
| [toolcensus](https://github.com/decentralizeallengineering/toolcensus) | Count an agent's real tool calls; check them against another tool set (MCP, OpenAI, Anthropic). |
| [freshlook](https://github.com/decentralizeallengineering/freshlook) | Independent audit of a repo by a clean agent that sees only code and intent. |
| [anti-lobotomy](https://github.com/decentralizeallengineering/anti-lobotomy) | Audit a Claude Code setup for silent context loss. |
| [intentpin](https://github.com/decentralizeallengineering/intentpin) | Pin your own words into every session start and compaction. |
| [breakthroughs](https://github.com/decentralizeallengineering/breakthroughs) | Several cheap agents brainstorm; one stronger agent scores the ideas. |
| [oldest-asks](https://github.com/decentralizeallengineering/oldest-asks) | Find what you asked your agents for that was never delivered, oldest first. |

## Agent cost

| repo | what it does |
|---|---|
| [turnthrift](https://github.com/decentralizeallengineering/turnthrift) | Fewer turns: run many reads in one call; hooks nudge batching and short replies. |
| [leanagents](https://github.com/decentralizeallengineering/leanagents) | Route subagents to small-prompt types and cheaper models. |
| [autocontext](https://github.com/decentralizeallengineering/autocontext) | Pick context window and autocompact threshold from measured cost. |
| [hushwire](https://github.com/decentralizeallengineering/hushwire) | Cut cross-session agent messages: status-only gate, digests, stats. |
| [escalator](https://github.com/decentralizeallengineering/escalator) | Cheap-first patches: a local model drafts, a stronger model fixes on red. |
| [qsum](https://github.com/decentralizeallengineering/qsum) | Extractive digests of long files through a local OpenAI-compatible endpoint. |

## Many sessions at once

| repo | what it does |
|---|---|
| [fleetwarden](https://github.com/decentralizeallengineering/fleetwarden) | Guardrail hooks and a launcher: protected dirs, rm and wait guards, agent routing. |
| [supra-orchestrator](https://github.com/decentralizeallengineering/supra-orchestrator) | One orchestrator for many sessions: order ledger, cadence, escalation. |
| [landbot](https://github.com/decentralizeallengineering/landbot) | Local merge queue for agent branches: batch, gate, bisect, land. |
| [billet](https://github.com/decentralizeallengineering/billet) | Hand a long session over to a fresh successor with a checked brief. |
| [tickwise](https://github.com/decentralizeallengineering/tickwise) | Adaptive tick intervals: slow when nothing changes, fast on change. |
| [diplomat](https://github.com/decentralizeallengineering/diplomat) | One idle watcher session per machine: alarms, load, tmux keepalive. |
| [opsledger](https://github.com/decentralizeallengineering/opsledger) | Split a big order into deduped asks with evidence-backed status. |

## Office files

| repo | what it does |
|---|---|
| [xlsxops](https://github.com/decentralizeallengineering/xlsxops) | Excel operations for LLM tool calls, with JSON schemas and safe saves. |
| [docxops](https://github.com/decentralizeallengineering/docxops) | Word operations for LLM tool calls, including a real table of contents. |
| [pdfops](https://github.com/decentralizeallengineering/pdfops) | PDF text, tables, merge, split and form fill for LLM tool calls. |
| [officecheck](https://github.com/decentralizeallengineering/officecheck) | Grade .docx, .xlsx, .pptx and .pdf outputs against a JSON spec, no model judge. |
| [fakepii-docs](https://github.com/decentralizeallengineering/fakepii-docs) | Fake-PII office documents with ground truth, to test maskers. |

## Homelab LLM rig

| repo | what it does |
|---|---|
| [llm-rig](https://github.com/decentralizeallengineering/llm-rig) | Local LLM servers in libvirt VMs with GPU passthrough. |
| [gpu-handoff](https://github.com/decentralizeallengineering/gpu-handoff) | Move a GPU between a VM and the host without a reboot. |
| [vmlease](https://github.com/decentralizeallengineering/vmlease) | Lease-based VM orchestration; a reaper reclaims. |
| [modelstage](https://github.com/decentralizeallengineering/modelstage) | Staged GGUF model rollout with health gate and rollback. |
| [gsched](https://github.com/decentralizeallengineering/gsched) | GPU airtime scheduler with leases. |
| [jobq](https://github.com/decentralizeallengineering/jobq) | Heavy jobs in cgroup slices, one queue across machines. |
| [rigwatch](https://github.com/decentralizeallengineering/rigwatch) | GPU and VM safety: temperature, RAM and job guards. |
| [nascare](https://github.com/decentralizeallengineering/nascare) | NAS care: heat, spin-down, SMART, ZFS error growth. |
| [corsair-fans](https://github.com/decentralizeallengineering/corsair-fans) | Temperature-driven fans for a Corsair Commander Core on Linux. |

## Small utilities

| repo | what it does |
|---|---|
| [trash30](https://github.com/decentralizeallengineering/trash30) | A trash folder that empties itself after 30 days. |
| [uistrings](https://github.com/decentralizeallengineering/uistrings) | Pull UI strings from HTML and JS; flag filler, emoji, long labels. |

Issues and pull requests are welcome on each repo. License: Apache-2.0.
