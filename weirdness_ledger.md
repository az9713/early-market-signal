# Weirdness Ledger

Use this file to capture behavior that feels too intense, too manual, or too strange for the current market category. Do not polish these entries too early. The point is to preserve evidence before it becomes obvious.

## Entry Template

```markdown
## Signal ID: S___

**Date captured:** YYYY-MM-DD
**Behavioral frontier:** 
**Community/source:** 
**URL/evidence:** 
**Observed behavior:** 
**Why it is weird:** 
**Pain behind the behavior:** 
**Current workaround:** 
**Tool/process being replaced:** 
**Possible product wedge:** 
**Confidence:** low / medium / high
**Next action:** ignore / watch / score / interview users / test concierge offer

### Evidence Notes

- Exact quote or paraphrase with URL:
- Repeated by other users? yes / no / unclear
- Any tutorial/script/plugin/fork/template? yes / no / unclear

### Follow-Up Questions

- Who experiences this most intensely?
- What breaks if the workaround disappears?
- What would the user pay to avoid doing this manually?
- Is this a temporary bug or a durable workflow gap?
```

## Seed Entry

## Signal ID: S001

**Date captured:** 2026-05-12
**Behavioral frontier:** People restructuring real software work around AI coding agents despite memory, reliability, and workflow-control gaps.
**Community/source:** Claude Code, Codex, Cursor, and AI coding communities.
**URL/evidence:** Start with GitHub issue trackers and Reddit/forum threads listed in `community_tracking_targets.md`.
**Observed behavior:** Developers create memory files, hooks, custom handoff docs, issue-search rituals, and local process rules to keep coding agents useful across multi-step work.
**Why it is weird:** Users are willing to add process overhead around a tool that is supposed to reduce process overhead.
**Pain behind the behavior:** Agent context loss, stale docs, incomplete task recovery, unclear reasoning trace, and unreliable long-running execution.
**Current workaround:** Manual `AGENTS.md`/project-memory files, custom scripts, checklists, hooks, and human review gates.
**Tool/process being replaced:** Human project manager notes, manual code review checklists, pair-programming context transfer, and ad hoc dev journals.
**Possible product wedge:** Agent memory and handoff layer for solo technical founders or small teams running multi-week coding-agent projects.
**Confidence:** medium
**Next action:** score and interview users

### Evidence Notes

- Exact quotes still need to be captured from specific issue URLs and forum threads.
- Repeated by other users? unclear until scanned.
- Any tutorial/script/plugin/fork/template? likely, but must be verified per source.

### Follow-Up Questions

- Which users maintain these files because they must, not because they enjoy tooling?
- What failures happen when the memory layer is missing?
- Does this replace an existing paid tool or just improve a personal workflow?
- Would a user pay for managed memory, recovery, and handoff, or only use a free template?

---

## Signal ID: S002

**Date captured:** 2026-05-12
**Behavioral frontier:** People maintaining memory files around AI coding agents.
**Community/source:** Hacker News (multiple Show HN threads), DEV Community, Medium
**URL/evidence:** https://news.ycombinator.com/item?id=46126066 | https://dev.to/sammiihk/i-built-a-self-managing-memory-system-for-claude-code-and-it-changed-how-i-work-3208 | https://medium.com/@malikchohra/i-built-a-memory-os-after-claude-code-hallucinated-42-of-my-code-1896334b9cfc
**Observed behavior:** Developers are building production-grade memory infrastructure (SQLite proxies, vector databases, knowledge graphs) on top of AI coding agents to compensate for session amnesia. One tool (grov) intercepts API calls and stores reasoning in SQLite. Another (A-MEM) uses ChromaDB with zettelkasten linking. A third (claude-brain) has run across 1,321 sessions and 67,000+ messages across 9 projects.
**Why it is weird:** The tool is supposed to reduce engineering overhead. Users are adding significant new engineering projects to keep it useful. A developer built an entire "memory OS" after their agent hallucinated 42% of their code.
**Pain behind the behavior:** Agent re-explores already-analyzed files each session (10-11 minute overhead becoming 1-2 minutes with memory fix); session amnesia forces complete context rebuilding; hallucination rate climbs without grounded memory.
**Current workaround:** grov (SQLite proxy for API interception); A-MEM (ChromaDB + zettelkasten); claude-brain (1,321 sessions, 67k+ messages); MEMORY.md as routing table to topic files; two-file injection system.
**Tool/process being replaced:** Manual session summaries; keeping Claude sessions alive continuously to avoid context loss; re-explaining project context at the start of every session.
**Possible product wedge:** Automatic context capture + injection with zero manual effort; managed memory-as-a-service for coding agents; anti-hallucination memory layer with session handoff.
**Confidence:** high
**Next action:** interview users

