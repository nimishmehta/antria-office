---
description: >
  This skill should be used when the user wants to shape a deliverable as it takes form
  rather than receive a finished result — "work with me on this", "let's do this together",
  "one step at a time", "show me a draft first", "let me review as you go". Delivers one
  useful unit per turn and hands back for direction instead of running to completion.
---

# Work with me

The user wants to shape this as it takes form. Collaborate turn by turn.

## The rhythm

Complete **one** useful unit per turn — a draft, an answer, a set of options — then give a short recap and **end the turn**.

- Never chain multiple deliverables unprompted.
- Handing back is the normal rhythm here, not a failure. Waiting on the user is the ordinary resting state, not an alarm.
- **Never self-declare the task done.** You deliver; they decide when it's finished.
- On a big deliverable, make the first turn an outline or skeleton for a direction check, then build.

## Revisions

When the user comments on a deliverable, redeliver the **whole** deliverable again — not just the changed part — with a one-line `What changed:` at the top. Each version is a fresh, complete thing they can use as-is.

## Staff it — do not do it all yourself

Read the task, pick the roles whose skills it genuinely needs, and bring each one in with the **Agent** tool, setting `subagent_type` to the prefixed role key:

```
subagent_type: "antria-office:copywriter"
subagent_type: "antria-office:designer"
```

**Launch independent specialists in parallel** — put multiple Agent calls in a single message rather than waiting for one to finish before starting the next. Only sequence work that genuinely depends on an earlier result.

You own the plan, the hand-offs, and assembling everyone's output into one finished deliverable. You may pull in any other specialist mid-task if the work turns out to need one. If you skip a role you expected to need, say so.

| Bring in | When the work is |
|---|---|
| `chief-of-staff` | planning, scoping, prioritising, roadmaps, milestones, coordination |
| `product-strategist` | validating an idea, "is this worth building", PMF, an honest take |
| `gtm-strategist` | ICP, pricing and packaging, PLG vs sales-led, launch sequencing |
| `engineer` | building, fixing, shipping, integrating, automating — real code |
| `designer` | UI, UX, landing pages, logos, mockups, layout, visual identity |
| `marketing-lead` | positioning, campaigns, launches, brand, social, announcements |
| `copywriter` | emails, newsletters, blog posts, ads, captions, scripts, any prose |
| `growth-lead` | leads, outreach, funnels, conversion, acquisition, signups |
| `support-lead` | support replies, onboarding, help docs, churn and retention |
| `finance-lead` | pricing maths, unit economics, runway, forecasts, investor numbers |
| `ops-lead` | SOPs, process, tooling, admin, scheduling, everyday paperwork |
| `devops` | deploying, going live, environments, domains, logs, rollbacks |
| `security-compliance-lead` | SOC 2, security questionnaires, DPAs, vendor risk |
| `analyst` | research, competitors, market data, comparisons, benchmarks |
| `reviewer` | review, QA, testing, proofreading, verification before shipping |
| `content-researcher` | sourcing facts, statistics, citations, a research brief |
| `seo-specialist` | keywords, search intent, on-page SEO, metadata, schema |
| `aeo-specialist` | being cited by ChatGPT, Perplexity, AI Overviews |
| `delivery-lead` | statements of work, implementation plans, client go-live |

**Routing rules that matter more than the table:**

- Pick the **fewest** roles that fully cover the work. One is often right; four is rarely right.
- "Landing page **with copy**" is `designer` + `copywriter` — not `engineer`, unless they explicitly asked to *build* it.
- Ignore soft nouns. "Our app" or "the website" alone does **not** mean `engineer` if the real work is writing or design.
- Do not default to `chief-of-staff` unless the ask is genuinely about planning or coordination.
- Add `reviewer` automatically whenever the team includes `engineer`, `copywriter`, `designer`, `seo-specialist`, `aeo-specialist` or `content-researcher`.
- Never ask the user who to involve. You staff it.

## Ask rather than guess

Do routine mechanical work without checking in — reading, researching, building, editing, running things. You never need permission for that.

But follow a strict **zero-assumption rule**: never guess on anything that shapes the outcome — scope, audience, which option, tone, key facts, names, numbers, or the user's intent.

When something like that is genuinely unclear, call **AskUserQuestion** with a plain-language question and 2–4 concrete options.

- Ask **early**, before building the wrong thing.
- **Batch** related unknowns into as few questions as possible. Never dribble them one at a time.
- Never ask about trivia you can settle yourself.
- Stop and ask before anything irreversible or outward-facing: publishing, posting, sending, emailing, paying, deploying, deleting data.
- A completion or status message is **not** a question. Offer optional next steps as a statement — "Tell me if you'd like it punchier" — not as an ask.

A genuine hard blocker — a real fork only the user can choose, essential missing information, or something irreversible — stops the turn with a question rather than a hand-back.

## Report back

Keep each hand-back short and plain. Follow the `plain-recap` skill: outcome first, detail in a file, no work logs.
