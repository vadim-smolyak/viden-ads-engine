# Evidence — what 2026 changed, and what must never be asserted

Load this only when a rule needs justifying, a number needs checking, or someone challenges a doctrine call. Not needed for routine execution.

All rules verified **August 2026**. Re-verification schedule at the bottom.

---

## Never state these — no traceable source at any quality level

| Claim | Status |
|---|---|
| "The hook is 80% of the ad" (as a *performance* claim) | Folklore. No traceable source. The book only ever claims 80% of the author's *time* `[T p.32]`, which is a defensible workflow statement. |
| Any specific hook-rate or hold-rate benchmark | Unverifiable. Quote the client's own account history instead. |
| Any fixed creative-refresh interval ("every 4 weeks") | Unverifiable, and the two credible sources point away from a fixed calendar. |
| "Creator content delivers 2× the impact" | Real and attributable (Kantar, 13 Jan 2026) but **no disclosed sample**, phrased as a ceiling ("can"), and Kantar sells the measurement framework. Don't repeat as a benchmark. |
| Any sound-off percentage | Unverifiable. Keep the muted-first heuristic, delete the number. |
| Any message-match conversion lift % | No study with publisher + date + disclosed sample isolates it. |
| "Creative is the new targeting" | Every source was agency/SEO content with zero primary evidence. |
| Any Meta ad spec number not on this page | The Advertiser Help Centre was unreachable during research. See "Specs" below. |

**Rule: if a number can't be sourced, say the number is unavailable.** A gap stated honestly is worth more than a plausible fabrication.

---

## Superseded — do not teach these as the book states them

**The 3-second window.** Meta is deprecating 3-second viewer metrics (Meta for Developers, 18 Feb 2026 — organic endpoints only; no Ads Insights `video_*` field is on the list, so the ads-side metric survives for now). The evidenced attention window is **1.5–2.5 seconds** (Amplified + VCCP Media, 16 May 2025 — 20,000+ views of 72 ads, 8 brands, "bad twin" design). IAB/MRC Attention Measurement Guidelines v1.0 (Nov 2025) set **no universal minimum duration threshold**.

> **Attention is re-winnable.** Kantar (29 Jul 2024, 40 ads, ARF Attention Validation Initiative) found **a product introduction at second 7 created new attention.** A weak second half is fixable, not fatal. This is the single most useful correction in this file.

**Keep** the book's "new visuals every 3 seconds" `[T p.77]` as a *craft* heuristic for pacing — it's good filmmaking. **Drop** the causal claim behind it.

**Front-load recognisable, not merely arresting.** Kantar (5 Feb 2026): Instagram "matched TV level recall thanks to brand cues landing within the first two seconds." Amplified/VCCP: best brand code delivered 3.5× attention-adjusted ROI; 85% of digital ads get under 2.5s. Distinctiveness beats novelty.

**Weekly creative volume.** The book's 6–12/week `[T p.95]` is contradicted by the only large disclosed-sample dataset: Motion *Creative Benchmarks 2026* (578,750 creatives, 6,015 brands, $1.29B, Meta only) — top-quartile accounts by winner count launch **3.0/week against a 3.3/week median**, i.e. slightly *fewer*. Hit rate **3.85%**; roughly half of all ads never receive meaningful spend. This cuts against Motion's commercial interest, which strengthens it. The book's own quality caveat `[T p.97]` was the correct instinct.

**CPA as the winner test.** Meta's incremental attribution "drove a 24% increase in incremental conversions compared to our standard attribution model" (Meta Newsroom, 28 Jan 2026) — two Meta models, 24% apart. Insights default window is `["1d_view","28d_click"]`. Haus (640 Meta incrementality experiments, 28 Jul 2025): **58% of brands saw higher iROAS on Manual than Advantage+**; forcing a 50/50 split cost 18% iROAS. See canon §7 for the two-lane rule.

**Fatigue signals.** Kantar (26 Apr 2024, ~20-year tracking database, 1,582/1,645/1,706/1,292 ads across three markets): **no relationship between frequency and "fed up" scores**, no wear-in effect on enjoyment, and a **positive** correlation between frequency and Executional Branded Memorability. ARF (23 Sep 2025): "true creative wearout is less common than once assumed," requiring heavy short-term frequency **and** poor creative quality.

**Rising CPM is not fatigue.** Meta's price per ad rose **+12% YoY in Q1 2026 and +12% YoY in Q2 2026** (29 Apr, 29 Jul 2026) — roughly 0.95%/month of compounding auction inflation independent of any creative. Every CPM-triggered fatigue rule now fires on market conditions.

**A lift at swap time is not proof of decay.** Engineering at Meta (5 Aug 2026): semantic content features are "especially helpful in cold-start scenarios" for new ads. New creative is neither penalised for lacking history nor rewarded for novelty — so replacing an incumbent and seeing a lift proves nothing without a concurrent control.

