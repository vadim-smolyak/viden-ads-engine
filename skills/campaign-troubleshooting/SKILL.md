---
name: campaign-troubleshooting
description: This skill should be used when a VIDEN strategist needs to diagnose an underperforming Meta campaign or account — "why is this campaign dying", "CPA is up and I don't know why", "the winner stopped working", "diagnose this account", "revenue fell off a cliff this week", "is this a creative problem or a landing page problem", "spend won't scale past X". It runs the book's 6-cause diagnostic tree as a symptom lookup, checks causes in cost order so free explanations get ruled out before expensive ones, splits commercial from creative causes using Meta and BigQuery data, and audits the landing page against a scored rubric with a Core Web Vitals gate.
metadata:
  version: "0.1.0"
---

# Campaign troubleshooting

Diagnose an underperforming campaign without reaching for the reshoot first.

## The ordering rule — check in cost order

The book implies this and never states it. State it, and follow it every time:

| Order | Layer | Cost to check | Cost to fix |
|---|---|---|---|
| 1 | **Fulfilment and the calendar** | Free | Often free — it's an operations answer |
| 2 | **Landing page** | Cheap — one page load and a CWV read | Cheap to moderate |
| 3 | **Messaging and positioning** | Moderate — read the last 8 weeks of hooks | Expensive |
| 4 | **Creative execution** | Expensive — a shoot | Most expensive |

**Most "creative problems" are not creative problems.** Never open a diagnosis at layer 4. If the fulfilment window closed, the page fails Core Web Vitals, or the last eight weeks of hooks say the same thing, a new shoot cannot fix it and will hide the real cause for another two weeks.

## Paths

| Path | When | Cost |
|---|---|---|
| **Fast — default** | A named symptom, one account | The symptom table + the six-causes table below, **zero references**, and **at most two batched data calls**. |
| **Deep** | Two candidate causes survive the fast path, or the fix is a shoot or a page rebuild | Add the second reference; add a control readout. |

Never run a web search at runtime.

## References — load one, or none

| File | Load when | Lines |
|---|---|---|
| **nothing** | The symptom row below names one cause and the fix is at layer 1 or 2 — operations, the calendar, or the CWV gate. That is a complete diagnosis | 0 |
| `references/diagnostic-tree.md` | Causes 1, 2, 3, 4 or 6 are live and the fix needs the check. All six in full, with the book's cases | 118 |
| `references/page-audit-rubric.md` | Cause 5 is live **and** the page passed the gate, so it needs scoring. The 9-category 100-point rubric, the conversion-killer taxonomy, above-the-fold and mobile checklists | 144 |
| `testing-and-iteration/references/live-performance-reads.md` | A Meta or BigQuery call is about to be made | 26 |

Load **one**. A diagnosis that loads both trees has not narrowed anything. On cause 5, this skill scores the page and runs the gate; auditing ad→page continuity and writing the corrected lines belongs to `ad-copy-qa` — name the break, hand over the rewrite.

## Intake — one grouped question

The account or campaign · the symptom in the strategist's own words · when it started (a date, not "recently") · what changed around then (creative, budget, offer, page, audience, price, stock) · the landing page URL · the category's seasonal shape.

"When did it start" plus "what changed then" resolves more diagnoses than any data pull.

## Symptom → cause lookup

Check the **Check first** column before anything else in the row, then take the check and the fix from the six-causes table below. Neither table needs a reference load; `references/diagnostic-tree.md` is for an ambiguous symptom or a case you need to cite.

