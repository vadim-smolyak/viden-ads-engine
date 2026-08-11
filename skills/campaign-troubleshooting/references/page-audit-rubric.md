# Page audit — the scored rubric

Load this when cause 5 is live. This file **scores the page as a conversion instrument**. It does not audit ad→page continuity and it does not write page copy — both belong to `ad-copy-qa`'s post-click alignment. Run the gate, score the page, rank the fixes, hand the rewrites over.

---

## Step 0 — the Core Web Vitals gate. Run this first.

| Metric | Threshold | Measured at |
|---|---|---|
| **LCP** | ≤ 2.5s | 75th percentile, **mobile** |
| **INP** | ≤ 200ms | same |
| **CLS** | ≤ 0.1 | same |

Source: web.dev, last updated 31 Oct 2024. A playbook citing FID is out of date — FID was replaced by INP.

**If any metric fails at mobile p75, stop and report.** Do not score the rest, and do not run a creative test against this page: you are testing the page, not the hook. Only 48% of mobile and 56% of desktop sites pass (HTTP Archive *Web Almanac 2025 — Performance*, 15 Jan 2026; CrUX + WebPageTest, July 2025 data) — a failing page is the base rate, not an anomaly, so expect this gate to fire often.

**Never claim** that Meta penalises landing-page experience in delivery or cost. No verifiable claim exists. The honest mechanism: slowness and mismatch cost conversion rate, which raises CPA.

---

## The 100-point rubric — nine categories

Score every category. The total is only meaningful because these nine sum to it; never report a "/100" assembled any other way.

| Category | Max | What earns the points |
|---|---|---|
| **Positioning clarity** | 15 | The problem and the solution are unmistakable in one screen; the buyer is obviously named; differentiation is stated, not implied |
| **Headline effectiveness** | 15 | Specific, benefit-carrying, and the most prominent thing on the page |
| **Copy quality** | 15 | Benefit-led, scannable, one idea per section, no filler |
| **CTA strategy** | 15 | Visible without scrolling, action-led, low friction, one primary action |
| **Trust signals** | 10 | Real, specific and early — named customers, counts, verifiable proof |
| **Visual hierarchy** | 10 | The eye is led; emphasis matches importance; nothing competes with the CTA |
| **Objection handling** | 10 | The top two objections are answered on the page — FAQ, comparison, guarantee, risk reversal |
| **Pricing presentation** | 5 | Clear, justified, anchored against the alternative the buyer is actually weighing |
| **Brand voice** | 5 | Consistent and appropriate to the buyer; recognisable |

**Bands.** 80+ the page is not your problem, look elsewhere in the tree. 60–79 real leaks, fixable, worth doing before a reshoot. Below 60 the page is the constraint — creative testing against it is wasted spend.

**Never state an expected conversion lift.** Not a percentage, not a range, unless the number comes from this client's own historical test. `shared/evidence.md` never-state list: no message-match conversion-lift figure has a publisher, date and disclosed sample behind it.

---

## Above-the-fold checklist — the presence/effectiveness pass

Six elements. Mark present or absent, then score effectiveness out of 10. These feed the positioning-clarity, headline, CTA, trust and hierarchy categories above — they are not a separate score.

| # | Element | Absent means |
|---|---|---|
| 1 | Headline carrying a clear value proposition | The reader has to work out what this is. Nothing below the fold rescues that |
| 2 | Subheadline explaining the "how" | The claim floats without a mechanism |
| 3 | Hero image or video showing the **outcome**, not just the product | Nothing to want |
| 4 | Primary CTA visible without scrolling, in a contrasting colour | The conversion path is hidden |
| 5 | One trust signal — logo bar, rating, or a real quote | Skepticism goes unanswered at the exact moment it forms |
| 6 | Navigation minimised | Every extra link is an exit |

---

## Conversion killers — the diagnostic taxonomy

