---
name: ems-scan
description: Use when scanning communities for early market signals around a behavioral frontier, looking for pain, workarounds, and demand before a market category exists. Use when the user names a behavioral frontier and wants evidence gathered from web sources.
---

# EMS: Scan Behavioral Frontier

## Overview
Scans communities and web sources for behavioral evidence around a named frontier. Updates `source_map.csv` and `weirdness_ledger.md` with evidence-backed entries. Separates demand signals from hype.

## Inputs
- **Behavioral frontier** (required): a behavior statement, not a market category
  - Weak: "AI agent market"
  - Strong: "People delegating multi-step work to unstable agents despite reliability gaps"

## When Not to Use
If there is no behavioral frontier yet, reframe before scanning. If the frontier sounds like a clean analyst category, push back and reframe it as awkward behavior.

## Process

### 1. Validate the Frontier
The frontier must describe behavior. Awkward framing = early. Clean category framing = probably late.

### 2. Select Communities
Open `community_tracking_targets.md`. Pick 5-10 communities matching the frontier's pain type. Prefer issue trackers, support threads, and complaint-heavy forums over launch boards.

### 3. Search for Pain
Use query patterns from `search_queries.md`. Target words: `manual`, `workaround`, `hack`, `script`, `broken`, `keeps forgetting`, `why is there no`, `copy paste`, `no API`, `alternative to`.

**Strong result:** specific user, specific pain, current workaround, repeated by others

**Weak result (skip):** trend essay, launch announcement, market map, speculation without behavior

### 4. Update source_map.csv
Add one row per useful source with all fields:
`community, url, topic_cluster, repeated_pain, workaround, evidence, tool_or_process_replaced, user_sophistication, monetization_hint, category_maturity, notes, next_action`

Use exact quotes or tight paraphrases. "People are annoyed" is not enough.

### 5. Update weirdness_ledger.md
For each behavior that seems too intense for the product quality or category maturity, add an entry using the template already in that file. Every entry must answer: what behavior, why weird, what pain, what workaround, what evidence, what wedge.

### 6. Report Changes

```
Updated:
- source_map.csv: added N sources
- weirdness_ledger.md: added S___ entries

Strongest signal:
[one sentence]

Evidence:
[source links, quotes, workarounds]

Next action: ignore / watch / score / interview users
```

## Evidence Standards

Strong:
- "I stopped using X for this."
- "I built a script to make this bearable."
- "This breaks every week but I still use it."
- "I made a guide because everyone kept asking me."
- "I would pay if someone handled this end to end."

Weak (do not log):
- "Looks cool." / "This is the future." / "Huge market." / "Lots of likes."

## Common Mistakes
- Scanning 20 communities at once: start with 3-5
- Treating hype as demand: likes and launches are not behavior
- Vague notes: capture exact workarounds and replacement targets
- Mixing inference with evidence: keep them in separate fields