### Evidence Notes

- "I kept watching Claude Code spend 10 minutes re-exploring files it already analyzed yesterday." (HN, grov author)
- "I built a memory OS after Claude Code hallucinated 42% of my code." (Medium, @malikchohra)
- "I spend hours with claude digging into some functionality, and it was frustrating that I have to start from scratch next day/session." (HN, A-MEM author)
- grov: ~250 npm downloads with no promotion — organic demand
- claude-brain: 1,321 sessions, 67,000+ messages across 9 projects — sustained high-investment usage
- Cluster of 5+ "I built X for Claude Code memory" posts on DEV Community and Medium in 2026
- Repeated by other users? yes — multiple independent builders, multiple HN threads
- Any tutorial/script/plugin/fork/template? yes — grov, A-MEM, claude-brain, private-journal-mcp, claude-session-memory, Hmem (MCP server)

### Follow-Up Questions

- Do users who built these tools use them daily or abandon them after initial excitement?
- What percentage of the pain is session amnesia vs. within-session context degradation?
- Would users pay for a managed version or only use open-source?
- Is the hallucination problem (42%) causal from missing memory, or correlated?

---

## Signal ID: S003

**Date captured:** 2026-05-12
**Behavioral frontier:** People maintaining memory files around AI coding agents.
**Community/source:** Hacker News (Show HN: Stop Claude Code from forgetting everything)
**URL/evidence:** https://news.ycombinator.com/item?id=46426624
**Observed behavior:** Individual developers are maintaining global CLAUDE.md files of 15,000 tokens — larger than most real project documentation — as personal OS-level agent configuration. One user (BonoboIO) maintains this as a global ~/.claude/CLAUDE.md with coding conventions and custom slash commands. Others maintain strict multi-file systems with length limits (under 250 lines per file) to prevent compliance degradation.
**Why it is weird:** 15,000 tokens of behavioral instructions for a coding assistant is more investment than most companies put into onboarding documentation. The user is essentially writing a personal employee handbook for an AI. This is also a negative signal about the tool: it only works well with this much manual configuration.
**Pain behind the behavior:** Without a curated global memory file, Claude reverts to defaults and loses all learned conventions, preferences, and project patterns. Users discovered empirically that beyond 250 lines, instruction compliance degrades — so they manage file sizes actively.
**Current workaround:** Global ~/.claude/CLAUDE.md with thousands of tokens; multi-file systems (CLAUDE.md + FEATURE_IMPL_PLAN.md + per-feature docs); git-based /handoff /sync /engineering commands for session capture and routing.
**Tool/process being replaced:** Human onboarding docs; pair-programming context transfer; ad hoc session notes.
**Possible product wedge:** Auto-generated personalized CLAUDE.md from observed agent behavior; role-specific memory templates (solo founder, senior engineer, PM); memory file compliance monitoring and auto-pruning.
**Confidence:** high
**Next action:** score

### Evidence Notes

- BonoboIO: "15k-token global ~/.claude/CLAUDE.md with coding conventions and custom slash commands" — maintaining this across all projects (HN thread)
- wfn: "FEATURE_IMPL_PLAN.md, per-feature docs in feature-impl-plans/ directory, CLAUDE.md restricted to code references under 250 lines" (HN thread)
- ossa-ma: Built a local git-based system with /handoff, /sync, /engineering commands routing session captures into organized markdown files (HN thread)
- Repeated by other users? yes — multiple HN commenters describe similar multi-file strategies
- Any tutorial/script/plugin/fork/template? yes — git-based handoff system, multi-file conventions documented in comments

### Follow-Up Questions

- How much time do these users spend maintaining their memory files per week?
- Do they share these files with teammates or keep them personal?
- What triggers a CLAUDE.md update — errors, regressions, or proactive improvement?
- Would they pay for automated maintenance vs. a better template?

---

## Signal ID: S004

