# Examples: Agentic Workflow Infrastructure

These examples show how to use the workflow. They are starting hypotheses, not confirmed market conclusions. Replace seed evidence with exact URLs, quotes, and interviews during live research.

## Example 1: Agent Memory And Handoff

### Weirdness Ledger Entry

**Signal ID:** S001
**Behavioral frontier:** People restructuring real software work around AI coding agents despite memory, reliability, and recovery gaps.

**Observed behavior:** Developers create persistent memory files, repo instructions, handoff docs, and custom checklists to keep coding agents aligned across multi-step work.

**Why it is weird:** The tool is supposed to reduce coordination overhead, but intense users add their own coordination layer around it.

**Pain behind the behavior:** Agents forget project state, lose thread continuity, drift from prior decisions, or produce changes that are hard to review after long sessions.

**Current workaround:** `AGENTS.md`, project memory files, custom prompts, issue-search rituals, hooks, and manual summaries.

**Possible product wedge:** Managed memory, recovery, and handoff layer for solo technical founders and small teams using coding agents on multi-week projects.

**Next action:** Interview users who maintain custom memory files or hooks.

### Scorecard Example

| Criterion | Score | Reason |
| --- | ---: | --- |
| Rough UX tolerated | 2 | Users add process overhead because the outcome is valuable. |
| User tutorials | 1 | Many users share tips, but exact evidence should be collected. |
| Incumbent replacement | 1 | Replaces some manual notes/review processes, but budget is unclear. |
| API/integration requests | 1 | Likely present around hooks and workflow integrations. |
| Hacked use cases | 2 | Custom files and hooks are hacked workflow infrastructure. |
| Vocabulary forming | 1 | Terms like memory, context, handoff, compaction, and hooks recur. |
| Copycats appearing | 1 | Templates and wrapper tools may emerge. Must verify. |
| Outside curiosity growing | 1 | Non-users ask how these workflows work. |
| **Total** | **10** | Early market candidate. |

### Interview Target

Find users who have written posts or issues about:

- Agent context loss
- Stale docs
- Hooks
- Session handoff
- Memory files
- Long-running coding-agent work

Ask:

```text
Could you show me the last time your agent lost project context or needed a handoff file to recover?
```

## Example 2: AI-Generated App Last-Mile Assembly

### Weirdness Ledger Entry

**Signal ID:** S002
**Behavioral frontier:** Nontechnical or semi-technical builders can generate app code but get stuck when the app needs to become a real product.

**Observed behavior:** Users can create a working local prototype with AI, then stall on auth, payments, deployment, databases, error handling, and iteration.

**Why it is weird:** AI makes the first 70% feel easy, which exposes a painful last-mile gap that previously stayed hidden behind "I cannot code."

**Pain behind the behavior:** The builder does not know how to transform generated code into a deployed, maintainable, secure app.

**Current workaround:** Asking Reddit/Discord, hiring freelancers, restarting projects, copying tutorials, using no-code tools, or abandoning prototypes.

**Possible product wedge:** Concierge or tool-assisted "ship my AI-generated app" service for solo founders.

**Next action:** Scan `r/vibecoding`, `r/VibeCodeDevs`, Vercel community, Supabase discussions, and YouTube tutorial comments.

### Scorecard Example

| Criterion | Score | Reason |
| --- | ---: | --- |
| Rough UX tolerated | 1 | Users tolerate broken generated code if it gets them closer. |
| User tutorials | 2 | Tutorial demand is visible in this category. |
| Incumbent replacement | 1 | Replaces freelancers or no-code paths for some users. |
| API/integration requests | 2 | Auth, payments, database, and deployment are integration-heavy. |
| Hacked use cases | 1 | Users stitch together tools manually. |
| Vocabulary forming | 1 | "Vibe coding" and "last mile" language is emerging. |
| Copycats appearing | 1 | Many tools claim to solve pieces. |
| Outside curiosity growing | 2 | Nontechnical founders are entering software creation. |
| **Total** | **11** | Early market candidate. |

