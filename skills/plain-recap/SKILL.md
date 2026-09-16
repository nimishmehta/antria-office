---
description: >
  This skill should be used when reporting finished work to a non-technical reader, or when
  the user says "in plain English", "no jargon", "just tell me what happened", "explain it
  simply", "summarise this for my board", "write this up for my client". Enforces
  outcome-first reporting and keeps tables, logs and code out of chat.
---

# Plain recap

You are reporting to someone non-technical who wants **semantic progress** in the fewest words: what moved, what it means, and the decision or next step. Never how the work was done.

## Shape

Lead with the outcome in **one plain sentence** a busy non-coder gets instantly. Then at most two or three short lines.

Talk like you would to a friend who runs a business. Report outcomes, not activity.

## Banned in any user-facing message

- Markdown or pipe tables
- PASS/FAIL, check/evidence/verdict grids, row-by-row results
- Raw number dumps
- Format tags — JSON, XML, cell references
- Tool names, file internals, terminal output
- Cryptic abbreviations and unexplained insider jargon
- Step-by-step "here is what I did" work logs

Any rich, tabular or detailed result goes into a **saved file or a self-contained artifact**. In chat you say, in one line, what it shows and where it is.

## The one exception

When the user must **run or copy** a command or a short snippet, put it in a fenced code block right there in chat with one plain sentence of what it does. Never bury a command they need in their hand inside a file.

## Never claim more than you did

- Never say "done", "delivered", "shipped", "finished" or use a ✅ unless you actually saved a real deliverable. If nothing was saved, say **"ready to review"**.
- Never end your turn as finished while a long external job you started is still running — a build, an upload, a deploy. Wait for it and hand back the proof, or make your last line a "still running" status so it's clear the work is live.

## The final-artifact rule

The deliverable is the **finished file the user opens** — a spreadsheet, document, PDF, deck, image, chart, or page. It is **never the code that produces it**.

If a script is only the means to build that file, run the script yourself and hand over the output. Someone who asked for a spreadsheet gets the `.xlsx`, not `build_it.py`.

The only times code itself is the deliverable: they explicitly asked for a script or automation, or you are building the product's own source.

If code was needed to generate the artifact, keep it aside. The thing you name in chat and hand back is the generated file.
