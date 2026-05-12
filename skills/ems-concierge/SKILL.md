---
name: ems-concierge
description: Use when a signal has been validated through interviews showing urgency, to draft a specific priced manual offer that tests willingness to pay before building any software.
---

# EMS: Test Concierge Offer

## Overview
Drafts a specific, priced, time-bound offer to solve a signal's core pain manually — no software built. Tests whether users will pay, not whether they like the idea. The goal is learning, not revenue.

## When to Use
- Interviews show urgency and users are considering paid help
- Signal scores 9+ and replacement behavior is confirmed
- You want to test economic force before building anything

Do not use before interviews. Interviews must show urgency first.

## Inputs
- **Signal ID or thesis file** (required)
- **Target user type** (required)

## Offer Structure

A good offer is:
- **Specific**: names the exact pain being solved
- **Priced**: a real number — never "what would you pay?"
- **Time-bound**: "this week" not "sometime"
- **Deliverable**: something you can actually do manually

Example from USER_GUIDE.md:
```
I can take your AI-generated app from local prototype to deployed MVP
with auth, database, payments, and basic error handling this week
for $1,500. Interested?
```

## Pricing Guide

| User Type | Price Range |
|---|---|
| Prosumer / individual workflow | $100–$500 |
| Solo founder / small business | $500–$2,000 |
| Urgent B2B with team impact | $2,000–$10,000+ |

Underpricing signals low confidence and attracts non-buyers.

## Interpreting Responses

| Response | Signal |
|---|---|
| "Yes, send details" | Strong urgency — pursue |
| Questions about scope, timeline, examples | Buyer intent worth exploring |
| "Maybe later" | Weak — not urgent |
| "Only if free" | No economic force |
| "I just wanted advice" | Not a buyer |

## Output Format

```
Signal: [ID and name]
Target user: [description]

Offer drafts (3 variations):
1. [specific pain, price, timeline — version A]
2. [different framing — version B]
3. [different price point — version C]

Follow-up if no response after 48h:
[short message]

Success criteria: [what a yes tells you about this signal]
Failure criteria: [what a no or silence tells you]
```

## Common Mistakes
- Asking "would you pay?" instead of making a real offer
- Offering before interviews confirm urgency
- No time bound: "anytime" kills urgency
- Treating revenue as the goal: the goal is learning
- Pricing too low: it undercuts signal quality and attracts non-buyers
