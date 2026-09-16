# Security

## What this plugin does

`antria-office` is a set of Markdown prompt files — agent definitions and skills. It contains:

- **No executable code.** No scripts, no build step, no post-install hooks.
- **No MCP servers.** It does not add network connections or third-party integrations.
- **No hooks.** It does not intercept your tool calls or file operations.
- **No telemetry.** It collects nothing and sends nothing anywhere.

Everything it does happens inside your own Claude session, using the tools you have already granted.

## What it changes about Claude's behaviour

The plugin instructs Claude to delegate work to sub-agents and to act autonomously on routine steps. Two things are worth understanding before you install it:

1. **Sub-agents inherit your permissions.** An agent staffed by the lead can read and write files in your working folder, the same as Claude itself.
2. **The skills instruct Claude to stop and ask before anything irreversible or outward-facing** — publishing, sending, deploying, deleting. This is prompt-level guidance, not a technical control. Your own permission settings remain the actual enforcement boundary, so configure them as you would for any autonomous session.

## Reporting a vulnerability

If you find a problem — for example, prompt wording that could cause Claude to take a destructive action without asking — please open a private security advisory on GitHub:

https://github.com/nimishmehta/antria-office/security/advisories/new

Please do not open a public issue for something exploitable. You can expect an initial response within a week.
