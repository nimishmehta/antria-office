# Antria Office

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Claude Cowork](https://img.shields.io/badge/Claude-Cowork-d97757.svg)](https://claude.com)
[![Claude Code](https://img.shields.io/badge/Claude-Code-d97757.svg)](https://claude.com/claude-code)

**Turn Claude into a small company.** Describe what you want in plain English. A lead reads the task, staffs the right specialists from a roster of 20, runs the independent work in parallel, and reports back like a colleague — not a terminal.

```
/plugin marketplace add nimishmehta/antria-office
/plugin install antria-office@antria-office
```

Works in **Claude Cowork** and **Claude Code**. No configuration, no API keys, no external services.

---

## Why this exists

Claude can already delegate to sub-agents. What it doesn't do by default is behave like a good colleague while it does — and that turns out to be most of the difference between a demo and something you'd actually hand work to.

A good colleague asks the awkward question *before* spending a day on the wrong thing, and asks it once, with options, instead of pestering you. They hand you the finished spreadsheet, not the script that generates the spreadsheet. They tell you what happened in a sentence, not a wall of check marks. They don't claim something is done when it isn't.

This plugin is those habits, written down, plus a roster of specialists to apply them.

It comes out of [Antria](https://antria.ai), a desktop app built on the same harness. The app needed a whole server to make these behaviours work. As a plugin it's 23 Markdown files and no runtime at all.

---

## The three skills

### `just-do-it` — hand over the whole thing

For when you want a finished result, not a conversation.

> *"Put together a launch email for the new pricing page and make sure the wording is tight."*

The lead staffs a copywriter and a reviewer, runs them, assembles the result, and comes back with the email and one line about what it does. It doesn't ask you who should write it.

Triggers on phrasings like *just do it*, *get this done*, *handle this*, *build me a…*, *put together a…*

### `work-with-me` — shape it as it takes form

For when you want to steer.

> *"Work with me on the investor update — show me an outline first."*

One useful unit per turn, then it hands back and stops. It never chains deliverables unprompted and never declares itself done — you decide that. Revisions come back as the **whole** deliverable again with a one-line `What changed:` at the top, so you always have a complete version rather than a diff to reassemble in your head.

Triggers on *work with me*, *let's do this together*, *one step at a time*, *show me a draft first*

### `plain-recap` — make it readable

Useful on its own, even if you ignore the office entirely.

> *"Summarise what you found for my board."*

Outcome first, in one plain sentence. Tables and detail go into a saved file, not into chat. No tool names, no terminal output, no step-by-step work log. And nothing is called "done" unless a real file was actually saved — otherwise it says *ready to review*.

Triggers on *in plain English*, *no jargon*, *just tell me what happened*, *summarise this for my client*

---

## The roster

Twenty specialists. The lead picks the fewest that genuinely cover the work — usually one or two.

| | |
|---|---|
| **Lead** | `founder` |
| **Planning** | `chief-of-staff` |
| **Strategy** | `product-strategist` · `gtm-strategist` |
| **Build** | `engineer` · `designer` |
| **Marketing** | `marketing-lead` · `copywriter` · `seo-specialist` · `aeo-specialist` |
| **Revenue** | `growth-lead` · `finance-lead` |
| **Customers** | `support-lead` · `delivery-lead` |
| **Operations** | `ops-lead` · `devops` · `security-compliance-lead` |
| **Research** | `analyst` · `content-researcher` |
| **Quality** | `reviewer` |

You can also call one directly when you know exactly who you want:

```
@agent-antria-office:product-strategist  Is this feature worth building?
```

Each one carries a point of view rather than a job title. The product strategist is explicitly the in-house skeptic. The reviewer is required to state what it did *not* check, because a skipped section reported as clean is how bugs survive a thorough-looking review. The finance lead knows the standard SaaS metrics and is instructed to flag them as rules of thumb that can mislead, not laws.

---

## How it works

Three rules do most of the work.

**Staffing is automatic.** You never get asked who should do something. The lead reads the task and decides — and the routing is tuned against the failure modes. "Landing page with copy" staffs a designer and a copywriter, not an engineer. "Our app" in a sentence about writing doesn't summon an engineer either. Anything creative or built automatically picks up a reviewer.

**Independent work runs in parallel.** Specialists whose parts don't depend on each other are launched together, not one after another.

**Questions are batched and come early.** Underspecify a task on purpose and you get one question with a few concrete options, before any work happens — not three questions in a row, and not a confident guess. Mechanical work never asks permission; anything that shapes the outcome always does.

---

## Design notes

A few choices that are deliberate, in case you're adapting this:

**Agents report to the lead, not to you.** They're instructed to be terse to the point of rudeness internally. Only the lead writes anything you read, and only the lead switches into plain language. Polished prose between agents is money spent on nobody.

**The final-artifact rule.** If a script was only the means of producing your file, the agent runs it and hands you the output. You asked for a spreadsheet; you get the `.xlsx`. Code is the deliverable only when you asked for code.

**No tool restrictions on agents.** These roles make things. An agent that can't save a file isn't a designer.

**Nothing executes.** No scripts, no hooks, no MCP servers, no telemetry. See [SECURITY.md](SECURITY.md) — worth a skim before you install anything that tells Claude to act autonomously, including this.

---

## Antria, the desktop app

This plugin is the harness on its own. [**Antria**](https://github.com/nimishmehta/antria-ai)
is the desktop app built on top of it — the same twenty specialists, plus a real interface,
your own folders, work that keeps running after you close the lid, and no terminal.

Free, runs on the Claude or Codex plan you already pay for, Mac and Windows.

You don't need it to use this plugin, and you don't need this plugin to use it. They're the
same office with different front doors.

## Requirements

Claude Cowork, or Claude Code v2.0 or later. Nothing else.

In Cowork, skills usually fire automatically from how you phrase a request. In Claude Code you can also invoke them explicitly as `/antria-office:just-do-it`.

---

## Contributing

Issues and pull requests welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).
The most useful bug report is the prompt you gave, the roles that got staffed, and the roles you expected instead.

| | |
| --- | --- |
| Report a bug or request a role | [Issues](https://github.com/nimishmehta/antria-office/issues) |
| Getting help and debugging staffing | [SUPPORT.md](SUPPORT.md) |
| Contributing | [CONTRIBUTING.md](CONTRIBUTING.md) |
| Reporting a vulnerability | [SECURITY.md](SECURITY.md) |
| Ground rules | [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) |
| Release history | [CHANGELOG.md](CHANGELOG.md) |

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, rename it, ship it in your own thing.
