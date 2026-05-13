# Interview Plan: Builder Memory Tools for AI Coding Agents

**Signals:** S002, S003
**Date prepared:** 2026-05-12
**Target user type:** Builders who experienced agent amnesia acutely enough to ship a tool in response — engineers who converted pain into a working system and posted about it publicly.

---

## Good Interview Targets

| Target | Source | Why they are a good target |
|---|---|---|
| grov author | https://news.ycombinator.com/item?id=46126066 | Quantified the pain (10-11min → 1-2min); 250 downloads = others use it; built a proxy not a file, which is a different architectural bet |
| A-MEM author | https://news.ycombinator.com/item?id=46636707 | Hooks-as-reminder reveals the tool doesn't fully work without babysitting — that gap is worth probing |
| claude-brain builder | https://dev.to/mikeadolan/how-i-built-persistent-memory-for-claude-code-1dn7 | Scale of usage (67k messages) means this is a real daily workflow, not a demo |
| @malikchohra | https://medium.com/@malikchohra/i-built-a-memory-os-after-claude-code-hallucinated-42-of-my-code-1896334b9cfc | 42% hallucination rate is specific and production-level — either confirms extreme pain or reveals a measurement worth understanding |
| BonoboIO | https://news.ycombinator.com/item?id=46426624 | 15k-token config is the S003 behavior at its most extreme — best target for understanding maintenance burden |

---

## Outreach Messages

**1 — grov author (HN: Show HN: Persistent memory for Claude Code sessions)**
```
I saw your Show HN post about grov — you mentioned watching Claude Code spend
10 minutes re-exploring files it had already analyzed the day before, and built
a SQLite proxy to fix it.

I am studying how developers are solving the agent memory problem today.
Not selling anything. Could I ask you 3-4 concrete questions about what
you built and how you actually use it now?

The most useful thing would be: what does your workflow look like on a
typical day when grov is working, and what does it look like when it breaks?
```

**2 — A-MEM author (HN: Show HN: A-MEM – Memory for Claude Code that links and evolves on its own)**
```
I saw your Show HN post about A-MEM. You wrote that you'd spend hours
with Claude digging into functionality, then have to start from scratch
the next session — and that you had to add hooks to remind Claude to
use the memory system at all.

I'm studying how builders are working around agent amnesia. Not selling
anything. Could I ask a few concrete questions about your current setup?

Most useful would be: what does your A-MEM workflow look like on a day
when it works well, and what still breaks that the tool doesn't fix?
```

**3 — claude-brain builder (DEV Community)**
```
I saw your post about claude-brain — running across 1,321 sessions and
67,000+ messages across 9 projects. That is a significant investment in
keeping an agent's memory alive.

I am researching how developers solve the context-loss problem in practice.
Not selling anything. Three questions about your actual workflow would be
more useful to me than any survey.

Specifically: what broke badly enough that you decided to build this
instead of using something off the shelf?
```

**4 — @malikchohra (Medium: "I built a memory OS after Claude Code hallucinated 42% of my code")**
```
I read your Medium post about building a memory OS after a 42% hallucination
rate in Claude Code. That number is specific enough that I'd like to understand
what was actually happening.

I am studying how developers solve agent memory gaps in production workflows.
Not selling anything. Could I ask you 3-4 concrete questions about what you
built and whether it solved the problem?

Most useful: what does your setup look like now, and what do you still
do manually that you wish you didn't have to?
```

**5 — BonoboIO (HN: Stop Claude Code from forgetting everything)**
```
I saw your comment in the HN thread about stopping Claude Code from
forgetting everything. You mentioned maintaining a 15,000-token global
~/.claude/CLAUDE.md with conventions and custom slash commands.

I am studying how developers manage agent configuration across sessions.
Not selling anything. Could I ask a few concrete questions about your
current setup?

Specifically: how did you build up that file over time, how often do
you maintain it, and what happens when it drifts or gets too long?
```

---

## Interview Plan

### Opening
```
I am trying to understand the workflow as it exists today — not opinions
about future tools, just what you actually do when the memory problem shows
up. If you can, show me the last time it happened.
```

### Core Questions

1. What were you trying to do the last time the agent forgot something important?
2. What were you using before you built your current solution?
3. What specifically broke, or cost you enough time, that you decided to build rather than tolerate it?
4. Walk me through your exact current setup — files, scripts, hooks, commands. Show me if you can.
5. How often do you actively maintain the memory layer vs. just use it?
6. How much time per week does maintaining this take, roughly?
7. What happens if your memory system breaks or disappears tomorrow — what do you lose?
8. What does your tool not solve that you still handle manually?
9. Who else do you know running something similar?
10. If someone offered to run this for you reliably — managed, not DIY — what would you pay per month?

### Replacement Questions

- What did you do before you built this — what process or habit did it replace?
- Is this a personal tool or does anyone else on your team use it?
- If it's personal: would you want your team to have it? Who would pay for that?
- What budget would this come from — tooling, infra, personal spend?

### Intensity Questions

- Have you recommended your tool or approach to anyone else?
- Have you written a post, guide, or internal doc about it? (You already have — what made you do that?)
- Do you use this every day or only on longer projects?
- What rough edges do you tolerate because the outcome matters enough?

### Concierge Offer Test

Do not ask: *"Would you pay for this?"*

Ask:
```
I can set up and maintain a managed memory layer for your Claude Code
workflow this week — I'll handle the configuration, file structure, and
upkeep. $200 to start. Should I send you the details?
```

Price anchor:
- $200–500 for solo developer workflow
- $500–2,000 if team-level impact is mentioned

---

## Red Flags to Watch For

- Builder says they use the tool occasionally, not daily — the pain may have been acute once and resolved
- Builder cannot describe what breaks when the tool is missing — may be a solution looking for a problem
- Builder says "lots of people asked me about it" but cannot name anyone who actually uses it
- Builder says they would only want a managed version if it were free — no monetization signal
- Builder describes the problem as interesting, not costly — enthusiasm without urgency

---

## Interview Notes Template

Use one file per interview: `interview_notes_[handle]_[date].md`

```markdown
# Interview Notes: [User / Handle]

**Date:**
**Signal ID:** S002 / S003
**Source URL:**
**User type:** builder
**Current workflow:**
**Pain:**
**Workaround:**
**Replacement target:**
**Frequency:**
**Cost/time impact:**
**Urgency:**
**Existing spend:**
**Who else has this pain:**
**Exact language used by user:**
**Evidence shown:**
**Willingness-to-pay signal:**
**Counterevidence:**
**Next action:**
```
