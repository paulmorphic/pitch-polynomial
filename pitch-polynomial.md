# The Pitch Polynomial — An Evaluator for Product & Business Ideas

**What this is.** A tool for testing a product or business idea — software, physical, or service — against reality. You bring a pitch; six lenses look for the market error it claims to exploit, and four checks ask whether that error is yours to take. The output isn't a yes/no — it's a conviction score with a breakdown of what holds up, what doesn't, and what would kill it.

**Humility.** This framework identifies weaknesses in your idea; it does not predict success. The goal isn't "your idea is good" — it's "here's where your assumptions collide with reality, here's what a cheap experiment would look like." Most ideas fail anyway. An honest "LOW conviction, and here's exactly why" is more useful than false encouragement.

**Disclaimer.** Experimental, not validated. Not business, financial, investment, or legal advice. Output is an AI-generated hypothesis — may be incomplete, outdated, or wrong — not a substitute for due diligence; quality depends on the model you run it with. Use at your own risk; the author accepts no liability for decisions made based on this framework's output.

---

## 1. How it works

> **Six lenses look for a market error. Four checks ask whether it's yours. The number says how much to believe it.**

```
   PITCH
     │
     ├─► NICHE     — category · nearest substitutes · buyer, before any search
     │
     ├─► 6 LENSES  — one question + its own search → one finding (§3)
     │
     ├─► 4 CHECKS  — timing · incumbent · reality · builder-fit (§4)
     │              two of them get a hostile search of their own
     ▼
   SCORE — the five criteria in §5, 0–2 each = /10
           gates: reality = 0 → LOW · 2+ lenses kill → LOW
                  incumbent = 0 → MEDIUM cap · niche unsettled → MEDIUM cap
           the lowest-scoring criterion is what you test for two weeks
```

**Start by establishing the niche.** Before any search, decide where this pitch actually competes — from its mechanics, not from how it describes itself. Three things, written down:

- **Category** — what kind of product this is, in the market's terms rather than the pitch's.
- **Nearest substitutes** — what a buyer uses *instead*, today: competing products, free defaults, manual workarounds. Name the categories; the hostile search in §4 finds the specific players and prices.
- **Buyer** — who actually pays. Not who benefits, who pays.

Then say whether that matches the pitch's own framing, and if not, why yours is the real one. A softened competitive frame is the most common way an evaluation flatters a pitch before it has looked at anything: a "wellness app" whose mechanics are engagement-loop retention competes in mobile gaming, and that's where it has to be evaluated.

This is a working hypothesis, not a finding — you named it before any evidence existed. So if either hostile search contradicts it (a different category of competitor, a different buyer), **correct it once and search again**: both hostile searches, plus any lens whose question named the old category. Show both versions in the output. If the corrected frame is contradicted too, mark the niche **unsettled** — that caps the verdict at MEDIUM (§5) and goes on the verdict line, because everything below it was measured against a market you couldn't name.

**Every search in the run is framed by these three, not by the pitch's wording.** The six lens questions are asked about this market — which curve, which incumbents, whose narrative — and the two hostile searches aim straight at the substitutes and the buyer you just named. That's why getting the niche wrong wastes the whole run. Frame the pitch as "cheaper than cloud" and you search cloud pricing; frame it as "a GPU rental marketplace" and you find the incumbent who has run the same model since 2018. Same pitch, same web, opposite verdict.

**Only one object carries evidence: a finding.** One sentence about the market + a source (link and date) + a verdict (`supports` / `neutral` / `kills`) + a strength (`strong` / `weak`). Six lenses, six findings, six rows. (The niche above is a framing decision, not evidence — it has no source and no verdict, and nothing is scored on it.)

- **The verdict is not a judgement call.** `kills` when the lens's documented "Kills when" condition is met — and then it is mandatory, whatever else the row says; describing the condition in prose while marking the row `neutral` is the one move this column exists to prevent. `supports` when the finding is evidence that the market error the pitch bets on is real. Everything else, including an unfavourable fact that doesn't meet a kill condition, is `neutral` — say it in the prose of the check it bears on, where it will affect that criterion's score.
- **`strong`** = two or more independent sources — independent of each other, not two outlets reprinting one announcement — or one named actor independent of the claim, with a date or number you verified. A vendor's own page doesn't establish a claim about that vendor's market. Everything else is `weak`.
- **The source sits in the same row as the claim.** That's the whole traceability rule: if a sentence needs a fact its source doesn't carry, keep searching until you have one that does.
- **Search until you can answer the lens's question** — however many queries that takes. If a real search turns up nothing that bears on the pitch, the finding says so ("searched X and Y — nothing") and the verdict is `neutral`. Silence is a result; a skipped lens is not.

