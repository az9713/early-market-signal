# Concierge Offer: Developer-Maintained Agent Memory

**Signal:** S002 / S003 — Developer-maintained agent memory
**Thesis:** thesis-developer-maintained-agent-memory.md
**Date prepared:** 2026-05-12
**Status:** ready to send — interviews confirmed urgency

---

## Target User

Solo technical founders and senior developers running multi-day Claude Code projects who:
- Built their own memory tools (grov, A-MEM, claude-brain, custom CLAUDE.md systems)
- Showed urgency in interviews (time cost, rework cost, or frustration language)
- Are spending measurable time on memory maintenance rather than coding

Do not send to users who said "only if free" or "I just wanted advice" in interviews.

---

## Offer Drafts

### Variation A — Setup + managed maintenance (recommended first send)

```
I'll set up and maintain your Claude Code memory layer for the next 4 weeks.

That means: CLAUDE.md architecture, MEMORY.md routing table, per-domain
topic files, hooks to keep Claude from ignoring its own memory, and weekly
pruning when files drift past the 250-line compliance threshold.

You get a working system on day one and don't touch the maintenance.

$500 this week to start. Want me to send setup details?
```

**Use when:** Interview showed time cost or rework frustration. User is spending >30 min/week on memory maintenance or session startup.

---

### Variation B — One-time architecture build (lower barrier)

```
I'll build your complete Claude Code memory system in 48 hours — CLAUDE.md
structure, MEMORY.md routing, topic files, and hooks — plus a maintenance
guide so you can run it yourself.

Based on what you described, this should cut your session startup time from
~10 minutes to under 2.

$300, delivered this week. Should I send the intake form?
```

**Use when:** User expressed urgency but also DIY preference. Use as a fallback if Variation A gets no response after 48h.

---

### Variation C — Team memory layer (if team impact surfaced in interview)

```
I'll set up a shared Claude Code memory system for your team — shared context
files, per-developer topic files, agent handoff conventions between sessions,
and a 30-day maintenance window while you embed the workflow.

$1,500 this week. Covers setup and one month of maintenance.
Want me to schedule a 30-minute kickoff?
```

**Use when:** Interview revealed team-level impact — multiple developers losing context, or user mentioned wanting teammates to benefit from their memory setup.

---

## Follow-Up If No Response After 48h

```
Quick follow-up — the offer I sent is open until Friday.

If the timing is off or the scope isn't right, happy to adjust.
What's the part of the memory problem that's costing you the most right now?
```

---

## Interpreting Responses

| Response | Signal | Action |
|---|---|---|
| "Yes, send details" | Urgency confirmed | Pursue; clarify team size before finalising price |
| Asks about scope, files, projects | Buyer intent present | Answer concretely; do not hedge |
| "Can you do it for less?" | Economic signal but weak | Hold price; offer narrower scope instead of discount |
| "Maybe later / after I finish X" | Urgency softer than interview suggested | Log; follow up in 2 weeks |
| "Only if free / just wanted advice" | No economic force | Do not negotiate; log as non-buyer |
| "I already built something that works" | Builder not buyer | Ask who they know with the same problem |

---

## Success Criteria

**A yes on Variation A or C at full price tells you:**
- Willingness to pay confirmed for managed memory maintenance
- Subscription or retainer model is viable — not just one-time setup
- Upgrade thesis status from `watch` to `prototype-test`

**A yes on Variation B only tells you:**
- Users will pay for setup but not ongoing maintenance
- Product shape may be a one-time configurator, not a subscription
- Re-test maintenance model with a different framing before concluding

---

## Failure Criteria

- 3+ "only if free" responses: workaround is good enough; no economic force; do not build
- 3+ "maybe later": urgency real but not acute; revisit in 90 days with a re-scan
- Users ask for cheaper alternatives: test Variation B at $150 before concluding price is the blocker

---

## Delivery Steps (if yes)

1. Send intake form: current CLAUDE.md state, project structure, agent workflow, session frequency
2. 30-minute kickoff call to understand project domains and pain points
3. Configure CLAUDE.md + MEMORY.md + topic files within 48 hours
4. Set up hooks to enforce memory use
5. Weekly 15-minute review: prune files above 250 lines, update routing table
6. End of week 4: check-in — is session startup faster? Would they pay for month 2?

---

## Thesis Update Trigger

If 2 or more users accept any variation at full price:
- Update `thesis-developer-maintained-agent-memory.md` status from `watch` to `prototype-test`
- Begin scoping narrow software prototype (auto-pruning + CLAUDE.md generator)
- Run second interview round focused on team-level adoption and budget ownership
