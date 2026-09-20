---
name: pitch-run-review
description: Review a finished Pitch Polynomial evaluation for factual accuracy, score-rubric consistency, internal consistency, and format compliance. Takes the path to an evaluation file. Reports findings only — does not edit the file.
argument-hint: <path-to-evaluation>
---

# Review a Pitch Polynomial evaluation

Independently re-verify a finished evaluation. Assume at least one score or one fact is wrong until you've rechecked it yourself — a model reviewing work of this shape tends to rubber-stamp it.

**Scope.** This is verification, not re-evaluation. Don't establish the niche yourself, don't run the lenses, don't form your own opinion of the pitch. The one exception is Step 3: fact-checking a claim already on the page is verification, not new research.

**Read first:** the evaluation, the order it came from (the `Source:` path in its header — runs written before the current template use `Pitch:` instead), and `pitch-polynomial.md` — the rubric you're checking against.

## 1. Is the evidence real?

This is the fastest way to catch an evaluation argued from vibes. Every finding is one row: sentence + source + verdict + strength.

- **Every row has a source you can retrieve**, or says outright what was searched and that nothing turned up. A confident sentence with no link is an opinion wearing a citation's clothes.
- **The source carries the claim.** Open it. If the row says "$69/mo" or "since 2018," the page has to say that — not something adjacent that the sentence stretched.
- **`strong` means what the rubric says:** two independent sources, or one named actor *independent of the claim*, with a date or number. A `strong` resting on one vendor's own marketing page is a finding — vendors verify only that they said it. Risk appetite adds a second condition on top, **for `supports` findings only**: under **LOW**, a supporting `strong` has to show something true *today*, so a supporting `strong` resting on a two-years-out window is a scoring error even when the sourcing is impeccable. Don't apply this to `kills` — a killing finding is `strong` on the sourcing bar alone, by design, so that a cautious profile isn't harder to kill than an aggressive one.
- **The niche survived contact with the evidence.** If the incumbent search turned up a different category than the niche names, the framework requires going back, correcting the niche and re-running both hostile searches, plus any lens whose question named the old category, in the corrected frame — with both versions shown. An evaluation that found a surprising competitor and carried on inside the original frame skipped that loop.
- **The hostile searches were aimed at the stated niche, not at the pitch's wording.** The queries are now in the output, under Checks — read them, don't infer them from the results. This is the highest-leverage thing you can check, because it happens before any evidence exists and it silently decides the verdict. Read the niche's `Nearest substitutes` and `Buyer`, then read what the incumbent and reality searches actually looked for. If the niche names substitutes the incumbent search never went near, the search was pointed at the wrong market and its result is worthless however well-sourced it looks. Also judge the niche itself: does it follow from the pitch's mechanics, or did it accept the pitch's self-description? "Cheaper than cloud" and "a GPU rental marketplace" are the same pitch and opposite verdicts.
- **Both hostile searches ran, and were genuinely hostile.** The incumbent check needs "who already sells this and at what price" (free defaults and manual substitutes count); the reality check needs "who pays today, how much." A friendly result relabelled as hostile is the most important thing you can catch here — it's the framework's main defence against confirmation, and disabling it is invisible in the prose.
- **All six lenses have a row.** A missing lens reads like a lens that found nothing; those are not the same, and only one of them is honest.

## 2. Does the score follow from what's written?

Go criterion by criterion through the Section 5 table, using the evaluation's own stated reasoning — nothing outside the document. Check which of the three level descriptions that reasoning actually matches, then compare to the number given. Flag differences, and say whether the difference crosses a HIGH/MEDIUM/LOW band.

Specific traps:
- **Criterion 1** needs two `strong` supporting findings on **different facts** for a 2 — two lenses resting on the same source are one fact.
- **Criterion 2** needs both an open window *and* the ability to ship inside it for a 2.
- **Criterion 5** needs a *named* Edge from the order crossing Column A (too hard to build) — adjacent experience doesn't count. Column A also has to be evidenced by something the run actually found (lens 2, 3 or 6, or the incumbent search); "hard to build" asserted from nowhere caps it at 1, since builder-fit gets no search of its own.
- **Gates:** reality = 0 → LOW; two or more lenses returning `kills` → LOW; incumbent = 0 → MEDIUM at best; niche marked **unsettled** → MEDIUM at best. Count the `kills` rows yourself, and check the kills gate the way the rubric defines it: two *separate* facts, not one fact through two lenses, with at least one of them `strong`. Reality = 0 means one thing only: nobody pays in any form. A pitch nobody pays for anywhere cannot sit at 1 because the technology happens to work — and, the other way round, a real market whose capability isn't ready yet is a 1, not a 0, so it must not be gated to LOW. If a gate fired, the verdict must name it.
- **Every `kills` maps to that lens's documented kill condition** in Section 3, and every met condition is marked — not a generic objection marked `kills`, and not a met condition left at `neutral` because the prose already said it. Both directions are findings. Unfavourable facts that meet no kill condition belong in the prose of the check they bear on, not in the verdict column.
- The arithmetic sums to its stated Total, and the verdict line matches the table directly above it.

## 3. Re-verify the load-bearing facts

Search independently — don't re-read the cited source's summary. Check the number or date means what the evaluation claims, that the source is independent of the thing it's cited for, and that nothing more recent contradicts it.

Two directions matter here. A falsified finding invalidates whatever rested on it — say what collapses. And on the hostile searches, check the *opposite* way too: a competitor or a price the evaluation missed is the finding its owner most needs to hear.

## 4. Format and hard rules

Sections in order: `Source` / `Pitch as I read it` → Niche (category, substitutes, buyer, and how it compares to the pitch's own framing) → Lens scan (6 rows) → Checks (4) → Score (5 rows + total) → Verdict → What to test → First step. Full template regardless of conviction — a LOW verdict missing sections is a finding. No summary table — one pitch, one verdict.

In **What to test**, the numbers have to describe one experiment: the sample size in the experiment, in the success threshold and in the fail line is the same N, and the time-and-cost line has to fit that N. Three slots each asking for a number is how an unrunnable plan gets written without anyone noticing.

Then the hard rules: nothing fabricated (unknowns marked `DON'T KNOW`, not asserted), the verdict written after the score, and **never sugarcoat** — checked on both layers. Did the prose pull punches? And was the structure routed around — a kill condition described but not marked, a hostile search quietly softened, a gate that fired but didn't cap? Structural evasion is the more serious finding, because it survives a careful read.

## 5. Report

Most severe first: a falsified finding, a missing or faked hostile search, a band-changing score error, an ignored gate. For each — what's wrong, which line, and the concrete fix.

**Don't edit the evaluation.** This skill reports; applying fixes is a separate, deliberate step the user takes afterwards.
