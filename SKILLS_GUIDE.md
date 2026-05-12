# Early Market Signal Workflow — Skills Guide

This document explains how the workflow files were converted into Claude Code skills, what each skill does, and how to use them together.

## What Changed

The original workflow lived entirely in markdown reference files. Claude could use those files within a session if explicitly directed to, but they required manual prompting and offered no automatic triggering.

The seven skills below are now registered globally in `~/.claude/skills/`. Claude Code will recognize and invoke them automatically when the context matches — no prompts required to reference the files.

The original files (`README.md`, `USER_GUIDE.md`, `source_map.csv`, `weirdness_ledger.md`, `signal_scorecard.csv`, `community_tracking_targets.md`, `search_queries.md`, `power_user_interview_script.md`, `early_market_thesis_template.md`, `examples.md`) are unchanged and remain the authoritative data and reference layer. The skills read and write to those files.

---

## File-to-Skill Mapping

| Original File | Role | Used By |
|---|---|---|
| `community_tracking_targets.md` | Reference: where to look | `ems-scan` |
| `search_queries.md` | Reference: what to search | `ems-scan` |
| `source_map.csv` | Data: source evidence rows | `ems-scan` (writes), `ems-score`, `ems-cluster`, `ems-decide` (reads) |
| `weirdness_ledger.md` | Data: signal entries | `ems-scan` (writes), `ems-score`, `ems-cluster`, `ems-decide` (reads) |
| `signal_scorecard.csv` | Data: scored signals | `ems-score` (writes), `ems-cluster`, `ems-decide` (reads) |
| `power_user_interview_script.md` | Reference: interview structure | `ems-interview` |
| `early_market_thesis_template.md` | Template: thesis structure | `ems-thesis` |
| `examples.md` | Reference: worked examples | All skills (as context) |
| `README.md` | Reference: full workflow doctrine | All skills (doctrine) |
| `USER_GUIDE.md` | Reference: first-run walkthrough | All skills (as context) |

---

## The Seven Skills

### ems-scan
**When it triggers:** When you name a behavioral frontier and want evidence gathered.

Scans communities and web sources for behavioral evidence. Updates `source_map.csv` with source rows and `weirdness_ledger.md` with signal entries. Separates demand from hype using the evidence standards in `README.md`.

**Covers workflow steps:** Choose frontier → Scan communities → Log to source_map.csv → Log to weirdness_ledger.md

---

### ems-score
**When it triggers:** When you ask how strong a signal is, or reference a signal ID and scoring.

Applies the 0–16 rubric to a named signal. Reads only from captured evidence in `source_map.csv` and `weirdness_ledger.md` — does not infer. Updates `signal_scorecard.csv`.

**Covers workflow step:** Score signals

---

### ems-cluster
**When it triggers:** When you want to review accumulated signals, find patterns, or decide what to kill.

Groups signals by repeated pain across communities. Triages each cluster as noise, watchlist, interview candidate, or ready to promote to thesis. Does not create thesis files.

**Covers workflow step:** Cluster review (use after 10+ ledger entries)

---

### ems-interview
**When it triggers:** When a signal scores 9+ and you need to talk to users.

Drafts 5 targeted outreach messages and a structured interview plan. Uses `power_user_interview_script.md`. Every message references a specific post. Every question asks for observed behavior, not hypothetical opinions.

**Covers workflow step:** Interview power users

---

### ems-thesis
**When it triggers:** When a cluster has 3+ independent sources and is ready to be formalized.

Creates a `thesis-[name].md` file from `early_market_thesis_template.md`. Requires workaround evidence, a replacement target, and counterevidence. Does not create thesis files from single-community signals.

**Covers workflow step:** Convert clusters into theses

---

### ems-decide
**When it triggers:** When signals are accumulating without clear next actions.

Reviews all open signals and assigns exactly one state to each: ignore / watch / interview users / test concierge offer. Leaves no signal undecided.

**Covers workflow step:** Decide next action for every signal

---

### ems-concierge
**When it triggers:** When interviews have confirmed urgency and you want to test willingness to pay.

Drafts a specific, priced, time-bound manual offer. Does not ask "would you pay?" — makes a real offer. Explains how to interpret responses as signal strength evidence.

**Covers workflow step:** Test concierge offer

---

## The Full Loop