| Symptom | Check first (cost order) | Likely cause | Fix / route |
|---|---|---|---|
| Revenue collapsed within days, no creative change | Shipping cutoff, stock, promo end date, holiday | **3 — Seasonality / desire has a clock** | Operations, not creative. See the Valentine's case. |
| Category revenue drifting down over weeks, ads unchanged | Season shape vs last year | **3 — Seasonality** | Re-position to the current state, don't reshoot the old one |
| Winner decayed slowly over weeks or months | Last 8 weeks of hooks and angles side by side | **4 — Repeating the same strategy** | New concepts, canon §6. The 90% cause `[T p.93]` |
| Winner died overnight, delivery normal | Page, offer, stock, price change on the same date | **5 — Landing page** or an offer change | `references/page-audit-rubric.md` |
| CTR healthy, CPA up, checkout initiations flat | CWV at mobile p75, then message match | **5 — Landing page** | Page fix. Don't re-hook a page problem |
| CTR healthy, add-to-cart healthy, purchases down | Price, shipping cost, stock, payment methods | Commercial, not creative | Run the commercial-vs-creative split below |
| Hook rate fine, hold rate collapses, no conversions | The script's second half | **2 — Ads too educational** | Push detail to the page; route to `video-script-system` |
| Never got traction from launch, good craft | Whether the desire has urgency | **1 — No urgency in the desire** | Re-angle. Route to `creative-concepting` |
| Whole account down at once across every creative | Calendar, tracking, page, account-level change | Almost never creative | Check layers 1–2 before writing a single note |
| Spend won't scale past a ceiling at target CPA | Audience saturation vs desire size | **1** or **6 — Positioning** | Awareness-stage shift hypothesis, or `positioning-mechanisms` |
| Every new creative flat despite strong hooks | Whether the product is perceived as you think | **6 — Positioning** | Hand to `positioning-mechanisms` |
| CPM and frequency rising, everything else stable | Platform drift vs account history | **Not a cause** | See below |

**Rising CPM and frequency are not diagnoses.** Meta's price per ad rose +12% YoY in Q1 2026 and +12% YoY in Q2 2026 (29 Apr, 29 Jul 2026) — roughly 0.95%/month of compounding auction inflation independent of any creative. Compare the account to its own history and to that drift before treating cost movement as a finding. Fatigue doctrine lives in `testing-and-iteration/references/cadence-and-fatigue.md` — 36 lines, and the only place it is written down. Do not re-derive it here.

## The six causes `[T p.92–94]`

**Check + fix for all six, inline, so a clear-symptom diagnosis needs no reference load.** `references/diagnostic-tree.md` adds the symptom shapes, the book's cases (the Valentine's collapse, the $200k account, the wall-art re-angle, the Rose Skin Co. summer re-position), the exceptions and the diagnostic-value notes — load it when the symptom is ambiguous, when two causes survive, or when you need the case to justify an expensive fix.

| # | Cause | One-line test | The check (cost) | The fix |
|---|---|---|---|---|
| 1 | **No urgency in the desire** | Is the pain painful *now*? "Snoring" vs "can't sleep in the same bed as my wife because of my snoring" | Moderate, a reading exercise. Ask what happens to this person if they do nothing for another month. "Nothing much" = no urgency | Re-angle onto a consequence already being paid — a *nearer* promise, not a bigger one. Route to `creative-concepting` with the consequence named, or `market-research` if you cannot name one from evidence. Urgency in the desire is not urgency in the offer |
| 2 | **Ads too educational** | Does the ad teach when it should make them want? People scroll for dopamine | Cheap — watch the ad and timestamp where it stops making them want and starts teaching | Focus on the desired state; use curiosity to push technical detail onto the page `[T p.92]`, then confirm the page carries it. Exception: when the spec *is* the desire, education is correct. Route `video-script-system`, or `hook-system` to rebuild the gap |
| 3 | **Seasonality** | Does the desire have a clock — and can fulfilment still meet it? | **Free, and always first.** Shipping cutoffs, stock, promo end date, holiday calendar, last year's same weeks | Operations first — extend the cutoff, change the shipping promise or the date framing. Then re-position to the state people are actually in. Never reshoot last season's angle in this season's weather |
| 4 | **Repeating the same strategy** | Read eight weeks of hooks. Is there a new idea? The main issue in 90% of underperforming accounts `[T p.93]` | Moderate — free but an hour. Pull 8 weeks of hooks as verbatim text in one column, then the angles, and ask whether there is a new idea. The roadmap matrix in `testing-and-iteration` shows it without the manual pull | New concepts per canon §6, not more iterations or re-hooks of the same footage. This is **message staleness**, not fatigue — declare it from reading the hooks, never from a cost chart |
| 5 | **Landing page** | Does the page follow through the thought the ad opened, and share its theme? *"Your prospect should never click on your ad and be like, 'What the hell did I end up at?'"* | Cheap — one page load. **CWV at mobile p75 first**; a failing page invalidates the creative read, so score nothing else until it passes | Page work in the order `references/page-audit-rubric.md` ranks it. Never re-hook a page problem — a better ad sends more traffic into the same leak. Continuity breaks and page copy → `ad-copy-qa` |
| 6 | **Positioning** | Does how you see the product match how they see it? | Moderate. Ask what the product *is* to the buyer — the category they file it under, the alternative they compare against, what switching costs them — then compare to how the brand describes itself. The gap is the diagnosis | Hand to `positioning-mechanisms`. Never attempt a reposition inside a troubleshooting run. **Only conclude cause 6 after 1–5 are named as ruled out** — it is the most expensive to act on and the easiest to reach for prematurely |

