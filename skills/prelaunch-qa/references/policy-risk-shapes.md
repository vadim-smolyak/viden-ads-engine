# Policy-risk shapes — pattern recognition, not policy citation

**The standing constraint.** The rule text for the policies below was never retrievable during research — `transparency.meta.com` renders JS-only and returned zero body text on three attempts (`shared/evidence.md`). Nothing here is written from memory of a policy document. This file is a list of *shapes that warrant a human read*, plus the URL where the actual rule lives.

**Never** assert what a policy says. **Never** clear copy as compliant. **Never** tell a client an ad will be approved or rejected.

**Boundary.** This file is for reviewing a **finished asset**, where imagery, on-screen text and shipped copy are all in frame. A copy-only pass on primary text and headlines belongs to `ad-copy-qa`. The imagery, Special Ad Category, AI-visibility and specs sections below are this skill's alone.

---

## The flag, verbatim

Use this wording. It is honest about what this plugin can and cannot do.

```
POLICY FLAG
  Risk:      [the specific shape, quoting the line or describing the frame]
  Policy:    [the URL below that governs it]
  Action:    This needs a human read against the policy text before launch.
             This plugin does not hold the rule text and cannot clear it.
```

One flag per distinct shape. Do not batch three risks into one flag — each needs its own line and URL.

---

## Shape → policy URL

| Shape in the creative | Why it's high risk | Policy URL to point at |
|---|---|---|
| Copy implying knowledge of the reader's health condition — "your snoring", "since your diagnosis", "you have [condition]" | Personal attributes: implying knowledge of someone's condition or identity | `transparency.meta.com/policies/ad-standards/objectionable-content/privacy-violations-personal-attributes` |
| Copy implying knowledge of the reader's financial situation — debt level, credit score, income bracket, benefits status | Same personal-attributes surface, financial variant | Same URL as above |
| Weight-loss claims, body-transformation framing, goal-weight language | Health & wellness restrictions | `transparency.meta.com/policies/ad-standards/restricted-goods-services/health-wellness/` (the `/weight-loss/` path 404s; rules live in the parent page) |
| Before/after body imagery, close-crops of a body part being "fixed" | Health & wellness plus adult-nudity adjacency | Same health & wellness URL |
| Any personal-health framing — supplements, conditions, symptoms, medical devices | Personal health | `facebook.com/business/help/2489235377779939` |
| Income or earnings claims — "$10k/month", "replace your salary", screenshots of earnings | Unacceptable business practices | Meta ad standards, unacceptable business practices section |
| Guaranteed-outcome language on any regulated outcome — health, money, immigration, legal | Same | Same |
| "You" framings that presume a diagnosis, a debt, or a body — even implicitly | The single most common failure shape in this list | Personal attributes URL |
| Nudity, near-nudity, suggestive framing used to stop the scroll | Adult nudity and sexual activity | Meta ad standards, adult content section |
| Copy or imagery designed to route around review — obfuscated text, misspelled restricted terms, cloaked landing pages | Circumventing systems. Never assist with this; flag and stop. | Meta ad standards, circumventing systems section |

---

## Special Ad Categories — a targeting consequence, not a creative rule

If the product sits in `HOUSING`, `EMPLOYMENT`, `FINANCIAL_PRODUCTS_SERVICES` (2024's "CREDIT", broadened) or `ISSUES_ELECTIONS_POLITICS`, note it in the verdict. Meta's own doc states no specific creative restrictions beyond standard policies — but the targeting constraints change what the creative has to do:

- Age locked 18–65+, no gender targeting, no lookalikes, 15mi/25km minimum radius, approved interest list only (Marketing API v26.0, 21 May 2026).
- **The consequence:** with no lookalikes and no demographic targeting, **the creative is the only targeting instrument left.** The first line must qualify the audience explicitly. In these categories, an unqualified hook is a delivery defect, not just a weak hook.

Add this as an ISSUE if the hook does not name who it's for.

---

## AI-generated creative — when to escalate

VIDEN uses AI avatars proactively. This is not a prohibition list; it is when a human decides.

| Situation | Action |
|---|---|
| Visible AI artefacts — warped hands, drifting text, uncanny motion | ISSUE, not a policy flag. Treat visible-AI as a **craft defect to fix**: Kantar (4 Nov 2025) found seamlessly integrated AI put over 40% of ads in the top tier for branded cut-through, while obvious AI performed worse. |
| Gen Z-skewed audience with an AI avatar | Flag for a human call. IAB + Sonata Insights (15 Jan 2026, 505 US Gen Z/Millennial + 104 execs): negative sentiment 37%, up 12 points from 2024; Gen Z 39% negative vs Millennials 20%. |
| EU-targeted campaign using a synthetic human likeness | Escalate to the client's legal contact. EU AI Act Article 50 applied 2 August 2026 and makes the *advertiser* a deployer who must apply perceivable labels to deepfakes. Ads are not explicitly addressed and no deadlines were given — so this is a legal question, not an agency one. |
| Political, social-issue or election ad using AI-generated media | Hard escalation. Advertiser self-disclosure **is** required (19 Feb 2026), plus authorisation, "paid for by", 7-year Ad Library retention, and the API `authorization_category` value `POLITICAL_WITH_DIGITALLY_CREATED_MEDIA`. |
| Ordinary ecom ad with an AI avatar | No disclosure flag needed. There is **no blanket advertiser disclosure requirement** for ordinary ads; Meta applies its own "AI info" label next to *Sponsored* when an AI-generated photorealistic human is included. Agency posts claiming a mandatory blanket disclosure are wrong. |

---

## The teaching example that must never ship

The book's flagship hook — *"Little-known secret about Medicare that could cost you thousands"* `[T p.32]` — hits the personal-attributes shape and the financial-situation shape, and today sits inside `FINANCIAL_PRODUCTS_SERVICES`.

It is an excellent illustration of the three golden hook rules. **Do not ship it, and do not ship anything built to its pattern without a flag.**

---

## Specs — what can and cannot be asserted

Only these numbers are sourced (Instagram Ads API *Media Requirements*, retrieved 2026-08-07, page undated): minimum width 600px (Facebook Stories >500px); caption up to 2,200 characters; video 3–60s, ≤2.3GB; IG Feed recommended 1:1, supported 1.91:1 to 4:5, with 4:5 needing at least 600×750; IG Stories recommended 9:16.

**Unverified and therefore never stated:** Facebook Feed and Reels ratios, Instagram Reels ratios, in-stream ratios, **safe-zone margins**, maximum durations by placement, text truncation points.

**Placements that no longer exist** (v26.0, 29 Jul 2026): Instagram Explore Feed removed; Messenger Stories `story` position silently removed — stale scripts appear to work; poll components unsupported.

**The 20% text rule** has no current cap in any retrievable doc, and Meta now *adds* image text as a feature. Treat text density as a performance variable, not a compliance gate. That is labelled inference from first-party evidence, not a policy citation.
