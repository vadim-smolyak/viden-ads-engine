# The context file template

Fixed section order. Do not reorder, rename or add sections — downstream skills read this file positionally and a renamed heading is a missing heading.

Drop a section only if it is genuinely not applicable, and say so in one line under the heading rather than deleting it.

---

## Labelling convention

Every non-obvious claim carries one of two labels:

| Label | Means | Example |
|---|---|---|
| **Confirmed** | Stated explicitly by the user, or retrieved verbatim from a source you fetched | "Confirmed — no clinical claims permitted (client stated at intake)" |
| **Inferred** | A reasonable read from category, price point, imagery or language | "Inferred — likely restricted from before/after imagery given the category" |

If a claim is neither, it does not go in the file. Guessing inside a document that other skills treat as settled is the one failure mode this artefact has.

Unlabelled prose in the descriptive sections is fine where it is plainly summarising fetched copy. Every constraint, every audience claim and every differentiation claim gets a label.

---

## Template

```markdown
# Brand Context: [Brand Name]
*Generated: [YYYY-MM-DD] | Focus: [product line, or "Full brand"] | Source: brand-context v0.1.0*

---

## Brand Overview
[Two or three sentences: who they are, what they sell, where they sit in the market.]

---

## Brand Story & Origin
[Founder story, mission, origin, age of the business. Factual and short.]

---

## Product Catalogue

| Product | Key differentiator | Audience |
|---|---|---|
| ... | ... | ... |

Hero product: [name, or "not identifiable"]
Purchase model: [one-time / subscription / bundle-led / gifting-led]

---

## What Makes Them Different
[Unique mechanism, proprietary ingredient, format advantage or positioning edge. Quote their own language.]

> "[verbatim claim from their site]"

Support for the claim: [certification, study, patent, or "unsupported"]

---

## Competitor Landscape

| Competitor | Their positioning | How this brand differs |
|---|---|---|
| ... | ... | ... |

Direct vs indirect: [note which of the above are indirect — different product, same desire]

---

## The Alternative Solution
[What the customer was doing before this product. The old way. Often a behaviour or a service rather than a product.]

---

## Core Audience(s)
**Primary:** [description] — Confirmed / Inferred
**Secondary:** [description, or "none identified"] — Confirmed / Inferred

Signals: [pain points surfaced, lifestyle cues, language patterns, price point]
Disagreements: [where the client's stated audience and the site's signals diverge]

---

## Brand Voice & Tone
Adjectives: [three to five]
Patterns: [recurring vocabulary, sentence shapes, emotional register]
Avoids: [what is conspicuously absent]

Examples:
> "[short verbatim line]"
> "[short verbatim line]"

---

## Existing Creative
[What is currently running, at the level of themes and formats — not a teardown. Link ads with their foreplay_url. If not retrieved, say so.]

---

## Creative Constraints

| Constraint | Type | Notes |
|---|---|---|
| ... | Confirmed / Inferred | ... |

Special Ad Category exposure: [HOUSING / EMPLOYMENT / FINANCIAL_PRODUCTS_SERVICES / ISSUES_ELECTIONS_POLITICS / none apparent]
Needs a human read: [policy-sensitive claim shapes, EU targeting, AI-creative exposure — or "none identified"]

---

## Must-Know Strategic Context
- [Only things that change a creative decision.]

---

## Research Notes
Sources fetched: [URLs]
Not retrieved: [what you tried and could not get, and why]
Gaps and low-confidence areas: [flag clearly so the user can correct]
```

---

## Writing standards

- **Length.** Aim for something another skill can read in full. If a section runs long, the detail probably belongs in the conversation, not the artefact.
- **No invented numbers.** No market sizes, customer counts, growth figures or review totals that were not retrieved (`shared/canon.md` §8).
- **No platform rules.** This file records constraints; it never asserts what Meta policy says.
- **Verbatim means verbatim.** If you tidied a quote, it is a paraphrase and must lose the quotation marks.
- **Date the file.** The `Generated` date is how staleness gets detected.

## Updating an existing file

Edit in place. Update the changed sections, refresh the `Generated` date, and append one line to Research Notes recording what changed and why.

Rebuild from scratch only when the brand has repositioned — a reposition usually changes the ideal customer as well as the message `[T p.31]`, which invalidates the audience and constraint sections together, not just the positioning one.