### Concierge Offer

```text
I can take your AI-generated app from local prototype to deployed MVP with auth, database, payments, and basic error handling this week for $1,500. Interested?
```

## Example 3: Local/Private Agent Workspaces

### Weirdness Ledger Entry

**Signal ID:** S003
**Behavioral frontier:** Users tolerate difficult local model setup to keep sensitive AI workflows private.

**Observed behavior:** Users run local LLM stacks with Ollama, Open WebUI, LM Studio, custom scripts, local vector stores, and hardware-specific tuning.

**Why it is weird:** Users accept setup friction and worse performance to preserve privacy, control, offline access, or cost predictability.

**Pain behind the behavior:** Cloud AI tools are unacceptable for sensitive data, regulated workflows, proprietary code, or personal privacy.

**Current workaround:** DIY local model orchestration, scattered tutorials, GPU tuning, self-hosted UIs, and manual model selection.

**Possible product wedge:** One-click private agent workspace for sensitive workflows.

**Next action:** Track `r/LocalLLaMA`, Ollama issues, Open WebUI issues, Hugging Face forums, and homelab/privacy communities.

### Scorecard Example

| Criterion | Score | Reason |
| --- | ---: | --- |
| Rough UX tolerated | 2 | Setup friction is high, but users persist. |
| User tutorials | 2 | Tutorial culture is strong. |
| Incumbent replacement | 1 | Replaces some cloud AI usage, but not always. |
| API/integration requests | 1 | Integrations matter but vary by use case. |
| Hacked use cases | 2 | Heavy DIY workflow composition. |
| Vocabulary forming | 1 | Local-first, private AI, self-hosted AI recur. |
| Copycats appearing | 1 | Many tools compete, but wedges remain. |
| Outside curiosity growing | 1 | Privacy-aware users are entering. |
| **Total** | **11** | Early market candidate. |

## Example 4: Agent Observability And Evals

### Weirdness Ledger Entry

**Signal ID:** S004
**Behavioral frontier:** Teams want agents to do real work but cannot see enough to trust, debug, or improve them.

**Observed behavior:** Users add logs, traces, prompt snapshots, eval scripts, manual review checklists, and replay workflows around agents.

**Why it is weird:** Agent systems create a new debugging surface that conventional app logs do not fully explain.

**Pain behind the behavior:** It is hard to know what the agent saw, why it acted, where it failed, and whether changes improved behavior.

**Current workaround:** Manual logs, LangSmith-style traces, screenshots, JSONL archives, custom eval scripts, and human audit notes.

**Possible product wedge:** Lightweight observability and replay dashboard for coding agents and browser/computer-use agents.

**Next action:** Scan LangChain/LangGraph issues, Codex/Claude Code issues, HN discussions, and AI ops posts.

### Scorecard Example

| Criterion | Score | Reason |
| --- | ---: | --- |
| Rough UX tolerated | 1 | Users add manual instrumentation when stakes are high. |
| User tutorials | 1 | Examples exist but need specific evidence. |
| Incumbent replacement | 1 | Could replace generic logging or manual QA notes. |
| API/integration requests | 2 | Production users need integrations. |
| Hacked use cases | 2 | Custom tracing/eval scripts are common in serious use. |
| Vocabulary forming | 2 | Observability, evals, traces, replay, guardrails are stabilizing. |
| Copycats appearing | 2 | Many adjacent tools are appearing. |
| Outside curiosity growing | 1 | Builders ask how to make agents production-ready. |
| **Total** | **12** | Early market candidate. |

## Pattern To Look For Across Examples

The best signals are not the loudest. They are the ones where users already changed behavior.

Ask:

- What changed in the user's workflow?
- What roughness do they tolerate?
- What have they built around the product?
- What old process is dying?
- What new vocabulary keeps appearing?
- What would they pay to stop doing manually?