```
1. ems-scan       →  gather evidence, populate source_map.csv + weirdness_ledger.md
2. ems-score      →  rate signal strength 0–16, update signal_scorecard.csv
3. ems-cluster    →  group by pain, triage, kill noise, identify candidates
4. ems-decide     →  assign next action to every signal (no undecided entries)
5. ems-interview  →  draft outreach + interview plan for signals scoring 9+
6. ems-thesis     →  create thesis file when 3+ independent sources confirm pain
7. ems-concierge  →  draft priced offer when interviews confirm urgency
```

Steps 1–4 repeat as new scans add evidence. Steps 5–7 activate when a signal earns them.

---

## Workflow Examples

### Example A: Starting from scratch with a new behavioral frontier

**You say:**
> People are maintaining handwritten memory files around AI coding agents because the agents keep losing project context.

**Claude invokes `ems-scan`** — scans GitHub issues, Reddit, HN, and forum threads. Updates `source_map.csv` with 4 source rows and `weirdness_ledger.md` with S002. Reports strongest signal and suggests next action.

**You say:**
> Score S002.

**Claude invokes `ems-score`** — reads the ledger entries, applies the 0–16 rubric, updates `signal_scorecard.csv`. Reports: S002 scores 11/16, "early market candidate," next action: interview users.

**You say:**
> Decide next actions for everything in the ledger.

**Claude invokes `ems-decide`** — reviews all signals, assigns states. Reports: S001 watch, S002 interview users.

**You say:**
> Prepare interviews for S002.

**Claude invokes `ems-interview`** — identifies developer user type, drafts 5 outreach messages referencing specific issue threads, writes a 10-question interview plan focused on observed behavior.

---

### Example B: After accumulating 15 signals across two scan sessions

**You say:**
> Cluster everything in the ledger.

**Claude invokes `ems-cluster`** — groups 15 entries into 4 clusters. Reports: 2 noise (marked ignore), 1 watchlist, 1 interview candidate (3 independent sources, workaround documented, replaces freelancer hiring).

**You say:**
> Create a thesis for the freelancer replacement cluster.

**Claude invokes `ems-thesis`** — checks evidence bar (3+ sources: confirmed), creates `thesis-ai-app-last-mile-shipping.md` with behavior description, pain breakdown, workaround table, counterevidence section, and a concierge test offer structure.

---

### Example C: After 3 user interviews confirm urgency

**You say:**
> Draft a concierge offer for S003. Target is solo founders who built an AI-generated prototype.

**Claude invokes `ems-concierge`** — drafts 3 offer variations (different framings, one with different price point), writes a follow-up message for no-response after 48h, and explains what a "yes," "questions," or "only if free" response each tell you about the signal.

---

### Example D: Natural language, no explicit skill naming needed

All of these will trigger the right skill automatically:

| What you say | Skill invoked |
|---|---|
| "Scan for evidence around people using local LLMs to keep sensitive workflows private" | `ems-scan` |
| "How strong is S001?" | `ems-score` |
| "Are there any patterns across the ledger?" | `ems-cluster` |
| "What should I do next with each signal?" | `ems-decide` |
| "Who should I talk to about S002 and what should I ask them?" | `ems-interview` |
| "Turn the agent-memory cluster into a thesis" | `ems-thesis` |
| "S003 interviews showed urgency. Write me an offer." | `ems-concierge` |

---

## What the Skills Do Not Do

- **Run interviews**: that requires human contact
- **Judge evidence quality for you**: Claude applies the rubric, you decide if a workaround is real
- **Replace the concierge offer itself**: Claude drafts the offer, you send it and interpret responses
- **Create theses prematurely**: `ems-thesis` will refuse if the 3-source bar is not met

---

## Suggested Session Cadences

### 20-minute scan
1. Name a frontier → `ems-scan`
2. Review what was added
3. `ems-decide` to assign next actions

### 60-minute deep session
1. `ems-scan` on 2–3 frontiers
2. `ems-score` top 2–3 signals
3. `ems-cluster` to find patterns
4. `ems-decide` to clear the backlog

### After 10+ ledger entries
1. `ems-cluster` to group and triage
2. `ems-decide` on all signals
3. `ems-interview` for anything scoring 9+

### After interviews confirm urgency
1. `ems-thesis` if 3+ sources exist
2. `ems-concierge` to draft the offer