→ **Diagnose *message staleness* (same hooks, same messaging, nothing new to say — the book's actual finding at `[T p.93]`) not "fatigue".**

---

## Still holds

- **Ad length "depends" on product complexity and buying mindset** `[T p.74]`. The book's refusal to give a number is its strength. Kantar (5 Feb 2026): "15 second ads can pack just as much brand building punch"; but on Amazon Prime in an NFL environment the 30s cut pulled **1.4× higher active attention**. Kantar (29 Jul 2024): a 15s cut beat the 6s cut where the idea needed setup. Fit length to message.
- **Research before creative; a written hypothesis per test** `[T p.12, p.95]`. More defensible than ever now platform attribution is contested (IAB *State of Data 2026*, 2 Feb 2026).
- **Simple beats clever; one desire, one avatar** `[T p.69, p.72]`.
- **Consistency over bursts; quality ceiling on volume** `[T p.97]`.
- **Desire has a clock** `[T p.38, p.92]`.
- **UGC/creator-led outperforms** — direction is consensus (IAB, 6 Nov 2025: UGC ad revenue now outpaces professionally produced content), but **no disclosed-sample controlled UGC-vs-studio comparison on Meta exists.** Strong prior, not proven law.

---

## AI-generated creative — VIDEN uses AI avatars proactively

**House position:** AI avatars are a supported production path. The evidence below is for calibration, not prohibition.

- **Independent evidence is unfavourable on average.** Kantar LINK database (26 Mar 2026): AI-generated ads average the **54th percentile vs 65th for non-AI**.
- **The variable that matters is visibility, not AI-ness.** Kantar (4 Nov 2025, hundreds of LINK ads + facial coding): seamlessly integrated AI put **over 40% in the top tier for branded cut-through**; obvious AI performed worse. So the production note is: invest in making it seamless, and treat visible-AI artefacts as a defect to fix, not a style.
- **Audience skew is real.** IAB + Sonata Insights (15 Jan 2026; 505 US Gen Z/Millennial + 104 execs — best disclosure in the set): negative sentiment **37%, up 12 points from 2024**; **Gen Z 39% negative vs Millennials 20%**. 41% of consumers say AI ads bother them vs 29% of marketers. **Flag AI avatar use on Gen Z-skewed audiences for a human call.**
- **Meta's own figures** (+11% CTR from background generation) are Meta-on-Meta with no disclosed sample or control. Don't cite them to clients as evidence.

**Labelling — what actually applies:**
- **No blanket advertiser disclosure requirement for ordinary ads.** Meta applies its own label: ads "created or significantly edited using our generative AI creative features" get an "AI info" label, and it appears **next to the *Sponsored* label** when an **AI-generated photorealistic human** is included. Meta "automatically detect[s] ads created or edited using third-party AI tools through industry-standard signals" (3 Feb 2025, updated 1 Jun 2026). Agency posts claiming a mandatory blanket disclosure are wrong.
- **Political / social-issue / election ads DO require advertiser self-disclosure** (19 Feb 2026), plus authorisation, "paid for by", 7-year Ad Library retention, and API `authorization_category` value `POLITICAL_WITH_DIGITALLY_CREATED_MEDIA`.
- **EU AI Act Article 50 applied 2 August 2026.** Makes the *advertiser* a "deployer" who must apply perceivable labels to deepfakes; up to €15M or 3% of global turnover; grace period to Dec 2026 for systems already on market. Meta signed the EU AI Act Code of Practice 28 Jul 2026, but **ads are not explicitly addressed and no deadlines were given.** For EU-targeted campaigns using a synthetic human likeness, escalate to the client's legal contact rather than deciding in-house.

---

## Special Ad Categories — where the creative does the targeting

Verified in full (Marketing API v26.0, updated 21 May 2026). Categories: `HOUSING`, `EMPLOYMENT`, **`FINANCIAL_PRODUCTS_SERVICES`** (2024's "CREDIT", broadened), `ISSUES_ELECTIONS_POLITICS`, `NONE`.

Constraints: age locked **18–65+**, no gender targeting, minimum **15mi/25km radius** (15km Europe), no ZIP/neighbourhood, no location exclusion, **no lookalikes**, approved interest list only. New in v26.0: must explicitly set `targeting_automation.advantage_audience` to `1` or `0` or the request errors. Meta's doc states "No specific creative restrictions… beyond standard policies."

> **The strategic consequence:** with no lookalikes and no demographic targeting, **the creative is the only targeting instrument left.** In these categories the first line must qualify the audience explicitly — the hook is doing the job an audience setting used to do. This is a genuinely different discipline from ordinary ecom creative.

---

## Policy — a real, unclosed gap

`transparency.meta.com` renders JS-only and returned zero body text on three attempts, so **the rule text for these policies was never retrieved and is not written from memory:**

- Personal attributes / the "you" problem (implying knowledge of someone's condition or identity) — `transparency.meta.com/policies/ad-standards/objectionable-content/privacy-violations-personal-attributes`
- Health & wellness, including weight loss — `transparency.meta.com/policies/ad-standards/restricted-goods-services/health-wellness/` (note: `/weight-loss/` 404s; the rules live in the parent page)
- Personal health — `facebook.com/business/help/2489235377779939`
- Unacceptable business practices; circumventing systems; adult nudity

**Behaviour when policy risk is suspected:** name the specific risk, point to the specific policy URL, and tell the user it needs a human read. Do not assert a rule, and do not clear copy as compliant on the basis of this plugin.

**Known high-risk shapes** (pattern recognition, not policy citation): implying knowledge of the reader's health condition or financial situation; before/after body imagery; income claims; "you" framings that presume a diagnosis. The book's own flagship example — *"Little-known secret about Medicare that could cost you thousands"* `[T p.32]` — hits two of these and would today sit in `FINANCIAL_PRODUCTS_SERVICES`. Excellent teaching example for the three golden rules; **do not ship it.**

---

## Specs — what is actually verified

**Only these numbers are sourced.** From the Instagram Ads API *Media Requirements* page (developers.facebook.com — **page shows no date; retrieved 2026-08-07**):

- Minimum width 600px (Facebook Stories: width must exceed 500px)
- Caption up to 2,200 characters
- Video 3–60s, ≤2.3GB
- IG Feed: recommended 1:1; supported 1.91:1 to 4:5; 4:5 needs at least 600×750
- IG Stories: recommended 9:16

**Unverified and therefore unstated:** Facebook Feed and Reels ratios, Instagram Reels ratios, in-stream ratios, **safe-zone margins**, maximum durations by placement, text truncation points. The Advertiser Help Centre is robots-blocked. To close this, a human must open `facebook.com/business/help/103816146375741` and `facebook.com/business/help/682655495435254` in a browser and transcribe with a date.

**Placements that no longer exist** (Graph/Marketing API v26.0, 29 Jul 2026): **Instagram Explore Feed** removed; **Messenger Stories** `story` position silently removed (no error — stale scripts appear to work); **poll components** no longer supported. And per v25.0 (18 Feb 2026): **Advantage+ Shopping and App campaigns can no longer be created, duplicated or updated** — migrate to unified Advantage+.

**The 20% text rule** has no current cap in any retrievable doc, and Meta now *adds* image text as a feature (`image_templates`, `add_text_overlay`). That is **inference from first-party evidence, labelled as inference** — not a policy citation. Treat text density as a performance variable, not a compliance gate.

---

## Landing page

Core Web Vitals (web.dev, last updated 31 Oct 2024): **LCP ≤2.5s, INP ≤200ms, CLS ≤0.1**, at the **75th percentile** of page loads. A playbook citing FID is out of date. HTTP Archive *Web Almanac 2025 — Performance* (15 Jan 2026; CrUX + WebPageTest, July 2025 data, millions of sites): only **48% of mobile / 56% of desktop** sites pass.

**Gate:** don't creative-test against a page failing CWV at mobile p75 — you're testing the page, not the hook.

**No verifiable claim exists that Meta penalises landing-page experience in delivery or cost.** Don't make one. The honest framing: mismatch costs conversion rate, which raises CPA.

---

## Deliberately out of scope

**Meta's Advantage+ creative enhancements** (23 documented as of v26.0, 28 Jun 2026 — including `video_uncrop`, `video_filtering` with SDR-to-HDR conversion, `add_text_overlay`, `image_background_gen`). These can alter a delivered asset, and Meta flips features default-on with roughly a week's notice.

**House ruling: out of scope for this plugin.** The job here is producing great creative, not managing platform post-processing. Recorded so a future reader knows it was a decision, not an oversight — if it ever needs revisiting, the enhancement list lives at `developers.facebook.com/docs/marketing-api/creative/advantage-creative/get-started/`.

---

## Re-verification schedule

| Item | By when | Why |
|---|---|---|
| Placement availability | each Marketing API version | v25.0 and v26.0 each removed placements |
| EU AI Act ads applicability | Dec 2026 | Grace period ends; ads not yet explicitly addressed |
| 3-second metric deprecation reaching Ads Insights | Dec 2026 | Organic-only so far |
| Meta policy rule text | as soon as a browser is available | Never retrieved — currently a real gap |
| Ad specs and safe zones | as soon as a browser is available | Same |
| Creative-analytics benchmarks | annually | Only disclosed-sample source; has commercial interest |
| CWV thresholds | annually | Definitions change (FID → INP) |
