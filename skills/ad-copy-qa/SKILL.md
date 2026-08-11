---
name: ad-copy-qa
description: >
  This skill should be used when a VIDEN strategist or copywriter needs the copy around the creative
  written or checked — primary text, headline, link description — or needs the page a click lands on
  checked against the ad that sent it. Trigger on "QA this ad copy", "check this copy before I submit
  it", "review this primary text and headline", "review this primary text", "check this headline", "is
  this copy ready to launch", "run the copy QA", "write primary text for this concept", "write the
  headline and link description", "rewrite this CTA", "is this within Meta's character limits", "does
  the landing page match the ad", "check the post-click", "will this get flagged". Copy only: it does
  not review images, video, or the script itself.
metadata:
  version: 0.1.0
---

# Ad copy QA

Own the copy **around** the creative and the page **after** the click. Two directions: write it, or QA a draft. Copy only — asset-level review (visuals, pacing, captions, pop) belongs to `prelaunch-qa`; the spoken/on-screen script belongs to `video-script-system`.

Never run a web search. Everything needed is in this skill's `references/`, `shared/canon.md` and the brand artefact. **`shared/evidence.md` is rare-path only** — the policy URLs and the high-risk shapes live in `references/copy-policy-risk.md`, so nothing routine goes to evidence.md; open it only for the Special Ad Categories constraint list or to justify a 2026 call.

## Before judging anything

1. **Load the cached brand-context artefact** for this brand (`brand-context` builds and stores it). Voice, register, banned words, product facts, pricing, warranty, sourcing claims and the VOC quote bank all come from there. Never from memory. If no artefact exists, say so and run `brand-context` first — without brand facts this pass can only catch grammar and structure, so label the verdict accordingly.
2. **Get three things about the ad**, in one grouped question if any is missing:
   - the asset the copy sits on (what is shown, which product, variant, colour);
   - awareness stage and traffic temperature (cold / retargeting) — stages per canon §2;
   - platform and placement.
3. Copy is judged **against the actual asset**. Copy that could describe any product, any size, or any variant fails on that ground alone.

## Fast path (default)

Run the seven **priority checks** only, return the verdict, stop. That is the whole job for "check this before I submit it." Load `references/copy-checks.md` — 65 lines, the priority checks and nothing else — and load nothing else.

## Deep path (say you are doing it)

Priority + standard checks, plus platform-limit truncation, policy-risk flagging, and post-click alignment. Add the shards you actually need, one at a time. Use it before a launch, on a full batch, or on anything in a restricted category.

## Reference index — load one shard, not the set

| Load | For | Lines |
|---|---|---|
| `references/copy-checks.md` | **Fast path.** Priority checks 1–7 in full — grammar tells, the empty-claim test, substantiation, asset match, the hook gate, clever-vs-simple, voice | 65 |
| `references/copy-checks-standard.md` | Deep path. Standard checks 8–14, the CTA doctrine with its Don't → Do pairs `[T p.76]`, and the 15-line pre-Pass gate | 71 |
| `references/copy-policy-risk.md` | A health, financial, body, income or identity shape is present. The four policy URLs, the five known high-risk shapes, and what a Special Ad Category changes | 32 |
| `references/copy-worked-examples.md` | You want the before/after pattern for a check, or you are teaching the standard | 47 |
| `references/platform-limits.md` | Character limits per surface per platform, what is actually sourced and what is not, truncation behaviour | 96 |
| `references/post-click-alignment.md` | Ad → page follow-through, landing-page structure, headline formulas, the CWV pre-flight gate | 104 |

Sibling skills: `hook-system` (hook craft and the tactic/trigger libraries), `belief-objection-engineering` (objection copy), `brand-context` (the artefact), `creative-brief-builder` (turning the output into a doc), `prelaunch-qa` (asset review), `campaign-troubleshooting` (when live copy underperforms).

## The verdict format

```
VERDICT: Pass  /  Needs changes (N issues)

ISSUE 1
  Element:   primary text / headline / link description / CTA / landing page
  Line:      "the exact line, quoted"
  Problem:   one sentence
  Rule:      the rule it breaks, named
  Rewrite:   the corrected line, ready to paste

ISSUE 2
  ...

KEEP: the one or two strongest lines in the draft
```

