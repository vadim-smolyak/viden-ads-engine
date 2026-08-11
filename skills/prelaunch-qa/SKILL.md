---
name: prelaunch-qa
description: This skill should be used when a VIDEN strategist wants a finished creative checked against the pre-launch bar before it goes live — "review this creative before launch", "check this creative before I launch it", "QA this ad", "QA this asset", "is this creative ready to ship", "run pre-launch on this concept", "check these before Monday's upload", "does this creative pass". It judges the finished asset; a primary-text or headline review with no asset attached belongs to `ad-copy-qa`. It runs the book's 10-item pre-launch checklist on the asset as built (hook, visuals, pacing, belief, boredom), substantiates every claim in the shipped copy, flags policy risk for a human read, and returns a Pass / Needs-changes verdict naming the exact element, the rule it breaks, and a suggested fix.
metadata:
  version: "0.1.0"
---

# Pre-launch QA

The last gate before upload. Judge the creative **as built** `[T p.77–78]` — the asset, its pacing, and the copy shipping with it. The job is to raise the floor of every ad so the Growth Operator's review is about strategy, not defects.

Built from four years of reviewing 100+ creatives a week `[T p.77]`. Run it on every asset, winner-lookalike or not.

## Scope

| In | Out — hand off |
|---|---|
| Hook against the gate, visual choices, pacing, belief, boredom, inspo match | Brand voice, register, banned words, line-by-line copy rewriting → `ad-copy-qa` |
| Claims and policy risk **on the asset** — on-screen text, superimposed numbers, imagery, category, AI visibility | A copy-only pass on primary text and headlines → `ad-copy-qa`, which owns the 14 copy checks |
| The verdict: ship or don't | Hook rewrites → `hook-system`; script surgery → `video-script-system`; positioning mismatch → `positioning-mechanisms` |

If `ad-copy-qa` has already passed this ad's copy, items 11 and 12 become a confirmation rather than a re-run — say so in the verdict and spend the time on the asset.

A strategy problem gets one flagged line, then move on. The verdict is about whether this specific creative is fit to launch.

## Paths

| Path | When | Load |
|---|---|---|
| **Fast — default** | One asset, one verdict | **Nothing.** The 12-item table below carries the fail signal *and* the fix shape for every item, which is the whole verdict. No data calls. |
| **Deep** | An item is contested, an ad is failing an item you cannot articulate, a batch fails the same item repeatedly, or you are teaching the standard | Add `references/checklist.md` |
| **Policy** | Health, finance, body, income, or identity claims present | Add `references/policy-risk-shapes.md` |

Never run a web search at runtime. Never pull performance data here — this skill judges an unlaunched asset. Post-launch reads belong to `testing-and-iteration`.

## References — load on demand only

| File | Load when | Lines |
|---|---|---|
| `references/checklist.md` | An item is contested or needs teaching. All 12 items in full: what each tests, what good looks like, the fail signal, the fix shape, the 2026 notes, and the pre-Pass final gate | 178 |
| `references/policy-risk-shapes.md` | Any high-risk shape is present. Known high-risk copy and imagery shapes, the policy URLs to point at, the escalation wording, the AI-escalation rule, and what can and cannot be asserted about specs | 85 |

**A routine Pass/Needs-changes verdict loads neither.** The table below is the fast path in full.

## Intake — ask before judging

Ask these as one grouped question. Judging an asset without them produces generic notes.

1. **The asset** — video or photo, and the cut that will actually run.
2. **The shipped copy** — primary text, headline, link description.
3. **Target audience and awareness stage** — the checklist tests fit against a named audience, not a general one.
4. **The written hypothesis** — from `testing-and-iteration`. No hypothesis is itself a fail.
5. **The inspo** — the reference the concept was built from, for item 8.

## The 12 items

Items 1–10 are the book's `[T p.77–78]`, in the book's order. Items 11–12 close 2026 gaps the book predates. **This table is the fast path: fail signal and fix shape for all twelve, so a routine verdict loads no reference.** What each item tests, what good looks like, how to run it honestly, and the 2026 notes are in `references/checklist.md`.

