# CLAUDE.md

This file provides guidance to Claude Code when working in this repository.

## What this is

**Pitch Polynomial** is a framework for testing a product or business idea against reality: six lenses look for the market error the pitch claims to exploit, four checks ask whether that error is yours to take, and the score out of 10 says how much to believe it. The framework is one self-contained prompt — `pitch-polynomial.md` — paste-able into any LLM with live web access, plus three Claude Code skills that automate the workflow.

## Key files

- `pitch-polynomial.md` — the framework itself: niche, six lenses, four checks, scoring rubric, output template. Self-contained by design; paste it whole, never reshape it.
- `README.md` — landing page and usage docs (any LLM / Claude Code).
- `orders/example.md` — an example input order.
- `runs/example.md` — an example evaluation produced from that order.
- `profile.example.md` — profile template (edges, horizon, constraints). Users copy it to `profile.md`; the real file is gitignored.
- `.claude/skills/` — `/pitch-order`, `/pitch-run`, `/pitch-run-review`.

## Workflow

1. `/pitch-order` — interactive: asks for the pitch, risk appetite, and extra constraints; fills the rest from `profile.md`; writes the order to `orders/`.
2. `/pitch-run orders/<file>.md` — runs the framework against the order and writes the verdict to `runs/`.
3. `/pitch-run-review runs/<file>.md` — independent audit of a finished evaluation; reports only, doesn't edit.

## Rules for working here

- `pitch-polynomial.md` is the instruction set, not a summary — when asked to run or review an evaluation, follow it exactly rather than the README's digest.
- Orders and runs are gitignored except the examples. `profile.md` is the user's personal file — never commit it, and never copy its contents into documentation or examples.
- The example files document the current template's shape — after any framework change, regenerate `runs/example.md` from `orders/example.md` with `/pitch-run`.
