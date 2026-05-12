# User Guide: Run Your First Early Market Signal Scan

This guide walks through one concrete example from start to finish. It is written for the first time you use the workflow.

The example topic:

```text
AI-generated app last-mile assembly
```

Plain English version:

```text
People can use AI to generate an app prototype, but then they get stuck turning it into a real product with auth, database, payments, deployment, bugs, and iteration.
```

That may or may not be a real market. This workflow helps you find out by looking for behavior, not hype.

## If You Are Using This In Codex App

Yes, the workflow changes a little when Codex is the operator.

Instead of manually opening every file and copying rows yourself, you can ask Codex to run a focused scan, gather evidence, update the workflow files, and summarize what changed. Your job becomes choosing the behavioral frontier and reviewing the evidence quality.

Use Codex for:

- Finding current communities, threads, issues, and discussions
- Extracting pain patterns from source links
- Updating `source_map.csv`
- Adding entries to `weirdness_ledger.md`
- Scoring signals in `signal_scorecard.csv`
- Drafting interview questions and outreach messages
- Creating thesis files from repeated clusters
- Separating evidence from inference

Do not use Codex as a substitute for customer discovery. Codex can surface the trail, but interviews and willingness-to-pay tests still need real users.

### Copyable Codex Prompts

Start a focused scan:

```text
Use early_market_signal_workflow. Scan for evidence around this behavioral frontier:

[paste frontier]

Use current web sources. Prioritize GitHub issues, Reddit, forums, HN, and YouTube comments. Update source_map.csv and weirdness_ledger.md with evidence-backed entries. Do not treat hype or launch announcements as demand.
```

Score a signal:

```text
Use early_market_signal_workflow. Score signal [S___] in signal_scorecard.csv using the 0-16 rubric. Base the score only on evidence already captured in source_map.csv and weirdness_ledger.md. Explain any weak assumptions in the notes field.
```

Cluster signals:

```text
Use early_market_signal_workflow. Review weirdness_ledger.md and source_map.csv. Cluster repeated pains, identify which signals are noise vs watchlist vs interview candidates, and create or update a thesis file only if evidence appears across multiple sources.
```

Prepare interviews:

```text
Use early_market_signal_workflow. For signal [S___], draft 5 outreach messages and a short interview plan using power_user_interview_script.md. Focus on asking users to show the last real instance of the problem.
```

Create a thesis:

```text
Use early_market_signal_workflow. Create a thesis file from early_market_thesis_template.md for this cluster:

[paste cluster name or signal IDs]

Keep evidence separate from inference. Include counterevidence and a concrete next test.
```

### Codex Operating Rules For This Workflow

When asking Codex to run the workflow, require:

- Current source links for any live-community claim
- Exact quotes or tight paraphrases with URLs when possible
- Clear separation between evidence and interpretation
- Updates to local workflow files, not just chat summaries
- A final list of changed files
- A next action for every signal: ignore, watch, interview users, or test concierge offer

Good Codex output should look like this:

```text
Updated:
- source_map.csv: added 6 sources
- weirdness_ledger.md: added S005 and S006
- signal_scorecard.csv: scored S005 at 10/16

Best signal:
AI-generated app builders repeatedly get stuck at deployment/auth handoff.

Evidence:
3 independent source links, 2 concrete workarounds, 1 paid-help signal.

Next action:
Interview users. Do not create a thesis yet until one more non-Reddit source confirms the same pattern.
```

Weak Codex output looks like this:

```text
This is a huge trend. Many people are interested. You should build a platform.
```

Reject that. Ask for source links, observed behavior, workarounds, and replacement targets.

## What You Are Trying To Learn

By the end of this walkthrough, you should have:

- A clear behavioral frontier
- A short list of communities to scan
- 3-5 pieces of source evidence
- 1 weirdness ledger entry
- 1 scored signal
- A decision: ignore, watch, interview users, or test a concierge offer

You do not need to complete everything perfectly. The goal is to build the habit of capturing real behavior.