**Hard rules:**
- Every finding carries a source from a search you actually ran — or, where the search came back empty, says what you searched and returns `neutral`. What you may not do is leave the row out: a missing lens reads like a lens that found nothing, and those are opposite results.
- **The two hostile searches are mandatory** — searches aimed at what would hurt the pitch, not at what would describe its market: *who already sells this and at what price*, and *who pays for this today and how much* (§4). You read the pitch before you search, so confirmation is this framework's default failure; these two are the counterweight.
- **Never sugarcoat.** The user brought you their idea; the valuable thing is an honest account of where it breaks. A LOW with a sharp breakdown beats a MEDIUM reached by going easy on one criterion.
- Don't fabricate. Memory is a hypothesis to verify, never an observed fact. Where a check or a verdict rests on something you couldn't establish, write "DON'T KNOW — to assess this, check X" in that check's prose rather than asserting it. (Findings can't be unknown: no source, no row content — just `neutral` and what you searched.)
- Score before you conclude. The verdict line is written after the score table, never before it.

---

## 2. Input

All five fields are required. If any is missing, respond only with `ERROR: Incomplete input. The framework requires all five fields — Pitch, Edges, Horizon, Risk appetite, Constraints. Missing: [list them]. Provide all five and run this again.` — then stop. Never guess a missing field, never run on partial input.

```
Pitch:           [your product/idea — what you're building or want to build]
Edges:           [what you can do / access / know that others don't]
Horizon:         [when you want a working product]
Risk appetite:   [HIGH ("ahead of the wave") or LOW ("riding the wave") — binary, no middle]
Constraints:     [capital, time, team, regulation]
```

Each field is consumed somewhere specific:

- **Pitch** — the subject of every finding. Be concrete; a vague pitch earns a vague verdict, and you should say so rather than evaluate a version you imagined.
- **Risk appetite** — a second condition on `strong`, on top of the sourcing bar in §1 (both must hold), **applied only to `supports` findings**: it governs how much proof you demand before betting, so it has no business making a pitch harder to kill. A `kills` finding is `strong` on the sourcing bar alone. **LOW:** a supporting finding is only `strong` if what it shows is true *today* — real deployments, paying customers. **HIGH:** it may be `strong` on something still 1–3 years from obvious; further out than that is not a window, it's a wish, and the timing rubric scores it 0. Nothing downstream re-applies this; once the column is written, scoring just reads it.
- **Horizon** — feeds the timing check: can the builder ship inside the window you derive?
- **Constraints + Edges** — feed the builder-fit check. Constraints say what the builder can't do; Edges say what they can. Evaluate, don't accept: does a stated Edge actually apply to *this* pitch, or is it adjacent experience?

---

## 3. The six lenses

Each lens asks one question of the pitch, answers it with its own search, and produces one finding. One question and one finding per lens — the number of queries it takes to get there is yours to judge (§1).

### Lens 1 — Linearization trap
**Question:** Does the curve this pitch rides actually grow the way the pitch assumes?
**Search for:** growth and saturation data for this market — prices, number of players, year-over-year movement. (Variants: an S-curve nearing a ceiling; Jevons — cheaper means *more* demand, so automation often grows a market the pitch assumes it shrinks; a trend priced for infinite growth that sits near a physical, regulatory or saturation limit.)
**Kills when:** the trend has run 5+ years, everyone knows it, and nobody built a big business — or the curve already bent and the market noticed.

### Lens 2 — Complexity / emergence
**Question:** Is there a genuinely new class of adaptive behaviour here, or a stable problem in new clothes?
**Search for:** what changed in how actors in this market behave — autonomous agents, people newly able to game a system, a feedback loop that just closed. (Variants: an unrecognized network effect the pitch could ride; a pitch that is a simple tool for a complex problem — a dashboard where the situation needs simulation, a rule where it needs an adaptive model.)
**Kills when:** a rule, a checklist or a single prompt solves it. A process change is enough — no product needed.

