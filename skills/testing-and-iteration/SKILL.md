---
name: testing-and-iteration
description: This skill should be used when a VIDEN strategist is planning, logging, reading or iterating a creative test — "did this ad win", "what should we test next week", "write the hypothesis for this creative", "run the post-launch review", "build the creative roadmap", "should we iterate or go to new concepts", "is this creative fatigued", "is this result significant", "how many creatives should we be shipping". It enforces a written hypothesis per creative, reads live Meta performance and BigQuery business KPIs, runs the 4-question post-launch review, applies the iteration ladder, and separates message staleness from auction effects before anyone declares fatigue.
metadata:
  version: "0.1.0"
---

# Testing and iteration

One loop, run every week: **hypothesis → launch → review → iterate.** Forward-looking and backward-looking halves of the same system — the book splits them across Ch11–Ch15; here they are one skill because the output of the review *is* the input to the next hypothesis.

## Paths

| Path | When | Cost |
|---|---|---|
| **Fast — default** | "Did this win?", "what next?", one cohort of creatives | One reference + **at most two batched data calls** (one Meta insights call, one BigQuery call). |
| **Deep** | Significance dispute, a roadmap rebuild, a fatigue claim that will cost a shoot | Add `references/significance-math.md`; add a concurrent-control readout. |

Never run a web search at runtime. Never fabricate a number — see *Degrading gracefully*.

## References — load one, or none

| File | Load when | Lines |
|---|---|---|
| **nothing** | "Did this ad win?" on numbers you already have. The 4-question review, the two runtime windows and the ladder are all below; canon §7 supplies the lane rule | 0 |
| `references/hypothesis-templates.md` | Writing or auditing hypotheses. The book's 5 templates with fill-in slots and falsification conditions | 110 |
| `references/roadmap-schema.md` | Building, auditing or exporting the creative roadmap. Column definitions and the XLSX sheet spec | 83 |
| `references/significance-math.md` | Someone claims a winner, or asks for sample size or runtime. Formulas, the validity checklist, the worked example | 105 |
| `references/live-performance-reads.md` | A Meta Ads or BigQuery call is actually about to be made. The full call-hygiene contract | 26 |
| `references/cadence-and-fatigue.md` | "How many creatives should we ship?" or "is this fatigued?" The Motion volume benchmark, the staleness-vs-auction table, the two pre-fatigue requirements | 36 |

Load one. A weekly review needs `roadmap-schema.md`; it does not need the math.

## The ship gate — a written hypothesis per creative

**No creative ships without a written hypothesis** `[T p.95]`: a theory of why it will improve overall performance, written before launch, logged on the roadmap, and later marked winner or loser.

A hypothesis is valid only if it states all four:

| Slot | Test |
|---|---|
| **The observation** | What in the research or the last review prompted this? Name the source. |
| **The change** | Exactly one strategic variable — positioning, awareness stage, audience, constraint workaround, or media type. |
| **The predicted effect** | Which metric moves, in which direction, and in which lane (canon §7). |
| **The falsifier** | What result would make you say this idea is wrong. Without it, every outcome gets rationalised. |

"Testing a new hook" is not a hypothesis. Full templates and worked examples: `references/hypothesis-templates.md`.

## Cadence and fatigue — both corrected, both in one reference

**The volume target is replaced by a quality gate.** The book's 6–12 new creatives/week `[T p.95]` is superseded: cadence is whatever the team sustains **at quality**, gated on one written hypothesis per creative. Never set a weekly number as the target.

**Fatigue is two different things wearing one name** — *message staleness* (real) and *delivery / auction effects* (not fatigue). Never write "fatigue" without saying which you mean, and never declare it without a concurrent control.

The disclosed-sample benchmark to quote a client, the staleness-vs-auction comparison table with its checks and fixes, and the two hard requirements before anyone books a shoot are in `references/cadence-and-fatigue.md` (36 lines). **Load it when the question is volume or fatigue; a routine "did this win?" needs neither.**

**The runtime conflict, resolved explicitly:**

