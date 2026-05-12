---
name: ems-decide
description: Use when reviewing all open signals to assign a definitive next action to each one, or when signals are accumulating without clear decisions. Use after a scan session or scoring batch.
---

# EMS: Decide Next Actions

## Overview
Reviews all signals in `weirdness_ledger.md` and `signal_scorecard.csv`. Assigns a definitive next action to every signal. Justifies each decision with evidence. Leaves no signals in an undecided state.

## Decision Framework

Every signal ends in exactly one state:

| Decision | Criteria |
|---|---|
| **ignore** | Hype language, no workaround, single source, pain is vague or isolated |
| **watch** | Real pain, only one community, no urgency, not ready to score yet |
| **interview users** | Score 9+, behavior is repeated across communities, workaround exists |
| **test concierge offer** | Score 9+, urgency signals present, users are already considering paid help |

## Process

1. Read all entries in `weirdness_ledger.md`
2. Read all rows in `signal_scorecard.csv`
3. For each signal without a confirmed next action, apply the decision framework
4. Update the `next_action` field in the relevant file
5. Report all decisions with one-sentence justifications

## Output Format

```
Decisions:

[Signal ID] — [name]
Decision: ignore / watch / interview users / test concierge offer
Reason: [one sentence citing specific evidence]

---

Summary:
- Ignored: N signals
- Watching: N signals
- Interview queue: [signal IDs]
- Concierge test queue: [signal IDs]
```

## Common Mistakes
- Leaving signals undecided: every signal must have a next action
- Moving to concierge offer without interview evidence of urgency
- Ignoring signals that score 9+ because interviews feel hard to arrange
- Watching signals indefinitely without a recheck trigger or new scan planned
- Treating "watch" as a permanent state: set a review condition when you choose it