## Step 1: Name The Behavior, Not The Market

Open:

```text
README.md
```

Use this behavior:

```text
Nontechnical and semi-technical builders are using AI to generate app prototypes, but they get stuck when the app needs to become a real product.
```

This is better than:

```text
AI app builder market
```

Why?

Because "AI app builder market" is a category. It pushes you toward market maps, product lists, and startup comparisons.

The behavior statement pushes you toward evidence:

- Who is stuck?
- Where do they get stuck?
- What do they do next?
- Do they pay someone?
- Do they quit?
- Do they build ugly workarounds?
- Are many people stuck at the same point?

Write this behavior at the top of your notes or directly into a new section of `weirdness_ledger.md`.

## Step 2: Pick 3 Places To Look

Open:

```text
community_tracking_targets.md
```

For this example, start with only three sources:

| Source | Why It Matters |
| --- | --- |
| `r/vibecoding` | Users discuss building apps with AI and often reveal where they get stuck. |
| Vercel Community | Deployment failures show the gap between local prototype and shipped app. |
| Supabase Discussions | Auth, database, and permissions problems reveal real last-mile product friction. |

Do not scan everything at once. Start narrow.

## Step 3: Search For Pain Words

Open:

```text
search_queries.md
```

Use these searches:

```text
site:reddit.com/r/vibecoding "deploy"
site:reddit.com/r/vibecoding "auth"
site:reddit.com/r/vibecoding "payments"
site:community.vercel.com "AI generated"
site:community.vercel.com "environment variable"
site:github.com/supabase/supabase/discussions "auth" "AI generated app"
```

You are not looking for the most popular post. You are looking for specific pain.

Good signs:

- "I built this with AI but cannot deploy it."
- "It works locally but breaks on Vercel."
- "I do not understand auth."
- "How do I add payments?"
- "AI generated this but I do not know how to fix the errors."
- "Should I hire someone to finish this?"

Weak signs:

- "This app builder is amazing."
- "The future of coding is here."
- "I made a startup in one hour."
- "What is the best AI tool?"

## Step 4: Add Useful Sources To `source_map.csv`

Open:

```text
source_map.csv
```

Add one row per useful source. You can edit it in a spreadsheet app or plain text editor.

For this example, a row might look like this:

```csv
community,url,topic_cluster,repeated_pain,workaround,evidence,tool_or_process_replaced,user_sophistication,monetization_hint,category_maturity,notes,next_action
"r/vibecoding","[paste URL]","AI-generated app last-mile","AI-generated apps work as demos but fail during deployment/auth/payments","Users ask Reddit, copy tutorials, hire freelancers, or restart projects","User says the app works locally but fails when deployed","Freelancer handoff, no-code builder, manual debugging","nontechnical founder / semi-technical builder","paid concierge shipping, deployment assistant, app hardening service","pre-category","Need more examples from Vercel and Supabase before scoring confidently","watch"
```

Do not worry if the wording is rough. The important part is that the row captures:

- the community
- the link
- the pain
- the workaround
- the replacement target
- the next action

## Step 5: Write A Weirdness Ledger Entry

Open:

```text
weirdness_ledger.md
```

Copy the entry template and fill it out.

For this example:

