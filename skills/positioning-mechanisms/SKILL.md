---
name: positioning-mechanisms
description: This skill should be used when a VIDEN strategist needs to decide what a product stands for before any hook gets written — choosing the mechanism, deciding whether to prove superiority, sell an identity or introduce a new mechanism, building the persona × pain matrix, writing messaging angles, or repositioning a stalled account. Trigger on "how should we position this", "what's our mechanism", "we need a new angle for [brand]", "build the messaging angles", "map the pain × persona matrix", "who are the indirect competitors", "what do people hate about the alternatives", "this account is stuck — is it positioning", "can we reposition this product", "name the mechanism", "what's the buying motivation here", or "this is a Special Ad Category campaign".
metadata:
  version: "0.1.0"
---

# Positioning & Mechanisms

Positioning decides what the ad is allowed to say. It runs before hooks, because "this will dictate the next part of our process: hook creation" `[T p.30]`. Two gates from `shared/canon.md` §1 apply before anything here ships: the desire must be proven and large, and the audience must be unambiguous.

## Fast path vs deep path — default to fast

| Path | Trigger | Do this | Output |
|---|---|---|---|
| **Fast** — one pass | "what's our mechanism?", "give me an angle for X", "is this a superiority play or an identity play?" | Pick the play from the table below, name the mechanism, write one to three messaging angles. Use whatever context the user supplied | Named play + mechanism + angles, markdown in chat |
| **Deep** — full treatment | New client, a reposition, a stalled account, or a full-workflow start | Anchor → matrix → mechanism → play → angles across every intersection → depositioning check | Angle matrix + mechanism statement + per-angle context blocks |

If brand context is missing on a fast-path ask, use what the user gave and note the gap in one line. Do not run `brand-context` first.

## Reference index — load on demand only

| Load | When |
|---|---|
| `references/buying-motivations.md` | Choosing a Motivation angle, or an angle feels generic and needs a named driver. Holds the 20 buying motivations, the three angle types, micropersona refinement |
| `references/repositioning-cases.md` | Repositioning, depositioning, or naming a new mechanism. Worked cases with the move and what to copy |
| `shared/canon.md` §2 | Deciding which awareness stage an angle targets, and therefore its script flow. Never restate that table |
| `market-research/references/question-batteries.md` L2–L3 | The competitor sets feeding the hate-list method below are missing |

## Step 1 — Anchor: pain-first or desire-first

The anchor is the organising axis for everything downstream. Pick one as *primary*; the other stays available as an expression.

| Anchor | Use for | Looks like | Signal you picked right |
|---|---|---|---|
| **Pain-first** (default) | Functional products solving a specific, nameable problem | Cystic acne, bulky wallet, weak WiFi, poor sleep, snoring, grout stains | People search the problem, not the category |
| **Desire-first** (exception) | Aspirational, status, aesthetic or identity products with no acute functional problem | Quiet luxury, collector credibility, barista coffee at home, timeless elegance | There is no before-state to photograph |

Demographics alone are never an anchor. "Are you a busy mom? Buy this water bottle" carries no value; "a water bottle that doesn't leak all over your car while you run errands with the kids" does. The demographic qualifies; the pain persuades.

## Step 2 — The persona × pain matrix

Personas are always secondary. A persona is a **life context in which the same pain is experienced differently**. Build the grid — pains down the rows, personas across the columns. Every filled cell is one messaging angle.

|  | Busy professional | Stay-at-home parent | Bride-to-be |
|---|---|---|---|
| Cystic acne | angle | angle | angle |
| Folliculitis | angle | angle | — |

Many-to-many: one pain reaches several personas, one persona carries several pains. Three to five personas per pain bucket is the working range. Define each by demographics, daily context, and above all **how this persona experiences this specific pain differently from the others** — that difference *is* the angle.

Coverage is not the goal. An unproven or small desire fails at any level of coverage `[T p.65]`, and one desire plus one avatar per ad is non-negotiable (`shared/canon.md` §8).

## Step 3 — Name the mechanism

**A mechanism is a vehicle** — the thing that carries the customer from where they are to where they want to be `[T p.26]`. Coast to coast:

| Vehicle | Price | Time | Cost of choosing it |
|---|---|---|---|
| Bike | Cheapest | 70 days | Most dangerous |
| Car | Middle | 45 hours | Boring |
| Plane | Most expensive | 6 hours | Safest, but anxiety-inducing |

**Which mechanism to position on depends entirely on what this customer cares about** `[T p.27]`. A fear of flying keeps someone driving even at a 45-hour time cost. Cheapest and fastest are not answers; they are candidates.

Write the mechanism as one sentence: *this product gets [persona] from [current state] to [desired state] by [vehicle]*. Negative beliefs attached to a mechanism cap results severely `[T p.27]` — if one surfaces, route it to `belief-objection-engineering` before writing copy.

## Step 4 — Choose the positioning play

Three plays, and only three `[T p.30]`. Choose by what is actually true about the product.