Rules for the verdict:
- **A draft passes only when every check in scope passes.** One hollow superlative, one invented number, one line that contradicts the asset, and the verdict is Needs changes.
- **Always quote the exact line.** Never say "the primary text is weak."
- **Always name the rule**, so the writer learns the standard rather than the correction.
- **Always give a usable rewrite**, not a direction to rewrite.
- **Always end with KEEP.** Naming the strongest line reinforces the instinct that produced it.
- Policy items are flagged as **RISK**, never as an issue with a verdict attached. See below.

## The checks

Priority detail in `references/copy-checks.md`, standard detail in `references/copy-checks-standard.md`. Priority checks are where VIDEN copy actually fails; never skip them.

**Priority**
1. **Grammar and naturalness** — read every line aloud; flag anything no native speaker would say, and show the corrected line.
2. **Empty claims and hollow superlatives** — if you cannot point at the feature behind the line, it fails.
3. **Claim substantiation** — no invented statistics, ever (canon §8 owns the rule; this check enforces it). Any number must trace to the brand artefact or a client-supplied figure. Cut it or replace it with a real one; never soften it.
4. **Match the asset** — product, variant, colour, size, claim and scene all agree with what is shown.
5. **Hook present and passing** — the first line clears all three golden rules (canon §1). A hook that fails the gate is a rewrite, not a note.
6. **Simple, not clever** — clever copy makes the reader solve a puzzle `[T p.72]`; canon §8 owns the standard.
7. **Voice and register consistency** — against the brand artefact, including banned words, punctuation habits and the exclamation rule.

**Standard**
8. **One idea** — one desire or problem, one avatar (canon §8). An ad that says three things says none.
9. **Use case present** — a real named moment, not a product description.
10. **CTA earns the click** — see the CTA rule below.
11. **Surface fit** — every surface within limits, hook front-loaded ahead of the truncation point (`references/platform-limits.md`).
12. **No repetition across the batch** — three ads reusing a phrase is one ad.
13. **Proof is real** — quotes verbatim from the artefact's VOC bank, never fabricated, never tidied up.
14. **Scarcity and urgency are true** — stated once, calm, and actually the case. Desire has a clock (canon §8), so check the calendar before writing urgency into copy.

## The CTA rule `[T p.76]`

An effective CTA **reminds people why to click, or gives them a reason to act now.** A verb plus a transaction is not a CTA. Full Don't → Do pairs in `references/copy-checks-standard.md`; the shape is "Click below to *get the thing you came for*", not "Click to buy now."

## Policy risk — flag and point, never assert

The Meta policy rule text was never retrievable during research (`shared/evidence.md` → Policy). So:

- **Name the specific risk** in plain language.
- **Give the specific policy URL** from `references/copy-policy-risk.md` — that shard carries all four URLs, so no policy question needs `shared/evidence.md`.
- **Say it needs a human read** before launch.
- **Never assert a rule.** Never quote policy text from memory.
- **Never clear copy as compliant.** This skill cannot issue a compliance pass, and must say so when asked.

Known high-risk shapes are **pattern recognition, not policy citation** — label them that way every time you use them: implying knowledge of the reader's health condition or financial situation; before/after body imagery; income claims; "you" framings that presume a diagnosis. Full list with the URLs in `references/copy-policy-risk.md`.

## Writing mode

Same checks, run before delivery instead of after.

- **Write the hook first**, then the surfaces around it. Text creates the visual (canon §4), and the primary text's first line is usually the hook doing double duty.
- **Write to the surface, not to the word count.** Front-load; assume truncation.
- **Draft three, keep one per surface.** Deliver the keeper plus one alternate, not a wall of options.
- **Match the script.** If a video script exists, the primary text continues its thought rather than restating it `[T p.51]`.
- Deliver as markdown in chat by default. Route to `creative-brief-builder` only when the copy needs to leave the chat as a document.