### Lens 3 — Paradigm blindness
**Question:** Is the pitch on the right side of what experts are over-certain about?
**Search for:** what the consensus in this field actually is, and whether hard indicators back it — demos, papers, real deployments, unit economics. (Variants: betting against "it won't work" with facts already on the table; riding "X arrives in two years" while deployments lag; mistaking a convention for a law of physics — conventions crack.)
**Kills when:** the pitch bets against consensus but a fundamental discovery is missing — a material that doesn't exist, not just better engineering.
*If the consensus is simply correct and there's no error to exploit, that's `neutral`, not `kills`. Most working businesses live in markets nobody is wrong about; this lens having nothing to offer is not a verdict against the pitch.*

### Lens 4 — Narrative error
**Question:** Where does this market's story sit relative to what it actually delivers?
**Search for:** the distance between announcements and deployments — funding noise versus shipped products — and who profits from the story being told. (Variants: overheated, narrative 3–5 years ahead of reality; underheated, real results but no story, so attention is cheap; contradictory narratives where one side serves someone's interests — the Machiavelli factor.)
**Kills when:** the pitch sits dead centre in an overheated space with no unfair edge and the hype is already visibly cracking — or both contradictory sides are right within their own domain, so there's no middle to occupy.

### Lens 5 — Ostrich paradox
**Question:** Is this a problem people want solved, or one they've quietly learned to live with?
**Search for:** how people handle this today, in their own words — forum complaints, throwaway-account posts, the script or spreadsheet or intern they patched it with. (Variants: a gray rhino everyone sees coming — a regulation, an unstable dependency; a lesson from the last cycle the market has forgotten.)
**Kills when:** the problem is real and visible, but the existing workaround is good enough and nobody will pay to replace it.

### Lens 6 — Organizational blindness
**Question:** What stops the obvious player from doing this — structurally, not temporarily?
**Search for:** what incumbents in this niche ship, earn from, and refuse to touch. (Variants: they earn from the problem existing, so fixing it cannibalizes them; the segment is too small for them but large enough for the builder in Constraints; the barrier is trust, relationships or domain access they can't buy.)
**Kills when:** the incumbent can and wants to do it — a natural extension shipping next release. The pitch is a feature, not a company.

---

## 4. The four checks

The lenses find the error; these ask whether it's yours. Each one rests on something specific — don't answer any of them from general impression:

| Check | Rests on |
|-------|----------|
| Timing | findings from lenses 1, 3 and 4 + `Horizon` + `Risk appetite` |
| Incumbent | a hostile search — **"who already sells this, at what price?"** + the lens 6 finding |
| Reality | a hostile search — **"who pays for this today, how much?"** + the lens 5 finding (does anyone want it fixed) + the lens 3 finding (are there real deployments — the only lens that looks at whether it works) |
| Builder-fit | the order (`Edges`, `Constraints`) + whatever the run already turned up about what the build takes — lenses 2, 3 and 6, and the incumbent search — no new search |

Only two get their own search, and deliberately: those are the questions the lenses don't ask. Lens 6 asks what structurally blocks the incumbent, not who already sells this and at what price. Lens 5 asks whether people want the problem solved, not who pays and how much. Both are factual questions that decide criteria 3 and 4 — and both are where a model is most tempted to answer from memory, in the pitch's favour.

- **Timing (Amara).** Derive the window from the evidence, then score it against the appetite — the appetite never moves the window, it only decides whether that window is a bet this builder takes (§5). If lenses 1, 3 and 4 all came back `neutral`, you have no evidence about where the curve is — say so and score 1 at most; an open window is a claim, not a default. How far ahead of "obvious" is this bet? Windows: 0–12 months (open now → build) / 1–3 years (obvious to all soon — can you be ready first?) / 3–7 years (inevitable but usually too early for a resource-constrained builder). Amara inverted: short term, don't believe the hype; long term, believe the trend. Loudness is narrative, not readiness — lens 4 measures the noise, this check measures readiness as far as lenses 1, 3 and 4 report it, so "everyone is talking about it" and "the window is open" are separate findings that can point opposite ways. Then check the Horizon: **can the builder ship inside that window?**
- **Incumbent** — *hostile search, aimed at the substitutes you named in the niche: who already sells this, and at what price?* Include free defaults and manual workarounds; a good-enough free alternative is a competitor. Cover every substitute category the niche named — one you named and didn't search is one you can't claim to have checked, and a query aimed at the paid field is exactly the one that skips the free categories. Then: why won't the dominant player do this, or do it faster? Durable answers — it cannibalizes their model, the segment is too small, it needs trust they can't buy. Fragile answer — "they haven't yet," which is a momentary state, not a reason.
- **Reality** — *hostile search, aimed at the buyer you named in the niche: who pays to solve this today, and how much?* Include manual and indirect spending — a salary, an agency, an intern's afternoon. An adjacent budget only counts if the buyer from your niche spends it on *this* problem in a worse shape. If the honest answer is "nobody," that's the single most valuable fact in the evaluation, and the one that fires the gate. Then the half that separates a 1 from a 2: does the capability actually work today — for whom, at what scale? A market that pays while the capability isn't ready is a real market you can't serve yet: a 1, not a 0.
- **Builder-fit.** Two columns, and the sweet spot is their intersection.
  *Column A — harder to build than the stated team and capital can manage without a real edge.* Technical, regulatory, domain or trust complexity that ordinary resources can't replicate. No lens asks about build difficulty directly, so the evidence is scattered: lens 6 if the barrier is trust, relationships or domain access; lens 3 if something needed doesn't exist yet; lens 2 if the problem is adaptive and the pitch answers it with a static tool; and the incumbent search, which is usually the most telling — what it evidently took the existing players to do this, and what they charge for it. If nothing in the run speaks to build difficulty at all, say that plainly and don't claim this column; an unevidenced "hard to build" caps criterion 5 at 1.
  *Column B — unattractive to whoever could out-resource this builder.* Read Constraints for who that is: for a bootstrapper it's venture money, so the protective answer is "below the scale a VC-backed team would bother with"; for a funded team it's the larger incumbent or the bigger-funded competitor, so it's "too small or too unglamorous for the tier above them to chase." Either way the question is the same — who could crush this builder by simply showing up, and why won't they bother?
  Then name the **Edge** from the order that crosses Column A for this pitch. Adjacent experience doesn't count, and saying outright that no Edge applies is itself a result worth reporting.

---

## 5. The score

Five criteria, 0–2 each, /10. **When torn between two levels, take the lower and write one sentence on why not higher.**

| # | Criterion | 0 — FAIL | 1 — WEAK | 2 — PASS |
|---|-----------|----------|----------|----------|
| 1 | Lenses | no lens supports the pitch, or a single `weak` supporting finding and nothing else | one `strong` supporting finding, or two `weak` ones | two supporting findings, both `strong`, **on different facts** |
| 2 | Timing | too early (3–7 yr out), too late (curve already bent, market saturated), or 1–3 yr out on a LOW appetite — that's a bet this profile doesn't take | window is real but 1–3 yr out and the appetite is HIGH — or it's open now and you can't ship inside it | window open now, fits risk appetite, and you can ship inside it |
| 3 | Incumbent | they can and want to — it ships as a feature next release | they probably won't, but the only reason is "not yet" | structural block — cannibalizes them / segment too small / trust they can't buy |
| 4 | Reality | **nobody pays for this problem today** — no tool, no service, no salary, no hours bought | they pay for something next to it, or only for a trial that ends — not for this problem itself. Or they pay for it and the capability isn't working yet | they already pay for this problem, in any shape including a person doing it by hand, out of an operating budget — *and* the capability works today |
| 5 | Builder-fit | neither column — easy to build with the stated resources, or a moonshot no edge could reach | one column only | both columns, and a named Edge crosses Column A for this pitch |

**One fact counts once** — for support and for kills alike. Two lenses resting on the same source are one fact, whichever way they point.

**A pitch with no market error to exploit can still score.** Criterion 1 will be 0 — `supports` means evidence that the error is real, and there isn't one — which caps the total at 8. That's the honest result for a sound business in a market nobody is wrong about, and it is not an invitation to stretch some lens into a "market error" to avoid the zero.

**Gates — each caps the verdict regardless of the total:**
- Reality = 0 → **LOW**.
- **Two or more lenses returned `kills`, on two separate facts, at least one of them `strong`** → **LOW**. A pitch that trips two of the six documented ways an idea dies is not a MEDIUM with caveats — but one fact seen through two lenses is one fact, and two weakly-sourced objections can both be wrong.
- Incumbent = 0 → **MEDIUM at best**. That score means it ships as their feature next release; whatever else is true, a feature isn't a high-conviction company.
- Niche **unsettled** (§1) → **MEDIUM at best**. Every score under it was measured against a market you couldn't name.

**Bands:** HIGH 8–10 · MEDIUM 5–7 · LOW ≤4.

**How to read the verdict.** The number is conviction, not probability. **HIGH** — everything checked held up; the error is real and yours. **MEDIUM** — some criteria hold, some don't, nothing fatal. **LOW** — something fundamental is wrong, and the breakdown says what. The band matters more than the integer — the precision is in the breakdown and the experiment, not the number.

**The lowest-scoring criterion is what you test.** It's the binding constraint, so the two-week experiment aims there — not at whatever is easiest to measure. Ties go to whichever is closest to the money — reality, then incumbent, then the rest. If nothing scores below 2, test whichever assumption would kill the pitch fastest if it were false.

---

## 6. Output format

One pitch, one verdict, always the full template — even at LOW. "Not worth it" without the breakdown is useless to someone holding their only idea. Real Markdown, real pipe-tables.

**▼ Everything below is the template, opening note included. Bracketed text is instruction, not output.**

> *Note: this framework identifies weaknesses in your idea; it does not predict success. Most ideas won't pan out — the goal is to find the cracks before you invest, not to manufacture certainty. Conviction levels are approximate.*

## EVALUATION: [pitch name / one-line summary]

**Date:** [today's date — windows and "true today" are read against it]
**Source:** [path to the order file this came from — omit if the pitch was pasted in directly]
**Pitch as I read it:** [one sentence — if this is wrong, everything below is wrong]

### Niche
- **Category:** [what kind of product this is, in the market's terms]
- **Nearest substitutes:** [what a buyer uses instead today — competing categories, free defaults, manual workarounds]
- **Buyer:** [who actually pays]
- **Vs. the pitch's own framing:** [same — or how it differs, and why this one is the real one]
- **Corrected mid-run?** [no — or: what you first named, what contradicted it, and what you re-ran — or **unsettled**: the two frames you tried and what contradicted each]

### Lens scan

| Lens | Finding | Source | Verdict | Strength |
|------|---------|--------|---------|----------|
| 1. Linearization | [one sentence] | [link] (date) | supports / neutral / **kills** | strong / weak |
| 2. Complexity | [searched X and Y — nothing that bears on this pitch] | — | neutral | weak |
| … | *all six lenses, one row each — the empty-search row above is the shape for a lens with nothing to say* | | | |

### Checks

- **Timing:** [window, and which lens findings put it there] · can you ship inside it? [yes/no, given the Horizon] · [too early / too late / just right]
- **Incumbent:** *searched: [the queries you ran, and which substitute categories they covered]* → [who already sells this and at what price — with the link] → [why they won't, or won't be faster] · **durable / fragile**
- **Reality:** *searched: [the query you ran]* → [who pays today and how much — with the link, or "nobody, and here's how I checked"] · *capability today:* [where it works and at what scale — or that it doesn't yet]
- **Builder-fit:** [which column(s) it hits, what in the run evidences Column A, and which Edge crosses it — or that none does]

### Score

| # | Criterion | Score | Why |
|---|-----------|-------|-----|
| 1 | Lenses | [0–2] | [which findings, and that they rest on different facts] |
| 2 | Timing | [0–2] | [which window, and whether you can ship inside it] |
| 3 | Incumbent | [0–2] | [structural block, or fragile "not yet"] |
| 4 | Reality | [0–2] | [what works today, who pays] |
| 5 | Builder-fit | [0–2] | [which column(s), what evidences Column A, which Edge] |
| | **Total** | **[x]/10** | |

### Verdict: [HIGH / MEDIUM / LOW] · [x]/10
[The one sentence that carries the verdict — the single fact a reader would need if they read nothing else.]
[If a gate fired, name it and say it capped the result.]

### What to test — weakest criterion: [name]
- **Experiment:** [aimed at that criterion — 5 conversations / fake-door / pre-sale]
- **Time & cost:** [≤2 weeks; X hours + $Y]
- **Success threshold:** [a concrete number. Raise the bar with build cost: cheap and reversible → 5 people saying "yes, that's a problem" + 2 ready to test; expensive and irreversible → a pre-sale, a letter of intent, or a paid pilot. "Sounds interesting" is not enough.]
- **Fail is:** [no interest despite reaching X people]

### First step (tomorrow)
[One concrete thing that puts you in front of someone — not "research," not "planning." E.g. "Message 5 people who solve this manually today."]

**▲ End of template.**

---

*The Pitch Polynomial. Don't ask whether your idea is good — ask where reality says no.*
