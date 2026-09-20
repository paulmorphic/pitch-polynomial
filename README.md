<div align="center">

# ∑ Pitch Polynomial

**An evaluator for product and business ideas.**

**Six lenses look for a market error. Four checks ask whether it's yours. The number says how much to believe it.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-blueviolet)](https://claude.com/claude-code)

**[paulmorphic.github.io/pitch-polynomial](https://paulmorphic.github.io/pitch-polynomial/)**

</div>

You already have a product or business idea — this framework tells you where it breaks. Bring a pitch; six lenses look for the market error it claims to exploit, and four checks ask whether that error is yours to take. The output is one verdict: a score out of 10, the evidence behind every part of it, and the single experiment worth running next.

> [!WARNING]
> This is an experimental, proof-of-concept LLM-based framework — not a finished or validated product — shared for informational and educational purposes only. It does not constitute business, financial, investment, or legal advice, and nothing it produces should be treated as a recommendation to take any specific action. Outputs are AI-generated hypotheses, not verified facts — they may be incomplete, outdated, hallucinated, or simply wrong, and are not a substitute for your own due diligence and professional advice. Quality and accuracy also depend heavily on the model you run this with — different models will follow the process with different rigor and reach different conclusions. Use at your own risk; the author accepts no liability for decisions made based on this framework's output.

> **Humility clause.** This framework identifies weaknesses in your idea; it does not predict success. Most ideas won't pan out — the goal is to find the cracks before you invest, not to manufacture certainty. Conviction levels are approximate.

Run it with any LLM, or as a [Claude Code](https://claude.com/claude-code) skill. The full rules live in [`pitch-polynomial.md`](./pitch-polynomial.md) — this page is the short version.

---

### 🔍 How it works

**The niche comes first.** The agent works out where your pitch actually competes — from its mechanics, not from how you framed it — and names the category, the nearest substitutes (including free defaults and manual workarounds), and who actually pays. Every search in the run is framed by those three, not by your wording. Frame a GPU marketplace as "cheaper than cloud" and the search finds expensive cloud pricing; frame it as a GPU rental marketplace and the search finds the incumbent running the same model since 2018. Same pitch, opposite verdict.

**Six lenses look for a market error.** Each asks one question, answers it with its own web search, and ends with a kill condition — the specific way that lens says "this looks like an opening and isn't." Every lens produces one finding: a claim, its source, and a verdict, in one row — the source sits next to the claim.

1. **Linearization trap** — does the curve this pitch rides actually grow the way the pitch assumes? (S-curves, ceilings, the Jevons paradox: automation often *grows* a market rather than shrinking it.)
2. **Complexity / emergence** — is there a genuinely new class of adaptive behaviour here, or a stable problem in new clothes?
3. **Paradigm blindness** — is the pitch on the right side of what experts are over-certain about, in either direction?
4. **Narrative error** — where does this market's story sit relative to what it actually delivers: overheated, underheated, or contradictory?
5. **The ostrich paradox** — is this a problem people want solved, or one they've quietly learned to live with (a script, a spreadsheet, an intern)?
6. **Organizational blindness** — what stops the obvious player from doing this, structurally rather than temporarily?

No lens supporting the pitch is a valid, and common, outcome — so is a lens with nothing to say.

**Four checks ask whether the error is yours.** Timing — can you ship inside the window the evidence shows, given your Horizon? Incumbent and reality each run a hostile search — *who already sells this, at what price* / *who pays for this today, how much* — aimed at the niche, not at your wording. Builder-fit — do your Edges and Constraints put the pitch in the gap between "too hard to build" and "unattractive to whoever could out-resource you"?

**The score.** Five criteria, 0–2 each, out of 10 — **HIGH 8–10 · MEDIUM 5–7 · LOW ≤4**. It's conviction, not probability: how much the evidence supports taking the bet. Four gates cap the verdict regardless of the total: nobody pays for this problem in any form → LOW; two or more lenses kill, on separate facts → LOW; the incumbent ships it as a feature → MEDIUM at best; the niche couldn't be settled → MEDIUM at best. And the number is only half the output: the lowest-scoring criterion is what the two-week experiment has to attack.

---

### 🚀 How to use it

**With any LLM.** Paste the full contents of [`pitch-polynomial.md`](./pitch-polynomial.md) — as the system prompt, or as your first message — then your input, filling in all five fields:

```
Pitch: A marketplace where indie game studios and small AI labs can rent spare
  GPU compute from each other — like Airbnb for GPUs
Edges: 10 years full-stack, hands-on with embeddings/RAG, AWS certified
Horizon: 3–6 months to MVP
Risk appetite: High
Constraints: solo dev, ~$1,000 budget
```

- **Pitch** — what you're building, for whom, why you think it works. Don't frame it favourably — the agent determines the real niche itself.
- **Edges** — concrete capabilities, access, or knowledge others don't have; a named Edge has to cross "too hard to build" to matter.
- **Horizon** — when you want a working product; the timing check asks whether you can ship inside the window.
- **Risk appetite** — exactly `HIGH` or `LOW`, no middle.
- **Constraints** — capital, time, team, funding path; calibrates the builder-fit check.

**Requires live web search.** Every finding carries a source from a search the model actually ran. Use a model/setup with live web access.

**Model.** Minimum recommended: **Opus 5 xHigh** or an equivalent frontier model — the process is only as rigorous as the model running it. Run the framework on different models and compare the output. See the disclaimer warning above.

See [`orders/example.md`](./orders/example.md) for a complete filled-out order.

**Reviewing the output (strongly recommended).** Any part of a run can be wrong — sources, verdicts, scores — and it won't look wrong. For an independent pass on a finished evaluation, start a new conversation and paste [`.claude/skills/pitch-run-review/SKILL.md`](./.claude/skills/pitch-run-review/SKILL.md) followed by the evaluation. It re-checks sources, hostile searches, kill conditions, the score, and the gates — it reports, it doesn't rewrite, but it still doesn't guarantee the correctness of the output; see the disclaimer warning above.

**With Claude Code.** 🤖

- **`/pitch-order`** — asks a few questions, reads your profile, writes an order into `orders/`.
- **`/pitch-run orders/<file>.md`** — runs the full evaluation and writes the verdict to `runs/`.
- **`/pitch-run-review runs/<file>.md`** — independently audits a finished evaluation. Reports only.

Copy [`profile.example.md`](./profile.example.md) to `profile.md` and fill it in once — `/pitch-order` reads it, so you don't retype your background each time. `profile.md` is gitignored.

---

## 📊 Example output

[`runs/example.md`](./runs/example.md) is the result of running `/pitch-run` on [`orders/example.md`](./orders/example.md) — generated with Claude Code, **Opus 5 xHigh** effort.

## 🗂️ Repository layout

```
pitch-polynomial.md    # the framework — "source code"
orders/                # input orders (gitignored, except example.md)
  example.md           # versioned
runs/                  # outputs (gitignored, except example.md)
  example.md           # versioned
profile.example.md     # profile template — copy to profile.md and edit
profile.md             # your profile (gitignored — never commit the real one)
.claude/skills/        # /pitch-order, /pitch-run, /pitch-run-review
docs/index.html        # the website (GitHub Pages)
```

## 📄 License

[MIT](./LICENSE)