Named failure modes, ranked by how often they turn out to be the binding constraint on paid traffic. Impact is qualitative on purpose: no impact number here is sourced, so none is stated.

| Killer | Why it costs conversions | Fix |
|---|---|---|
| Fails Core Web Vitals at mobile p75 | Readers leave before the page renders; every downstream measurement is contaminated | Step 0. Fix before anything else |
| Ad / page mismatch | The thought the ad opened is dropped; trust breaks at the first screen | Route to `ad-copy-qa` post-click alignment |
| Unclear value proposition | Confusion resolves as a bounce, not a question | Rewrite the headline around one specific outcome |
| Competing CTAs | Two primary actions is zero primary actions | One primary action per page; demote the rest |
| CTA below the fold | The path is invisible at the moment of highest intent | Move it up |
| Too many form fields | Every field is a decision to abandon | Cut to what the business genuinely needs today |
| No trust signals early | Skepticism forms before proof arrives | Move one proof element above the fold |
| Poor mobile experience | Most paid social traffic is mobile — a desktop-first page loses the majority audience | Mobile checklist below |
| Visual clutter | Nothing is emphasised, so nothing is read | Remove elements; do not add |
| Weak CTA copy | "Submit" and "Learn more" give no reason to act | Action verb plus the value received |
| Wrong page type for the traffic | A hyper-specific ad landing on a collection or home page hands back the filtering job the click was meant to do | Send to a page matching the ad's specificity |
| Detail promised and never delivered | The ad deliberately deferred the technical detail (cause 2) and the page does not carry it | Add the detail the ad pushed downstream |

The last two are the ones that come from the *ad* side of the diagnosis and get missed by page-only audits.

---

## Mobile assessment

Paid social traffic is predominantly mobile. Audit the mobile rendering, not the desktop one.

- [ ] Layout is genuinely responsive, not a scaled desktop page
- [ ] Touch targets large enough to hit with a thumb (≈44px is platform design guidance, not a measured performance claim)
- [ ] Body text readable without zoom
- [ ] Usable on a slow connection — reconfirm with the Step 0 gate
- [ ] Form uses correct input types and keyboards; no desktop-only interactions
- [ ] Sticky CTA on any page longer than two screens
- [ ] Media does not push the CTA off the first screen on a small viewport

---

## Output

```
PAGE AUDIT — [URL]

CWV GATE: pass / fail / not checked
  LCP [x]s · INP [x]ms · CLS [x] at mobile p75
  If fail: the creative read against this page is unreliable until fixed. Stop here.

SCORE: [N]/100
| Category | Score | Note |
| Positioning clarity | /15 | |
| Headline effectiveness | /15 | |
| Copy quality | /15 | |
| CTA strategy | /15 | |
| Trust signals | /10 | |
| Visual hierarchy | /10 | |
| Objection handling | /10 | |
| Pricing presentation | /5 | |
| Brand voice | /5 | |
| TOTAL | /100 | |

KILLERS FOUND
| Killer | Severity | Fix | Effort |

FIX ORDER
  1 [free or cheap]
  2 [moderate]
  3 [expensive — named as expensive]

HAND OFF
  Continuity breaks and page copy rewrites -> ad-copy-qa (post-click alignment)

COVERAGE: which sections were assessed, and which could not be (partial screenshot, gated page, logged-out view)
CONFIDENCE: HIGH / MEDIUM / LOW
```

Always state coverage. A rubric score from a partial screenshot presented as a full audit is worse than no score.

---

## Rules

- Score against the rubric, not against taste. If a category scores low, name the element that cost the points.
- Give the corrected element, never criticism alone — except where the rewrite belongs to `ad-copy-qa`, in which case name the break and hand it over.
- Rank fixes by impact against effort, and label the expensive ones as expensive.
- If the URL cannot be fetched, ask for a screenshot and say which categories cannot be scored from an image.
- Never state a conversion-lift figure that is not from this client's own history.
