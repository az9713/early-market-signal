---
name: ems-interview
description: Use when a signal scores 9 or higher and needs interview outreach messages and a concrete plan for talking to users about their actual behavior, not their opinions about potential products.
---

# EMS: Prepare Interviews

## Overview
Drafts targeted outreach messages and an interview plan for a specific signal. Uses `power_user_interview_script.md`. Focuses on asking users to show behavior, not describe hypothetical needs.

## Inputs
- **Signal ID** (required): e.g., S001
- **Target posts or users** (optional): specific URLs to source outreach targets from

## Process

### 1. Identify Target User Type
Read the signal's entries in `weirdness_ledger.md`. Identify the user who shows the behavior most intensely — not the largest audience, the most specific one.

### 2. Draft 5 Outreach Messages
Each message must:
- Reference a specific post or behavior, not generic pain
- Mention you are studying the workflow, not selling anything
- Ask for 3-4 concrete questions
- Name the specific issue the user posted about

Template:
```
I saw your [post/comment] about trying to [specific workflow or pain].

I am studying how people are solving this problem today. Not selling anything. Could I ask you 3-4 concrete questions about your current setup?

The most useful thing would be understanding what happened the last time you ran into this problem.
```

### 3. Draft Interview Plan

**Opening:**
```
I am trying to understand the workflow as it exists today. I am less interested in opinions about future tools and more interested in what you already do when this problem shows up.
```

**Core questions:**
1. What were you trying to do the last time this problem happened?
2. What were you using before your current workaround?
3. What broke, annoyed you, or slowed you down enough to try something different?
4. What exact tools, files, scripts, prompts, or manual steps do you use now?
5. How often does this happen?
6. How much time or money does the current workaround cost?
7. What happens if the workaround disappears tomorrow?
8. What have you built, hacked, copied, or borrowed to make this bearable?
9. Who else do you know with the same problem?
10. What would you pay for immediately if it solved this end to end?

**Key replacement questions:**
- What old tool, spreadsheet, contractor, or checklist does this replace?
- What budget would this come from? Who owns it?
- Is this a personal annoyance or a team-level problem?

### 4. Note Red Flags During Interviews
Treat these as weak demand:
- User likes the concept but has no current workaround
- User cannot remember the last time the problem happened
- User says many people need it but cannot name anyone
- User wants it only if free
- User would not care if the current workaround disappeared

## Output Format

```
Signal: [ID and name]
Target user type: [description]

Outreach messages (5):
1. [message referencing specific post]
2. ...

Interview plan:
- Opening: [text]
- Core questions: [1-10]
- Replacement questions: [list]
- Red flags to watch: [list]

Good interview targets from source evidence:
- [user or post URL]: [why they are a good target]
```

## Common Mistakes
- Generic outreach: every message must reference a specific post or behavior
- Asking "would you use this?": ask "show me the last time this happened"
- Interviewing too late: if score is 9+, start outreach now, not after more desk research
- Targeting users who posted opinions rather than users who posted specific problems
