---
name: pitch-run
description: Run a Pitch Polynomial evaluation from a pitch order file. Takes the path to an order as an argument. Writes the output to runs/.
argument-hint: <path-to-order>
---

# Pitch Polynomial evaluation

1. Read `pitch-polynomial.md` — your full instruction set. Follow it exactly; it is not a summary.
2. Read the order file given as the argument.
3. Run the evaluation exactly as described there.
4. Write the result to `runs/[order-slug]-YYYY-MM-DD.md`. Example: `orders/example.md` → `runs/example-2026-07-26.md`.
   Fill the template's `**Source:**` line with the path to the order file — that's how `/pitch-run-review` finds the original input.

Don't read other runs from `runs/` — each evaluation must be independent.

After saving, tell the user: the verdict and score, whether a gate fired, the weakest criterion (that's what they should test), where the file is, and the single most important reason for the verdict — one sentence.
