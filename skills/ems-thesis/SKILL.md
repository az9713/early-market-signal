---
name: ems-thesis
description: Use when a signal cluster has appeared across 3 or more independent sources and is ready to be converted into a structured startup thesis file. Use after ems-cluster recommends promotion.
---

# EMS: Create Thesis

## Overview
Creates a `thesis-[name].md` file from `early_market_thesis_template.md` for a named signal cluster. Keeps evidence separate from inference. Includes counterevidence and a concrete next test.

## Evidence Bar — Do Not Create Without This

- 3+ independent sources (not 3 posts from the same community)
- At least one workaround documented
- At least one replacement target identified
- Plausible willingness to pay exists

If any of these are missing, log the cluster as watchlist in `ems-cluster` and return when evidence improves.

## Inputs
- **Cluster name or signal IDs** (required)

## Process

### 1. Name the File
```
thesis-[behavior-name].md
```
Name by the behavior, not the product:
- Good: `thesis-agent-context-handoff.md`
- Weak: `thesis-agent-memory-platform.md`

### 2. Fill the Template

Required sections (from `early_market_thesis_template.md`):

| Section | What to Write |
|---|---|
| Behavior Observed | Behavior before naming a product. Format: "[User type] are already [new behavior] despite [friction] because [outcome] matters." |
| User Type | Who shows the behavior most intensely. Include exclusions. |
| Pain | Functional, time, money, emotional. Why existing tools fail. |
| Current Workaround | What users do today. Tools, scripts, frequency, rough edges tolerated. |
| Replacement Target | What this behavior is killing. Budget replaced, labor replaced. |
| Why Now | New enabling tech, new expectation, new failure mode, new distribution. |
| Evidence | Source table with signal type per row: complaint / workaround / tutorial / replacement / vocabulary / copycat |
| Counterevidence | Active reasons this is not a startup (see below) |
| Signal Score | Link to scorecard row, total score, interpretation |
| Product Wedge | Narrow first product. Specific, not "platform for X." |
| Concierge Test | What can be delivered manually before software is built. Offer, price, delivery steps, success/failure criteria. |
| Next Test | One decision with evidence justification |

### 3. Counterevidence Is Mandatory
Include at least three active reasons the wedge might fail:
- Is the pain temporary (a bug that will be fixed)?
- Can incumbents patch it quickly?
- Is willingness to pay weak?
- Is the workaround already good enough?
- Are users loud but not economically valuable?
- Is the workflow too niche?

### 4. Set Status
- `active`: evidence is strong, pursuing
- `watch`: interesting but needs more evidence
- Do not set `prototype-test` until interviews confirm urgency

## Output
- New file: `thesis-[name].md` in the workflow directory
- Report: file name, signal IDs included, source count, counterevidence count, next test

## Common Mistakes
- Creating a thesis from one community: wait for 3+ independent sources
- Naming by product category: name by the behavior
- Skipping counterevidence: always include reasons it might fail
- Setting prototype-test status without interview confirmation of urgency
