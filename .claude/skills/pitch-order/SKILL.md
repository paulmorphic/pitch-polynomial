---
name: pitch-order
description: Create a new pitch for the Pitch Polynomial framework. Asks about the pitch idea, risk appetite, and any extra constraints, then generates a file in orders/.
---

# New Pitch Polynomial order

Your job is to walk the user through creating a new pitch and save it to a file in `orders/`.

Don't read existing orders from `orders/` or runs from `runs/` — every new pitch is created from scratch, based only on the user's answers and the profile referenced below.

## Profile (fixed — don't ask about it)

Read `profile.md` from the repo root. If it doesn't exist yet, copy `profile.example.md` to `profile.md` and tell the user to fill in their real edges, horizon, and constraints. It holds the fixed parts of the pitch — the user's edges, horizon, and constraints — that don't change between runs. Use its contents to fill the corresponding sections of the order below.

## Process

### 1. Ask about the pitch

Ask the user (at most 3 questions at a time):

- **Pitch** — what's the product or business idea? Describe what you're building, for whom, and why you think it works. Be concrete — the more specific, the sharper the evaluation. It can be software, a physical product, or a service.
- **Risk appetite** — HIGH ("ahead of the wave") or LOW ("riding the wave")? Always ask; don't assume a default. The framework is binary here — there is no MEDIUM. It calibrates Amara timing and the proof bar — so the user must set it deliberately. (You may note that HIGH is a common choice, but wait for their answer.)
- **Extra constraints** — has anything changed since the last pitch? New context? A specific geography? Anything the framework should know that isn't in the profile?

### 2. Generate the file name

From the pitch, propose a short, keyword slug (e.g., `gpu-marketplace`, `healthcare-saas`, `devtool-security`). File name:
`orders/[slug].md`

If the file already exists, add a suffix `-02`, `-03`, etc.

### 3. Generate the order

Use the template below, filling it with the user's answers and the profile above:

```
# ORDER — apply the Pitch Polynomial framework to evaluate the pitch below

Pitch: [from the user's answer]

Edges:
[copy from the profile]

Horizon: [copy from the profile]

Risk appetite: [from the user's answer — required, no default]

Constraints:
[copy from the profile]
[Append any extra constraints from the user's answer, if provided]
```

### 4. Save the file

Save the generated order to `orders/[file-name].md`.

### 5. Point to the next step

Tell the user the order is ready. Ask whether to run the evaluation right away (i.e., run the analysis based on `pitch-polynomial.md` and save the result to `runs/[slug]-YYYY-MM-DD.md`).
