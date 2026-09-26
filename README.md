<div align="center">

# ∑ Pitch Polynomial

### *Don't ask whether your idea is good — ask where reality says no.*

**Six lenses look for a market error. Four checks ask whether it's yours. The number says how much to believe it.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![One prompt](https://img.shields.io/badge/Framework-One_prompt-blue)
![Any LLM](https://img.shields.io/badge/Runs_on-Any_LLM_with_web_search-green)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-skills-blueviolet)](https://claude.com/claude-code)

**[paulmorphic.github.io/pitch-polynomial](https://paulmorphic.github.io/pitch-polynomial/)**

</div>

---

You have an idea you're about to spend months on. Pitch Polynomial goes looking for the evidence that would kill it — who already sells this, who actually pays, which market you're actually in. You get a score out of 10, a source behind every finding, and the one experiment worth running next.

It's one self-contained prompt. Paste it into any LLM with live web search, or run it as Claude Code skills.

## Who it's for

- **Founders and indie builders** holding an idea they're about to spend months on
- **Anyone who already has a pitch** — this doesn't generate ideas, it stress-tests the one you have
- **People who'd rather hear "LOW, and here's exactly why"** than be encouraged into building something nobody pays for

## What you get

A full evaluation runs several pages: the niche, six findings each with its source, four checks with the hostile searches spelled out, the score table, the verdict, a two-week experiment, and one thing to do tomorrow.

**[Read a real run — an "Airbnb for GPUs" pitch →](./runs/example.md)**

## 🚀 Quickstart

**Any LLM** (needs live web search):

1. Copy [`pitch-polynomial.md`](./pitch-polynomial.md) in full — as the system prompt or your first message.
2. Add your order:

```
Pitch:          what you're building and for whom — don't frame it favourably
Edges:          what you can do, access or know that others can't
Horizon:        when you want a working product
Risk appetite:  HIGH or LOW
Constraints:    capital, time, team, regulation
```

A filled-in order: [`orders/example.md`](./orders/example.md).

**Claude Code:**

```bash
git clone https://github.com/paulmorphic/pitch-polynomial.git && cd pitch-polynomial
cp profile.example.md profile.md    # fill in once: edges, horizon, constraints
```

- **`/pitch-order`** — a few questions about your pitch, writes an order to `orders/`
- **`/pitch-run orders/<file>.md`** — runs the evaluation, writes the verdict to `runs/`
- **`/pitch-run-review runs/<file>.md`** — independent audit of a finished run

**Model:** use a frontier model — minimum recommended **Opus 5 xHigh** or equivalent. The process is only as rigorous as the model running it.

## Why it says no

The pitch is read before anything is searched, so confirmation is the default failure. Every rule below is a counterweight:

- **Niche first.** Before any search, it decides where your pitch actually competes — from its mechanics, not your framing. "Cheaper than cloud" searches cloud prices; "GPU rental marketplace" finds the incumbent running it since 2018.
- **Hostile searches.** Two mandatory searches aimed at what would hurt you: *who already sells this, at what price* and *who pays for this today, how much.*
- **Every finding has a source.** Link and date in the same row as the claim. No source, no finding.
- **Every lens has a kill condition.** When it's met, the verdict is `kills` — not a softened `neutral`.
- **Gates override the total.** Nobody pays for this → LOW. Two lenses kill, on separate facts, at least one strongly sourced → LOW. The incumbent ships it as a feature → MEDIUM at most.
- **Ties go down.** Torn between two scores, it takes the lower one and says why not higher.

## The six lenses

| Lens | Asks |
|------|------|
| Linearization trap | Does the curve this pitch rides actually grow the way it assumes? |
| Complexity / emergence | Is there genuinely new adaptive behaviour here, or a stable problem in new clothes? |
| Paradigm blindness | Is the pitch on the right side of what experts are over-certain about? |
| Narrative error | Where does the market's story sit relative to what it actually delivers? |
| Ostrich paradox | Do people want this solved, or have they learned to live with it? |
| Organizational blindness | What stops the obvious player from doing this — structurally, not temporarily? |

Then four checks — **timing, incumbent, reality, builder-fit** — ask whether the error is yours. Five criteria, 0–2 each, make the score out of 10: **HIGH 8–10 · MEDIUM 5–7 · LOW ≤4**. The full rules live in [`pitch-polynomial.md`](./pitch-polynomial.md).

## Review the output

Any part of a run can be wrong and still look right. For an independent pass, open a new conversation, paste [`.claude/skills/pitch-run-review/SKILL.md`](./.claude/skills/pitch-run-review/SKILL.md) followed by the evaluation — or run `/pitch-run-review` in Claude Code. It re-checks sources, kill conditions, the score and the gates, and reports without rewriting.

## 🗂️ Repository layout

```
pitch-polynomial.md    # the framework — one self-contained prompt
orders/example.md      # example input
runs/example.md        # example output
profile.example.md     # copy to profile.md (gitignored)
.claude/skills/        # /pitch-order, /pitch-run, /pitch-run-review
docs/index.html        # the website
```

## ⚠️ Disclaimer

> This is an experimental, proof-of-concept LLM-based framework — not a finished or validated product — shared for informational and educational purposes only. It does not constitute business, financial, investment, or legal advice, and nothing it produces should be treated as a recommendation to take any specific action. Outputs are AI-generated hypotheses, not verified facts — they may be incomplete, outdated, hallucinated, or simply wrong, and are not a substitute for your own due diligence and professional advice. Quality and accuracy also depend heavily on the model you run this with — different models will follow the process with different rigor and reach different conclusions. Use at your own risk; the author accepts no liability for decisions made based on this framework's output.
>
> This framework identifies weaknesses in your idea; it does not predict success. Most ideas won't pan out — the goal is to find the cracks before you invest, not to manufacture certainty.

## 📄 License

[MIT](./LICENSE)

---

<div align="center">

⭐ **Star it if you'd rather find the cracks before you build.**

</div>
