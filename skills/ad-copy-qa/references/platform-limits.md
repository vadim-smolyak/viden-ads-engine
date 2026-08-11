# Platform limits — copy surfaces

Load this when checking whether copy fits, or when writing to a surface for the first time.

## Read this before quoting a number to a client

These tables are **VIDEN's working house limits**, carried forward from the agency's prior in-house creative tooling and reproduced here in full so nothing outside this plugin has to be loaded. They are not transcriptions of a platform document. Meta's Advertiser Help Centre was robots-blocked during research, so no ad-spec number could be retrieved and verified (`shared/evidence.md` → Specs).

Practical consequence:

- **Use these numbers as a truncation-risk guide.** They have held up in production, which is why they are here.
- **Do not present them to a client as platform-documented limits**, and do not cite them as policy.
- **One number is genuinely sourced:** Meta primary text / caption up to **2,200 characters** — Instagram Ads API *Media Requirements* (developers.facebook.com, page shows no date; retrieved 2026-08-07). Everything else in these tables is an unverified working default.
- To close the gap, a human needs to open `facebook.com/business/help/103816146375741` and `facebook.com/business/help/682655495435254` in a browser and transcribe with a date. Until then, say "our working limit is X" rather than "the limit is X."

---

## Meta (Facebook / Instagram)

| Element | Working limit | Notes |
|---|---|---|
| Primary text | **125 characters visible**, up to 2,200 total | The 2,200 figure is the sourced one. 125 is the working visible-before-truncation figure. Front-load the hook. |
| Headline | **40 characters** | Sits below the image. Truncates hard and without an ellipsis in some placements. |
| Link description | **30 characters** | Below the headline. Often suppressed entirely depending on placement and objective. |
| Display link | **40 characters** | Optional. |

Behaviour to write for:
- Assume the reader sees **the first line only**. The hook lives in the first ~125 characters and ideally in the first clause.
- Assume the **link description may not render at all.** Never put a load-bearing claim there.
- Assume the **headline is read before the primary text** on some placements. It must stand alone.

## Google Ads (Responsive Search Ads)

| Element | Working limit | Quantity |
|---|---|---|
| Headline | 30 characters | up to 15 |
| Description | 90 characters | up to 4 |
| Display URL path | 15 characters each | 2 paths |

RSA-specific rules that change how the copy is written:
- Every headline must make sense **independently and in any combination**, because the system assembles them.
- Pin only when genuinely necessary; pinning removes combinations from the optimiser.
- Cover at least one keyword-led headline, one benefit-led headline, one CTA headline.
- The batch is the deliverable. Fifteen near-identical headlines is one headline.

## LinkedIn

| Element | Working limit | Notes |
|---|---|---|
| Intro text | 150 recommended, 600 max | Above the image |
| Headline | 70 recommended, 200 max | Below the image |
| Description | 100 recommended, 300 max | Renders in some placements only |

## TikTok

| Element | Working limit | Notes |
|---|---|---|
| Ad text | 80 recommended, 100 max | Above the video |
| Display name | 40 characters | Brand name |

## X (Twitter)

| Element | Working limit | Notes |
|---|---|---|
| Post text | 280 characters | The ad copy |
| Card headline | 70 characters | |
| Card description | 200 characters | |

---

## Placements that no longer exist

Do not write copy for these, and flag any brief that assumes them (Graph / Marketing API v26.0, 29 Jul 2026, per `shared/evidence.md`):

- **Instagram Explore Feed** — removed.
- **Messenger Stories** `story` position — silently removed. No error is raised, so stale scripts appear to work.
- **Poll components** — no longer supported.

## How to flag an over-limit line

Do not just report the overage. Supply the trimmed version, and **trim from the back**:

```
ISSUE
  Element:   headline
  Line:      "The everyday carry that finally fits everything you need"  (56 chars)
  Problem:   over the 40-character working limit for Meta headlines; will truncate mid-clause
  Rule:      surface fit, check 11
  Rewrite:   "The carry that finally fits everything"  (38 chars)
```

Count characters including spaces. Report the count so the writer can see the margin.

## The text-density question

There is **no current 20% image-text cap** in any retrievable document, and Meta now adds image text as a product feature. Treat text density as a **performance variable, not a compliance gate**. That is inference from first-party evidence and is labelled as inference in `shared/evidence.md` — do not present it as a policy citation either way.
