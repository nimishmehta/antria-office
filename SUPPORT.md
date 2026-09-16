# Support

## Getting help

**A skill isn't triggering, or the wrong specialists get staffed** → [open a bug report](https://github.com/nimishmehta/antria-office/issues/new?template=bug_report.yml)

**You want a role or behaviour that doesn't exist** → [open a feature request](https://github.com/nimishmehta/antria-office/issues/new?template=feature_request.yml)

**You want to change how a role behaves** → the agent prompts are plain Markdown in `agents/`. Edit one, try it, and send a pull request. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Debugging a staffing problem

Most reports come down to routing — the lead staffed the wrong specialist, or a
skill didn't fire at all. Two things to check first:

**Did the skill trigger?** In Cowork, skills fire by matching your phrasing
against their `description`. If nothing happened, try naming it directly:
`/antria-office:just-do-it`. If that works, the description needs widening —
tell us the phrasing you used, that's exactly the useful detail.

**Who got staffed?** The lead announces its team. If a writing task pulled in an
engineer, or a build task skipped the reviewer, that is a routing bug worth
reporting.

## What to include

- The exact prompt you gave
- Which roles got staffed
- Which roles you expected instead
- Whether you were in Claude Cowork or Claude Code

That combination is almost always enough to find the problem in an agent
`description` or in the routing rules in `skills/just-do-it/SKILL.md`.

## Response times

This is a free plugin maintained alongside other work. Expect a reply within a
week. Pull requests that include a before/after of the behaviour get looked at
fastest.
