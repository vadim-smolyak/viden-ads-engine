# Post-click alignment — the page after the ad

Load this when auditing an ad against its destination, or when writing the page copy that has to catch the ad's traffic.

## The doctrine `[T p.93]`

"Landing page" covers product pages, home pages, collection pages, advertorials, listicles and sales pages. Two failures, both fatal:

1. **The page does not follow through on the thoughts the ad opened.**
2. **The page does not share the ad's theme.**

The standard, verbatim: *"Your prospect should never click on your ad and be like, 'What the hell did I end up at?'"*

**Never put a percentage next to message-match.** No study with a publisher, a date and a disclosed sample isolates the effect (`shared/evidence.md` → the never-state list). The honest framing: mismatch costs conversion rate, which raises CPA. There is also **no verifiable claim that Meta penalises landing-page experience in delivery or cost** — do not make one.

## The alignment audit

Run these five in order. Stop at the first failure and fix it before looking at the rest — a page that fails 1 or 2 makes 3 to 5 irrelevant.

**1. Continuity of thought.** Take the ad's hook. Does the page's first screen continue that sentence, or start a new one? The page's headline should read as the next line of the ad, not as an introduction to the brand. If the ad promised a mechanism, the mechanism is above the fold; if it promised an outcome, the outcome is above the fold.

**2. Theme.** Same subject, same register, same visual world. An ad that opened on a chaotic morning routine and a page that opens on a studio product shot share no theme, even if both are the same product.

**3. Offer identity.** The named offer in the ad is the named offer on the page, in the same words, at the same price. A "back-to-school special" in the ad and "20% off" on the page is a break in continuity even though the maths agrees.

**4. Specificity of destination.** If the ad qualified an audience or a variant, the page arrives already filtered to it. Sending a hyper-specific ad to a collection page hands the reader the filtering job they clicked to avoid.

**5. Detail placement.** The ad pushes the technical detail onto the page on purpose `[T p.92]` — over-educating in the ad turns people away. So the page must actually carry that detail. Check the ad's curiosity gap is closed on the page and not deferred again.

## Pre-flight gate: Core Web Vitals

**Do not creative-test against a page failing Core Web Vitals at mobile p75** — you are testing the page, not the hook. Load `shared/evidence.md` → Landing page for the sourced thresholds, the measurement percentile, and the pass-rate figure. Do not restate those numbers from memory; they change definition (FID became INP) and the evidence file carries the source and date.

If the page fails, say so, and say the creative read is unreliable until it is fixed. That is a more useful finding than a copy note.

## Landing-page structure

The shape a page needs to catch paid traffic.

**Above the fold**

| Element | Job |
|---|---|
| Headline | The single most important message. Continues the ad's thought. Specific over generic. |
| Subheadline | Expands the headline, adds the specificity the headline had no room for. One or two sentences. |
| Primary CTA | Names what they get, not the transaction. Same CTA doctrine as the ad (`references/copy-checks.md`). |

**Core sections**, in this order unless research says otherwise:

| Section | Purpose |
|---|---|
| Social proof | Credibility early, before the argument starts. Logos, counts, review quotes. |
| Problem / pain | Show you understand the situation. State it once and move — do not wallow `[T p.67]`. |
| Solution / benefits | Connect to outcomes. Three to five, all serving the one desire the ad named. |
| How it works | Reduce perceived complexity. Three or four steps. This is where the mechanism lives. |
| Objection handling | FAQ, comparison, guarantee. Reach for `belief-objection-engineering` for what to answer. |
| Final CTA | Recap the value, repeat the CTA, add the risk reversal. |

**Page type changes the job:**
- **Landing page** — one message, one CTA, complete argument on the page. This is the default destination for paid traffic.
- **Product page** — the ad's angle has to survive the template. Check the first variant selected matches the ad.
- **Advertorial / listicle** — the ad's theme carries through as editorial voice; the break in register at the CTA is the usual leak.
- **Collection page** — only acceptable when the ad was deliberately category-level. Otherwise a specificity failure.
- **Home page** — almost never right for paid traffic. Flag it.

## Headline formulas

Starting shapes for the page headline, to be earned rather than filled in blindly:

- "{Achieve outcome} without {pain point}"
- "The {category} for {audience}"
- "Never {unpleasant event} again"
- "{Question naming the main pain point}"

Two constraints on all four:
- The audience or the outcome must be the **specific one the ad named**, not the general one the brand serves.
- Specificity raises the quality of the audience that stays, the same way it raises the quality of the audience that stops `[T p.41]`.

## Writing-style rules for page copy

1. **Simple over complex** — "use" not "utilize".
2. **Specific over vague** — no "streamline", "optimize", "innovative".
3. **Active over passive** — "we generate reports", not "reports are generated".
4. **Confident over qualified** — cut "almost", "very", "really".
5. **Show over tell** — describe the outcome rather than reaching for an adverb.
6. **Honest over sensational** — never fabricate a statistic or a testimonial (canon §8).
7. **One idea per section** — each section advances one argument; the page is a sequence, not a pile.

## Output format for an alignment audit

```
ALIGNMENT: Aligned  /  Breaks (N)

BREAK 1
  Where:     ad hook -> page headline
  Ad said:   "the exact ad line"
  Page says: "the exact page line"
  Problem:   which of the five audit points fails, in one sentence
  Fix:       the corrected page line, ready to paste

CWV GATE: pass / fail / not checked (say which, and if failed, that the creative read is unreliable)
```

Report the gate every time, even when it is "not checked" — an unstated gate reads as a passed one.