| Play | Use when | What makes it work | Evidence needed |
|---|---|---|---|
| **Prove superiority** | The product genuinely is superior — desire-focused, cheaper, more benefits, or solves more of the problem `[T p.8]` | Benefits mapped onto what people hate about the alternatives — that mapping *is* the perception of superiority `[T p.11]` | The hate list (below). Every iPhone launch is this play, on only three axes: screen size, battery life, camera quality `[T p.28]` |
| **Sell to a new identity** | The product is *not* superior | Niching down inside the market until a sub-community's shared interest creates new demand `[T p.9–10]` | A real community with real language. Black Rifle Coffee and Gymshark are the canonical cases |
| **Introduce a new mechanism** | The market has tried everything in the category and lost hope | A named vehicle nobody else is offering. Includes the highest-leverage move in the doctrine — see below | Testing. The market must *accept* the product as a viable solution for that desire `[T p.30]` |

**The move worth remembering:** a new mechanism can simply be **an existing product aimed at a desire nobody has aimed it at before** `[T p.29–30]`. No product change required. Naming that vehicle is part of the play — an unnamed method is a claim, a named method is a thing `[T p.29]`. Both cases are in `references/repositioning-cases.md`.

**When the product is not better and identity is not available:** examine the character-trait niches inside the market and position to one, showing the product doing what that person loves. iPhone's niches: gamers, vloggers, business owners, influencers, athletes `[T p.28]`.

## The hate-list method — direct and indirect competitors

**Direct competitor** = same product. **Indirect competitor** = a different product satisfying the same desire `[T p.10]`. A superior product beats indirect competitors too `[T p.11]`.

1. List every existing solution, direct and indirect.
2. For **each** solution separately, enumerate what people hate about it.
3. Map the product's benefits onto those hatreds.

Different solutions produce different hatreds, so different benefit claims and different personas — which is why step 2 is per-solution and not once for the market. Worked example in `references/repositioning-cases.md`.

Source the hate list from research, never from imagination. `market-research` Levels 2 and 3 exist to produce it.

## What they have tried before

Ask the count, then the reason: **how many solutions have they already tried, and why did each fail?** This "drastically changes what we must say in an ad" `[T p.25]`, and it selects the awareness stage and therefore the script flow (`shared/canon.md` §2).

A failed desire is not a dead desire. The desire persists; hope has gone, and hope is what the ad re-instils `[T p.25]`. You cannot create desire — only call it out and channel it (`shared/canon.md` §8).

## The messaging angle

An angle is the **core truth at one pain × persona intersection** — conversational human language, not a tagline. "Your dermatologist wrecked your skin", not "professional-grade natural healing without prescription side effects". Document each one in this shape:

```
PAIN / DESIRE:  [the bucket]
PERSONA:        [name and one-line life context]
MECHANISM:      [the vehicle sentence]
PLAY:           [superiority | identity | new mechanism]
ANGLE:          "[core truth, in their words]"

Use case:       [how THIS person experiences THIS pain]
Deepest desire: [the visceral outcome, past the surface want]
Priorities:     [which features matter to them, and the benefit each becomes]
Objections:     [what THEY specifically will doubt]
Tried before:   [count + why each failed]
Motivation:     [1–2 from references/buying-motivations.md]
```

Feature → benefit → desire, in that order, and only keep the features serving the one desire `[T p.71]`.

## Depositioning and repositioning

| Move | Trigger | The action |
|---|---|---|
| **Deposition** | Your mechanism is at the end of its trend, or the market has commoditised what you were known for | Deliberately shed the image you built and capture a new market with a new mechanism `[T p.31]` |
| **Reposition** | The positioning lacks urgency, or performance stalled with creative that is technically fine | Re-aim the same product at a different desire. Expect the ideal customer to change with it, and rebuild the matrix rather than reusing it `[T p.31]` |

Test the positioning for urgency before touching production — "this will make your wall look great" is a true statement that nothing has to happen about this week. Cases and what to copy: `references/repositioning-cases.md`. If the diagnosis is not yet confirmed as positioning, `campaign-troubleshooting` owns the decision tree.

## Special Ad Categories — the creative does the targeting

Applies to `HOUSING`, `EMPLOYMENT`, `FINANCIAL_PRODUCTS_SERVICES`, `ISSUES_ELECTIONS_POLITICS` (Marketing API v26.0, updated 21 May 2026).

In these categories there are **no lookalike audiences and no demographic targeting** — age locked to 18–65+, no gender targeting, 15mi/25km minimum radius, no ZIP-level or exclusion targeting.

**The consequence: the creative is the only targeting instrument left, so the first line must qualify the audience explicitly.** The hook is doing the job an audience setting used to do. What that changes here:

- Write the audience qualifier *into* the angle, not just the hook. Every angle in the matrix must name who it is for, and the matrix column heading has to survive into the first sentence.
- Broad-appeal angles are a liability, not an efficiency. Precision in the copy replaces precision in the audience.
- Financial, insurance and credit products all sit inside `FINANCIAL_PRODUCTS_SERVICES` — a boundary that broadened in 2024 and is easy to miss.

Policy risk here needs a human read, not a ruling from this plugin. Name the risk, point at the policy URL, escalate — see `shared/evidence.md`.

## Handoff

Markdown in chat by default. For client-facing output or a full-workflow run, hand the angle matrix and mechanism statements to `creative-brief-builder`.

Onward: angles → `hook-system` for opening lines, `creative-concepting` for visuals and concepts. Missing pain or persona evidence → back to `market-research`. Negative beliefs about the mechanism → `belief-objection-engineering`.
