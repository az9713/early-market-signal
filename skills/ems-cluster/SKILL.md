---
name: ems-cluster
description: Use when reviewing accumulated signals to group repeated pains, identify which are noise versus interview candidates, and decide what to kill or promote to thesis. Use after 10 or more ledger entries exist.
---

# EMS: Cluster Signals

## Overview
Reviews `weirdness_ledger.md` and `source_map.csv` to group repeated pains across communities. Identifies which signals are noise, watchlist, or interview-ready. Does not create thesis files — that is `ems-thesis`.

## When to Use
- The ledger has 10+ entries
- You want to find patterns across signals
- You want to kill weak signals and promote strong ones
- Signals are accumulating without being triaged

## Process

### 1. Group by Pain
Read all entries in `weirdness_ledger.md`. Group signals sharing the same underlying pain, even if the language differs across communities.

Look for:
- The same workaround appearing with different labels
- The same replacement target across different communities
- The same vocabulary forming independently in separate places

### 2. Assess Each Cluster

For each group:
- How many independent sources confirm this pain?
- Is there evidence of workarounds or replacement behavior, or just complaints?
- Does the pain appear across at least two different communities?
- Is any signal in this cluster scored 9+ in `signal_scorecard.csv`?

### 3. Triage

| Status | Criteria |
|---|---|
| **Noise** | Single source, hype language, no workaround, vague pain |
| **Watchlist** | Real pain, only one community, no urgency yet |
| **Interview candidate** | Pain repeats across 2+ sources, workaround exists, score 9+ |
| **Promote to thesis** | 3+ independent sources, workaround, replacement target, plausible willingness to pay |

### 4. Kill Weak Signals Explicitly
Mark noise signals as `ignore` in `next_action`. Do not leave them undecided — stale signals pollute future reviews.

### 5. Report

```
Clusters found: N

[Cluster name]
- Signals: S___, S___
- Independent sources: [count]
- Status: noise / watchlist / interview candidate / promote to thesis
- Reason: [one sentence]

Recommended kills: [signal IDs]
Recommended for interviews: [signal IDs]
Recommended for thesis: [signal IDs]
```

## Common Mistakes
- Waiting for 30+ entries before clustering: review at 10-15 to kill noise early
- Promoting to thesis without 3+ independent sources
- Leaving signals undecided: every signal must end with a status
- Counting multiple posts from the same community as independent sources
