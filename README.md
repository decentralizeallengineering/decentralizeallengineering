# decentralizeallengineering

Small, tested, Apache-2.0 tools from running a fleet of Claude Code agents and local LLMs on our own hardware every day. Mostly standard-library Python. Each repo stands alone, has CI, and has a v0.1.0 release.

## Install as Claude Code plugins

    claude plugin marketplace add decentralizeallengineering/decentralizeallengineering
    claude plugin install zoomout@decentralizeallengineering
    claude plugin install codeindex@decentralizeallengineering

zoomout: step back when an agent is stuck. codeindex: where is it defined, who calls it, which tests cover it (skill plus MCP server).

## Start here

Five tools that work on their own:

| repo | the problem it solves |
|---|---|
| [donegate](https://github.com/decentralizeallengineering/donegate) | Your coding agent says "fixed, tests pass" without running a test. A Stop hook blocks that. |
| [codeindex](https://github.com/decentralizeallengineering/codeindex) | Agents grep and read whole files to find a definition. One local index answers where, who calls, which tests. |
| [turnthrift](https://github.com/decentralizeallengineering/turnthrift) | Many small reads cost many model turns. `burst` runs them in one call. |
| [xlsxops](https://github.com/decentralizeallengineering/xlsxops) | LLM tool calls that edit Excel files safely: JSON-schema tools, checked formulas. |
| [docxops](https://github.com/decentralizeallengineering/docxops) | LLM tool calls that edit Word files, including a real table of contents. |

## Agent cost and usage

Measure Claude Code usage and spend fewer tokens for the same work.

| repo | what it does |
|---|---|
| [pacekeeper](https://github.com/decentralizeallengineering/pacekeeper) | Claude Code usage pacing: 5h and 7d meters from the status line (also a one-line model, context and meters status line), %/hour targets, budgets, spend by project, and a wind-down hook. |
| [turnthrift](https://github.com/decentralizeallengineering/turnthrift) | Fewer turns, shorter replies: burst runs many reads in one call; hooks nudge batching and brevity in Claude Code. |
| [leanagents](https://github.com/decentralizeallengineering/leanagents) | Route Claude Code subagents to small-prompt agent types and cheaper models automatically. |
| [autocontext](https://github.com/decentralizeallengineering/autocontext) | Let an agent pick its own context window and autocompact threshold from measured cost and re-reads. |
| [hushwire](https://github.com/decentralizeallengineering/hushwire) | Cut cross-session agent messages: status-only gate, digests, message stats. |
| [escalator](https://github.com/decentralizeallengineering/escalator) | Cheap-first patch pipeline: a local model drafts, a gate checks, a reviewer reviews, a stronger model fixes on red. |
| [qsum](https://github.com/decentralizeallengineering/qsum) | Extractive digests of long files through a local OpenAI-compatible endpoint. |
| [codeindex](https://github.com/decentralizeallengineering/codeindex) | Fast local code index for agents to find symbols and files without an LLM. |

## Session orchestration

Run, schedule and hand over many long-running Claude Code sessions.

| repo | what it does |
|---|---|
| [supra-orchestrator](https://github.com/decentralizeallengineering/supra-orchestrator) | Run a fleet of Claude Code agent sessions from one orchestrator: order ledger, cadence, escalation. |
| [fleetwarden](https://github.com/decentralizeallengineering/fleetwarden) | Guardrail hooks and a session launcher for running many Claude Code sessions: cadence, agent routing, protected dirs and protected sets, rm, wait, hang and kill guards, a Haiku context cap, intent injection. |
| [tickwise](https://github.com/decentralizeallengineering/tickwise) | Adaptive tick intervals for long-running agent sessions: slow down when nothing changes, speed up on change. |
| [diplomat](https://github.com/decentralizeallengineering/diplomat) | One idle agent session per machine: watch, triage alarms, relieve load, CPU efficiency, plus tmux keepalive and an idle-session backstop. |
| [opsledger](https://github.com/decentralizeallengineering/opsledger) | Turn a big multi-part order into deduped, deconflicted asks with evidence-backed status and a percent-complete ledger. |
| [oldest-asks](https://github.com/decentralizeallengineering/oldest-asks) | Find what a person asked their agents for that was never delivered, oldest first, with at most 5 Haiku workers. Includes `hist`, a read-only search of old commits and transcripts before you rebuild something. |
| [landbot](https://github.com/decentralizeallengineering/landbot) | Local merge queue for AI-agent branches: batch, gate, bisect, land. No CI service needed. |
| [billet](https://github.com/decentralizeallengineering/billet) | Billet turnover for long-running Claude Code sessions: performance-based degradation check, verified turnover brief, clean successor. |

## Agent quality

Keep agents on your stated intent, verify that work is done, and get stuck agents moving.

| repo | what it does |
|---|---|
| [intentpin](https://github.com/decentralizeallengineering/intentpin) | Pin the person's own words into every Claude Code session start and compaction, newest wins. |
| [anti-lobotomy](https://github.com/decentralizeallengineering/anti-lobotomy) | Audit a Claude Code setup for silent context loss: compactions, truncated reads, silent model rewrites, rule bloat and alarm noise. |
| [donegate](https://github.com/decentralizeallengineering/donegate) | Claude Code Stop hook: no 'done' without a test run after the last edit; replies kept short. |
| [zoomout](https://github.com/decentralizeallengineering/zoomout) | Step back when an agent is stuck: how top practitioners would approach it, then continue, pivot or simplify. |
| [freshlook](https://github.com/decentralizeallengineering/freshlook) | Escalate a project to a fresh, independent auditor that sees only code and intent; ranks complexity to remove. |
| [breakthroughs](https://github.com/decentralizeallengineering/breakthroughs) | 3-10 cheap agents brainstorm anything that could work on a project; one stronger agent scores reliability. |

## Homelab and GPU

Run local LLM servers on your own hardware without cooking it.

| repo | what it does |
|---|---|
| [llm-rig](https://github.com/decentralizeallengineering/llm-rig) | Run local LLM servers in libvirt VMs with GPU passthrough: bring up, provision, status, benchmark. |
| [vmlease](https://github.com/decentralizeallengineering/vmlease) | Lease-based libvirt VM orchestration for agent fleets: agents lease, a reaper reclaims, no hand virsh. |
| [gpu-handoff](https://github.com/decentralizeallengineering/gpu-handoff) | Hand a passthrough GPU between a libvirt VM and the Linux host at runtime, no reboot: precheck, dry-run, rollback. |
| [modelstage](https://github.com/decentralizeallengineering/modelstage) | Staged rollout of local LLM model files (GGUF) across machines: sha-verified, health-gated switch, automatic rollback. |
| [gsched](https://github.com/decentralizeallengineering/gsched) | GPU airtime scheduler with leases, plus a queue wrapper that books GPU time. |
| [jobq](https://github.com/decentralizeallengineering/jobq) | One door for heavy jobs across nodes, each run in its own cgroup slice with limits and a queue. |
| [rigwatch](https://github.com/decentralizeallengineering/rigwatch) | Homelab GPU and VM safety: temperature guards, VM and GPU leases, RAM guard, heavy-job enforcer, and a boot check for LLM containers that started without CUDA. |
| [nascare](https://github.com/decentralizeallengineering/nascare) | NAS care on Linux: heat policy, spin-down, SMART and pool health, ZFS error-growth alerts. |
| [corsair-fans](https://github.com/decentralizeallengineering/corsair-fans) | Temperature-driven fan control for a Corsair Commander Core on Linux, using the liquidctl CLI. |

## UI copy checks

| repo | what it does |
|---|---|
| [uistrings](https://github.com/decentralizeallengineering/uistrings) | Extract user-visible strings from static HTML and JS and flag filler words, emoji, exclamation marks, long labels and broken text such as `undefined`. |

## Office files

Reliable PDF, Word and Excel operations for LLM tool layers, plus grading and test data.

| repo | what it does |
|---|---|
| [pdfops](https://github.com/decentralizeallengineering/pdfops) | Python library of PDF operations for LLM agents: extract text and tables, merge, split and fill forms, with JSON schemas for tool calls. |
| [docxops](https://github.com/decentralizeallengineering/docxops) | Word .docx operations for LLM agents in Python, including a real table of contents, with JSON-schema tool definitions. |
| [xlsxops](https://github.com/decentralizeallengineering/xlsxops) | Excel .xlsx operations for LLM agents in Python (openpyxl), with JSON-schema tool definitions and safe saves. |
| [officecheck](https://github.com/decentralizeallengineering/officecheck) | Deterministic grader for .docx, .xlsx, .pptx and .pdf outputs: a JSON spec goes in, pass or fail per check comes out, no model judge. |
| [fakepii-docs](https://github.com/decentralizeallengineering/fakepii-docs) | Synthetic test corpus generator for PII masking: fake personal data in docx, xlsx, pptx, pdf and csv, with ground truth and a leak scorer. |

Contributions: see each repo's CONTRIBUTING.md. License: Apache-2.0.
