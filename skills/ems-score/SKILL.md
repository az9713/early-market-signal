---
name: ems-score
description: Use when scoring a signal from weirdness_ledger.md or source_map.csv using the 0-16 demand quality rubric, or when the user asks how strong a signal is.
---

# EMS: Score Signal

## Overview
Scores a named signal using the 0-16 rubric. Bases the score only on evidence already captured in `source_map.csv` and `weirdness_ledger.md`. Updates `signal_scorecard.csv` with the result and reasoning.

## Inputs
- **Signal ID or description** (required): e.g., S001 or "developers maintaining memory files around coding agents"

## Scoring Rubric

Score each criterion 0, 1, or 2:
- `0`: absent
- `1`: weak or occasional
- `2`: repeated and strong

| Criterion | What to Look For |
|---|---|
| Rough UX tolerated | Users stay despite bad product quality |
| User tutorials | Unprompted explainers, guides, scripts |
| Incumbent replacement | Old tool or process being abandoned |
| API/integration requests | Users asking for connections to other tools |
| Hacked use cases | DIY workflows, forks, templates, scripts |
| Vocabulary forming | New terms appearing before category names |
| Copycats appearing | Multiple tools claiming to solve the same thing |
| Outside curiosity growing | Non-users asking how the behavior works |

## Interpretation

| Total | Meaning | Next Action |
|---|---|---|
| 0-4 | Probably noise | ignore |
| 5-8 | Watchlist | watch |
| 9-12 | Early market candidate | interview users |
| 13-16 | Serious founder attention | interview / test concierge offer |

## Process

1. Read the signal's entries in `weirdness_ledger.md` and `source_map.csv`
2. Score each criterion based only on captured evidence — do not infer
3. Note the basis for each score
4. Add or update the row in `signal_scorecard.csv`
5. Flag any assumptions or evidence gaps in the notes field

## Output Format

```
Signal: [ID and name]
Score: [X/16] — [interpretation]

Criterion scores:
- Rough UX tolerated: [0/1/2] — [reason]
- User tutorials: [0/1/2] — [reason]
- Incumbent replacement: [0/1/2] — [reason]
- API/integration requests: [0/1/2] — [reason]
- Hacked use cases: [0/1/2] — [reason]
- Vocabulary forming: [0/1/2] — [reason]
- Copycats appearing: [0/1/2] — [reason]
- Outside curiosity growing: [0/1/2] — [reason]

Assumptions or gaps: [list]
Next action: [ignore / watch / interview users / test concierge offer]
```

## Common Mistakes
- Scoring based on potential, not evidence: only score what is captured
- Rounding up weak signals: 1 means occasional, not "kind of present"
- Skipping the notes field: weak assumptions must be documented explicitly
- Scoring a signal without reading the source files first