```markdown
## Signal ID: S002

**Date captured:** 2026-05-12
**Behavioral frontier:** Nontechnical and semi-technical builders can generate app prototypes with AI, but they get stuck turning them into real deployed products.
**Community/source:** r/vibecoding, Vercel Community, Supabase Discussions
**URL/evidence:** [paste 2-3 URLs]
**Observed behavior:** Users produce a local prototype with AI, then ask for help with deployment, auth, databases, payments, and debugging.
**Why it is weird:** AI removed the first coding barrier but exposed a new shipping barrier. The user now owns code they do not fully understand.
**Pain behind the behavior:** The prototype is not useful until it is deployed, secure, connected to data, and maintainable.
**Current workaround:** Asking communities, copying tutorials, hiring freelancers, restarting in another tool, or abandoning the app.
**Tool/process being replaced:** Freelancer MVP build, no-code tools, manual tutorial stitching, and traditional beginner coding education.
**Possible product wedge:** Concierge or tool-assisted "ship my AI-generated app" service for solo founders.
**Confidence:** medium
**Next action:** score

### Evidence Notes

- Exact quote or paraphrase with URL: [paste here]
- Repeated by other users? yes / no / unclear
- Any tutorial/script/plugin/fork/template? yes / no / unclear

### Follow-Up Questions

- Where exactly do users get stuck most often: deployment, auth, payments, database, debugging, or iteration?
- Are users willing to pay to ship the app, or do they only want free advice?
- Is the buyer a founder, hobbyist, agency, or internal team?
- Does this become a recurring need or a one-time service?
```

This is the first real artifact. It turns scattered observations into a signal you can compare against others.

## Step 6: Score The Signal

Open:

```text
signal_scorecard.csv
```

Add a row for this signal.

Use `0`, `1`, or `2` for each scoring column:

- `0`: not present
- `1`: weak or occasional
- `2`: strong and repeated

For this example, your first score might be:

```csv
signal_id,signal_name,evidence_url,rough_ux_tolerated,user_tutorials,incumbent_replacement,api_integration_requests,hacked_use_cases,vocabulary_forming,copycats_appearing,outside_curiosity_growing,total_score,interpretation,next_action,notes
S002,"AI-generated app builders get stuck shipping real products","[paste strongest URL]",1,2,1,2,1,1,1,2,11,"early market candidate","interview users","Strong tutorial and integration pain. Need proof that users will pay to solve the last mile."
```

Why the score is `11`:

| Criterion | Score | Reason |
| --- | ---: | --- |
| Rough UX tolerated | 1 | Users tolerate broken generated code if it gets them closer. |
| User tutorials | 2 | Tutorial demand is high in this area. |
| Incumbent replacement | 1 | May replace freelancers or no-code workflows, but not proven. |
| API/integration requests | 2 | Auth, payments, database, and deployment are integration-heavy. |
| Hacked use cases | 1 | Users stitch tools together manually. |
| Vocabulary forming | 1 | "Vibe coding" and "last mile" language are emerging. |
| Copycats appearing | 1 | Many tools claim to solve pieces of this. |
| Outside curiosity growing | 2 | Nontechnical builders are entering software creation. |

Score interpretation:

```text
0-4: probably noise
5-8: watchlist
9-12: early market candidate
13-16: serious founder attention
```

An `11` does not mean "build a company now." It means "talk to users."

## Step 7: Find 5 Users To Interview

Open:

```text
power_user_interview_script.md
```

Look for users who posted specific problems. Avoid users who only posted generic tool opinions.

Good interview targets:

- Someone whose app works locally but fails on deployment
- Someone asking how to add auth
- Someone asking how to connect a database
- Someone trying to add Stripe or subscriptions
- Someone who says they may hire help
- Someone who rebuilt the same app multiple times in different AI tools

Use this message:

```text
I saw your post about getting an AI-generated app stuck at [specific issue: deployment/auth/payments/database].

I am studying how people are solving this problem today. Not selling anything. Could I ask you 3-4 concrete questions about your current setup?

The most useful thing would be understanding what happened the last time you hit this issue.
```

During the interview, do not ask:

```text
Would you use an app that solves this?
```

Ask:

```text
Can you show me the last time this broke?
```

Then ask:

```text
What did you do next?
```

The "what did you do next" answer is where the market signal usually appears.

## Step 8: Decide The Next Action

After scoring and interviews, choose one action.

| Decision | Choose This When |
| --- | --- |
| Ignore | The problem is rare, low-stakes, or mostly curiosity. |
| Watch | The pain repeats, but users are not urgent yet. |
| Interview more users | The score is 9+ but willingness to pay is unclear. |
| Test concierge offer | Users are stuck, urgent, and already considering paid help. |