## The commercial-vs-creative split

Run this whenever CPA moved and the cause isn't obvious. It separates four things that all show up as "CPA is up".

| If this moved | The cause is | Source |
|---|---|---|
| Sessions and CTR steady, page CR down | Funnel or page | BigQuery: orders / sessions over the window |
| AOV down, orders steady | Offer or product mix | BigQuery: AOV, mix by product |
| Orders steady, margin down | Margin — discount depth, shipping, COGS | BigQuery: net sales vs gross, discount and refund rate |
| New-customer share down, total orders steady | The account bought returning customers, not growth | BigQuery: new vs returning share |
| Hook rate and hold rate down at the ad level | Creative — and only then | Meta: `level="ad"`, video metrics over the same window |

**Two calls, matched windows.** One Meta insights call and one BigQuery aggregate, both covering the same dates, or the comparison is meaningless.

Call hygiene: one well-formed query, never five exploratory ones, and every attributed figure carries its model and window — canon §7. The full contract (explicit `fields` and `level`, tight dates, `limit` with a `sort`, uppercase filter operators, the 1–2 breakdown limit, the attribution default, never selecting a `description` column) is `testing-and-iteration/references/live-performance-reads.md` — 26 lines, and the only place it is written down. Load it when you are about to make a call, not to plan one.

**Degrade gracefully.** If a connector fails or returns nothing, name the call and what it would have told you, then diagnose from the creative, the page and the calendar. Never estimate a performance figure.

## The Core Web Vitals pre-flight gate

Before any creative test against a page: **LCP ≤2.5s, INP ≤200ms, CLS ≤0.1**, at the **75th percentile of mobile** page loads (web.dev, 31 Oct 2024). **If any metric fails, stop** — you are testing the page, not the hook. **Never claim** that Meta penalises landing-page experience in delivery or cost; no verifiable claim exists, and the honest framing is that mismatch and slowness cost conversion rate, which raises CPA.

The base rate (only 48% of mobile / 56% of desktop sites pass), the FID→INP note and the reporting format are in `references/page-audit-rubric.md` → Step 0. Do not load the rubric just to run the gate — the three thresholds above are the gate.

## Output

```
DIAGNOSIS: [primary cause, numbered] — confidence HIGH / MEDIUM / LOW

RULED OUT IN COST ORDER
  1 Fulfilment / calendar:  [what was checked, what it showed]
  2 Landing page:           [checked / not reached, and why]
  3 Messaging / positioning:[checked / not reached]
  4 Creative execution:     [checked / not reached]

EVIDENCE
  - [the number, its source, and for attributed metrics the model + window]
  - [what a concurrent control would have shown, if one exists]

THE FIX
  Do now (free or cheap):  [ ... ]
  Then (moderate):         [ ... ]
  Only if the above fail:  [the expensive fix, named as expensive]

NOT THE CAUSE
  [what was suspected and eliminated — as valuable as the diagnosis]

HANDOFF
  [sibling skill, and the one question it needs to answer]
```

State confidence honestly. LOW confidence with the ruled-out list intact is a useful deliverable; a confident guess at layer 4 is not.

## Handoffs

Finding → skill, one line each: positioning mismatch → `positioning-mechanisms` · angle has no urgency → `creative-concepting` · hook fails the golden rules → `hook-system` · script over-educates or sags mid-roll → `video-script-system` · objection unaddressed on the page or in the ad → `belief-objection-engineering` · ad→page continuity break or page copy needs rewriting → `ad-copy-qa` · the desire itself is unproven or the audience is unknown → `market-research` · a new test is the right next move → `testing-and-iteration` · the asset has execution defects → `prelaunch-qa`. Always name the **one question** the receiving skill has to answer.