**Date captured:** 2026-05-12
**Behavioral frontier:** People maintaining memory files around AI coding agents.
**Community/source:** Cursor Community Forum
**URL/evidence:** https://forum.cursor.com/t/agents-have-lost-access-to-memory-capability/143310
**Observed behavior:** After Cursor's native memory feature broke repeatedly and was eventually removed, users migrated to manually maintained project.md files, project rules, and the OpenSpec framework. One user reports the feature was "broken for months" before removal. Users are now maintaining workaround memory systems that replicate what the product promised natively.
**Why it is weird:** Users kept using Cursor after the memory feature broke for months, then after it was removed — building manual workarounds rather than switching tools. The product failed a core promise and users absorbed the cost themselves rather than leaving.
**Pain behind the behavior:** Without memory persistence, every session requires re-explaining project context; agents cannot autonomously update project knowledge; progress is lost when sessions end.
**Current workaround:** Convert memories to project rules; create project.md files with notes and specifications; use OpenSpec framework for spec-driven development instead of agent memory; downgrade to v2.0.77.
**Tool/process being replaced:** Native Cursor memory feature; per-session re-explanation of project state.
**Possible product wedge:** Reliable cross-session memory that survives product updates and tool switches; memory portability across IDE versions and tools.
**Confidence:** medium
**Next action:** interview users

### Evidence Notes

- Maor Azoulay: "memories persistence has been broken for me for months" (Cursor forum)
- Maor Azoulay: "instead of fixing it they remove the feature altogether" (Cursor forum)
- Brandon Maness: "the agent could not remember things I had told it to remember" (Cursor forum)
- Dean Rie (Cursor support): "a known recurring issue that's affecting multiple users" (Cursor forum)
- Repeated by other users? yes — 4-5 direct reports; support acknowledges as known recurring issue across multiple versions
- Any tutorial/script/plugin/fork/template? yes — OpenSpec framework, project rules convention, project.md pattern

### Follow-Up Questions

- Did these users migrate to a different tool or stay on Cursor with manual workarounds?
- How much time do they spend maintaining project.md files as a Cursor memory replacement?
- Is this a Cursor-specific failure or a pattern across all AI coding tools?
- Would they pay for a memory layer that works across tools regardless of native support?

---

## Signal ID: S005

**Date captured:** 2026-05-12
**Behavioral frontier:** People maintaining memory files around AI coding agents.
**Community/source:** anthropics/claude-code GitHub Issues
**URL/evidence:** https://github.com/anthropics/claude-code/issues/4588 | https://github.com/anthropics/claude-code/issues/6235 | https://github.com/anthropics/claude-code/issues/25882 | https://github.com/anthropics/claude-code/issues/34235
**Observed behavior:** Sub-agents in Claude Code are stateless — they must be told the same domain rules in every prompt. Users are manually prepending critical instructions to every Task tool invocation, e.g. "CRITICAL: Use Unicode escape sequences (\uXXXX) for Java properties / Check existing translations for terminology consistency." This is happening at the per-call level, not the per-session level.
**Why it is weird:** Users are paying to run AI agents and then spending engineering time writing the same manual instructions into every individual agent call — the equivalent of texting your assistant the same memo every morning. The issue was closed as a duplicate, referencing 6+ other issues (#4182, #1770, #3013, #87, #1813, #3081), which means this exact pain has surfaced independently many times.
**Pain behind the behavior:** Sub-agents have no memory of previous successful patterns; domain expertise resets with every call; cognitive load stays on the user even when agents handle execution.
**Current workaround:** Manually prepending CRITICAL instructions to every prompt; maintaining prompt snippets as personal documentation; some users creating wrapper scripts to auto-inject standard instructions.
**Tool/process being replaced:** Human expert hand-holding; repeated manual prompt engineering; institutional knowledge that would normally live in team documentation.
**Possible product wedge:** Agent-specific persistent memory files (e.g., ui-translator-memory.md, code-reviewer-memory.md); cross-session specialization layer that accumulates domain knowledge from successful runs.
**Confidence:** high
**Next action:** score

### Evidence Notes

- Issue text: "Currently, ui-translator requires this in every prompt: CRITICAL: Use Unicode escape sequences (\uXXXX) for Java properties / Check existing translations for terminology consistency" (GitHub #4588)
- Closed as duplicate referencing: #4182, #1770, #3013, #87, #1813, #3081 — 6+ independent reports of the same pain
- Repo has 123k stars and 5k+ issues — large base of affected developers
- Feature requests for AGENTS.md support filed as #6235, #34235, #25882 — multiple independent requests for persistent agent instruction files
- Repeated by other users? yes — closed as duplicate with 6 cross-references
- Any tutorial/script/plugin/fork/template? unclear — workarounds are prompt-level, not yet tooled

### Follow-Up Questions

- Are users who hit this building wrapper scripts, or manually copy-pasting every time?
- Does this pain scale with the number of specialized agents a user runs?
- Would agent-specific memory files solve this, or is the real need a learning mechanism from outcomes?
- What is the cost (time, errors) when users forget to include the critical instructions?