| Read | Window | What it licenses |
|---|---|---|
| **Directional creative read** | **7 days** | Iterate, kill, or re-hook. Runs on canon §7's fast lane. |
| **Statistical significance** | **14 days minimum** | Claiming a winner in a document, reallocating budget, telling a client a number. |

A 7-day read is a decision, not a finding. Never call a 7-day result significant, and never wait 14 days to make an iteration decision.

## The post-launch review — 4 questions `[T p.88]`

Run on **every** ad launched, winner or loser.

| # | Question | Discipline |
|---|---|---|
| 1 | **Did the ad improve business performance?** | Canon §7 governs the answer. State the lane; if attributed, state model and window. |
| 2 | **What went right?** | Even losers did something right. Name it or the finding is lost. |
| 3 | **What went wrong?** | Even winners did something wrong. |
| 4 | **What one thing carries into the next test?** | **One.** It becomes the observation slot of the next hypothesis. |

Answer 4 is the handoff. A review that produces three carry-forwards produces none.

## Iterating a winner

The ladder is canon §6 — **3 iterations → 3–6 variations → new concepts.** Do not restate it; apply it. Operational detail the canon doesn't carry:

**The six iteration variables** `[T p.85–86]`, each a single-variable change: **environment** (reshoot in 2–3 other locations that would resonate), **ethnicity**, **gender** (product dependent), **age**, **length** (test 3 other cuts), **removal** ("can anything be removed to make it better?"). One variable per iteration, or the read is worthless.

**The hard rule — go film new concepts.** Variations require new footage. Re-hooking the same asset is the failure mode: *"Do not just take the same video or photo and include a new hook in it… The same content over and over with just new hooks is a quick way to burn down an advertising campaign"* `[T p.86]`. When a request is "give me 10 new hooks for the winner", the correct answer is 10 hooks **plus a shot list**.

**The Flex Seal escalation** `[T p.87]`. Once messaging wins, broaden the demonstration, then push to *extreme* demonstration: leaking window seal → drill a hole in a boat, seal it, float it. Escalation exaggerates the mechanism's strength and buys another rung of the ladder without new messaging. Ask on every winner: what is the extreme version of this demonstration?

## The creative roadmap

The log of every creative test with its hypothesis and its outcome `[T p.89, p.95]` — the macro view of what is and isn't working in the account. Columns, definitions and fill rules: `references/roadmap-schema.md`.

Minimum viable columns: date launched, concept, angle, awareness stage, format, hook, hypothesis, spend, the fast-lane read, the attributed read with model + window, verdict (winner / loser / no read), the one carry-forward, ladder position.

**Offer an XLSX export when asked for one** — two sheets: a **matrix** (concept × angle × hook × format × awareness stage, for spotting the untested cells) and the **test log**. Build it with a short openpyxl script; spec in `references/roadmap-schema.md`. Do not offer it unprompted.

## Reading live performance

**Meta first, then BigQuery when the question is whether the problem is creative or commercial.** One well-formed query, never five exploratory ones; matched windows; every attributed figure carries its model and window (canon §7). The full call-hygiene contract — explicit `fields` and `level`, tight dates, row caps with a sort, uppercase filter operators, the 1–2 breakdown limit, the attribution default, lossless compaction, the >50-row rule, the BigQuery aggregate, and how to degrade gracefully — is `references/live-performance-reads.md`. **Load it only when you are actually about to make a call.** A question answered from pasted data or from the roadmap needs none of it.

## The three daily habits `[T p.90–91]`

Thirty minutes each. Offer them when a strategist asks how to get better, or when a review surfaces the same mistake twice.

| Habit | What it means |
|---|---|
| **Review your game footage** | Your most recent tests, like an athlete: what went right, what went wrong, what improves. This is the 4-question review as a daily habit, not a weekly ritual. |
| **Research with a specific objective** | Never open-ended. Broad first, then targeted at a named question — e.g. a newly discovered segment with a specific problem. Route to `market-research`. |
| **Practice one weak area per week** | Pick one skill — a hook-writing week, a visual-brief week. "Once you learn how, you don't have to keep relearning it" `[T p.91]`. |
