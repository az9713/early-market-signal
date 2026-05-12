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