For this example, the likely first decision is:

```text
Interview more users.
```

Reason:

```text
The pain appears real, but the key unknown is whether users will pay for last-mile shipping or just ask communities for free help.
```

## Step 9: Create A Thesis Only After A Cluster Appears

Do not create a thesis from one post. Wait until you see the same pain across several sources.

Create a thesis when you have evidence like:

- 3+ users stuck on deployment/auth/payments/database
- 2+ communities showing similar complaints
- At least one user considering paid help
- A repeated workaround, such as hiring a freelancer or restarting in another tool

Then copy:

```text
early_market_thesis_template.md
```

Create a new file:

```text
thesis-ai-generated-app-last-mile.md
```

Fill out the first version:

```markdown
# Early Market Thesis: AI-Generated App Last-Mile Assembly

## Behavior Observed

Nontechnical and semi-technical builders are using AI to create app prototypes, but they get stuck when those prototypes need deployment, auth, payments, database setup, debugging, and ongoing iteration.

## User Type

Solo founders, indie hackers, operators, and nontechnical builders who can prompt an AI tool but cannot reliably ship production software.

## Pain

The user now has code that appears valuable but is not usable as a real product.

## Current Workaround

Community posts, tutorials, freelancers, no-code rebuilds, restarts in new tools, or abandonment.

## Replacement Target

Freelancer MVP handoff, beginner coding help, no-code tools, and manual tutorial stitching.

## Product Wedge

Concierge or tool-assisted service that turns AI-generated prototypes into deployed MVPs with auth, database, payments, and basic maintainability.

## Next Test

Interview 5 users and offer to manually ship one app for a fixed price.
```

Keep the thesis short at first. It should improve as evidence improves.

## Step 10: Test A Concierge Offer

Only do this if interviews show urgency.

Example offer:

```text
I can take your AI-generated app from local prototype to deployed MVP with auth, database, payments, and basic error handling this week for $1,500. Interested?
```

What you learn:

- If they say yes quickly, the pain may be urgent.
- If they ask for scope, timeline, or examples, there may be real buyer intent.
- If they say "maybe later," "only if free," or "I just wanted advice," the signal is weaker.

The point is not to maximize revenue. The point is to learn whether the pain has economic force.

## First-Run Checklist

Use this checklist the first time you run the workflow.

```markdown
- [ ] I picked one behavior, not a market category.
- [ ] I scanned 3 focused communities or searches.
- [ ] I captured 3-5 pieces of evidence.
- [ ] I added at least one row to `source_map.csv`.
- [ ] I added one entry to `weirdness_ledger.md`.
- [ ] I scored one signal in `signal_scorecard.csv`.
- [ ] I chose a next action: ignore, watch, interview, or test offer.
- [ ] I did not create a thesis until I saw repeated evidence.
```

## Common Mistakes

### Mistake: Starting With Product Ideas

Wrong:

```text
I should build a deployment assistant for AI apps.
```

Better:

```text
I see repeated evidence that users get stuck at deployment after AI generates a local prototype.
```

### Mistake: Treating Hype As Demand

Likes, launches, and demos are not enough.

Demand looks like:

- workarounds
- repeated pain
- users asking for help
- users spending time or money
- users replacing old workflows

### Mistake: Scanning Too Broadly

Do not scan 20 communities on your first pass. Pick three sources and capture good evidence.

### Mistake: Interviewing Too Late

If a signal scores 9+, talk to users. Desk research cannot answer willingness to pay.

## What A Good First Session Looks Like

A good first session is not a polished thesis. It is a small evidence packet:

```text
Behavior:
AI-generated app builders get stuck at the shipping layer.

Evidence:
3 links from r/vibecoding, Vercel Community, and Supabase Discussions.

Weirdness:
AI makes prototype creation easy enough that nontechnical users now own code they cannot ship.

Score:
11/16, early market candidate.

Next action:
Interview 5 users who posted specific last-mile problems.
```

That is enough. The next move is user contact, not more theorizing.