| # | Item | Fails when | Fix shape — what the verdict says |
|---|---|---|---|
| 1 | **Strong hook** — all three sub-checks | Any of canon §1's three golden rules misses. Cite which one. | Name the failing rule and hand to `hook-system`. Never rewrite strategy inside a QA verdict. Precondition checked first: is the desire proven and large, and the audience unambiguous `[T p.65]` |
| 2 | **Visuals speak to the target audience** | A visual serves the brand, the aesthetic, or the editor — not what this audience wants. | Name the offending scene plus the audience want it fails to serve; suggest the substitute environment or subject |
| 3 | **The visuals pop** | Flat, low-contrast, low-saturation, expected angles. "Visuals that do not pop, do not perform" `[T p.77]`. | Name the frame and the lever — contrast, saturation, or an unusual angle/thing/place |
| 4 | **Eyes flow easily** | Video: captions repeat across scenes or sit where the eye isn't. Photo: hook hard to find, focus undirected. | Per-scene caption rewrite, or a placement note per shot |
| 5 | **New visuals every ~3 seconds** — *craft heuristic, see below* | A scene holds long enough to feel static with nothing new entering frame. | Timestamp the sag and name what to introduce there. **CRAFT NOTES, never ISSUES** |
| 6 | **Visuals provide belief** | The thing that has to be believed is only said, never shown. Canon §4's belief rule. | Name the load-bearing claim and the shot that would prove it. If it cannot be shown, that is a media-type hypothesis for `testing-and-iteration`, not a QA fix |
| 7 | **Not boring** | You would scroll past it. Be brutally honest `[T p.77]` — this item fails more ads than any other. | Name the dead stretch and what it lacks — tension, stakes, surprise, a reason to stay. Usually a concept problem: route to `creative-concepting` |
| 8 | **Matches the inspo's intent** | Compared side by side, something structural from the reference is missing. Copying execution instead of the mechanism also fails. | Name the missing **structural** element, not the missing aesthetic |
| 9 | **Friend reaction captured** | Nobody outside the build has seen it, or the reviewer was briefed first. | Ask one question only: "what did you think that was about?" Confusion in the answer is the finding |
| 10 | **72-hour re-review** | Reviewed only on build day. Three days away, or a second reviewer, substitutes. | Schedule it or name the second reviewer. If neither fits the upload window, state it as a risk in the verdict |
| 11 | **Claims substantiated** | Any statistic, percentage, ranking, superlative or "studies show" without a client-supplied source. Plausibility is not sourcing. | Cut the number, or replace it with a demonstration that shows the same thing |
| 12 | **Policy risk flagged** | A known high-risk shape is present with no flag — or worse, a compliance opinion was stated. | The three-step flag below. That is the whole deliverable |

## The two corrections to the book's checklist

**Item 5 is craft, not mechanism.** Cutting every ~3 seconds is good filmmaking and worth holding as a pacing standard. It is **not** a claim about how attention works, and must never be written up as one. The evidenced attention window is shorter and messier than the book's framing (`shared/evidence.md`), and:

> **Attention is re-winnable.** Kantar (29 Jul 2024, 40 ads, ARF Attention Validation Initiative) found a **product introduction at second 7 created new attention.**

So a weak second half is **fixable, not fatal**. When a video sags after the hook, the fix is to introduce something new mid-roll — the product, a demonstration, a turn — not to bin the asset. Never fail an ad on pacing alone; write it up as a craft note with the specific timestamp and what to put there.

**Claim substantiation is a hard fail (item 11).** No invented statistics in shipped copy, ever — canon §8. The book itself models this badly at `[T p.86]`; do not follow it there. Check the places a copy pass cannot see: numbers burned into the asset, on-screen superlatives, chart or results overlays, implied results in a before/after frame. If a number can't be traced to something the client supplied, the fix is to cut it or replace it with a demonstration. "Sounds like the kind of number that's true" is not a source.

## Policy-risk flagging — what to do and what never to do

When a high-risk shape appears (see `references/policy-risk-shapes.md`):

1. **Name the specific risk** in the copy or imagery — quote the line or describe the frame.
2. **Point at the specific policy URL** from `references/policy-risk-shapes.md`.
3. **Say it needs a human read** before this ad ships.

Never assert what a Meta policy says. Never clear copy as compliant. The rule text for the relevant policies was never retrievable during research (`shared/evidence.md`) and is not written from memory anywhere in this plugin. Flagging a risk honestly is the deliverable; a compliance opinion is not available.

## Output — the verdict

```
VERDICT: Pass  /  Needs changes (N issues)

ISSUE 1
  Element:   hook / visual (00:0X) / caption / primary text / headline / pacing
  Exact:     "the line" or the frame described
  Problem:   one sentence
  Rule:      checklist item N, or the canon rule it breaks
  Fix:       the corrected line, or the specific shot to reshoot

ISSUE 2
  ...

POLICY FLAG (only if present)
  Risk:      the specific shape
  Policy:    the URL
  Action:    needs a human read before launch

CRAFT NOTES (non-blocking)
  - pacing, timestamps, item 5

KEEP: the one or two strongest elements in the creative
```

Pass only when every item 1–4 and 6–12 passes. One unsubstantiated statistic, one belief carried by narration instead of demonstration, one hook missing a golden rule, and the verdict is Needs changes. Item 5 alone never blocks a launch.

End every verdict with **KEEP**. Reinforcing the instinct that produced the good element is how the next batch gets better.

## Final gate

Run every row of the 12-item table above as a checkbox, in order, before writing `VERDICT`. The same gate written out as a tick-list — the exact wording to run against — is the closing section of `references/checklist.md`.
