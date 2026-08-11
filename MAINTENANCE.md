# Maintenance

Everything in this plugin is baked in and timestamped so that **no skill has to search the web at runtime**. The cost of that decision is that some rules will rot. This file says which ones and when.

All evidence was verified **August 2026**. The authority is `shared/evidence.md` — if a search result ever disagrees with it, evidence.md wins until someone updates it here.

## Re-verify on a schedule

| Item | Where it lives | By when | Why it rots |
|---|---|---|---|
| Placement availability | `shared/evidence.md` → Specs | Each Marketing API version | v25.0 removed ASC/AAC creation; v26.0 removed Instagram Explore Feed and silently dropped Messenger Stories. Silent removals are the dangerous kind — stale scripts appear to work. |
| EU AI Act applicability to ads | `shared/evidence.md` → AI creative | **December 2026** | Article 50 applied 2 Aug 2026; grace period ends Dec 2026; ads are not yet explicitly addressed. This is the highest-priority date on the list. |
| 3-second video metric deprecation | `shared/evidence.md`, `prelaunch-qa` item 5 | December 2026 | Deprecation announced for organic endpoints only. If it reaches Ads Insights, hook-rate reporting changes. |
| Meta ad policy rule text | `shared/evidence.md` → Policy | As soon as a browser is available | **Never retrieved** — `transparency.meta.com` is JS-only. This is a real, open gap, not a stale entry. |
| Ad specs and safe zones | `shared/evidence.md` → Specs | As soon as a browser is available | Same cause: the Advertiser Help Centre is robots-blocked. |
| Creative-analytics benchmarks | `shared/evidence.md`, `testing-and-iteration` | Annually | The 3.0/week and 3.85% figures come from one vendor with a commercial interest in the metric. |
| Core Web Vitals thresholds | `campaign-troubleshooting` | Annually | Metric definitions change — FID became INP. |
| Special Ad Categories | `shared/evidence.md`, `positioning-mechanisms` | Twice yearly | CREDIT became FINANCIAL_PRODUCTS_SERVICES; the constraint list changed in v26.0. |
| Platform character limits | `ad-copy-qa/references/platform-limits.md` | When a spec source becomes reachable | Currently labelled **house defaults**, not platform documentation, because no Meta spec page was retrievable. |

## The two gaps worth closing first

**1. Policy text.** Open these in a browser and transcribe with a retrieval date into `shared/evidence.md`:

- `transparency.meta.com/policies/ad-standards/objectionable-content/privacy-violations-personal-attributes`
- `transparency.meta.com/policies/ad-standards/restricted-goods-services/health-wellness/` (note: `/weight-loss/` 404s — the rules are in the parent page)
- `facebook.com/business/help/2489235377779939` (personal health)

Until then `prelaunch-qa` and `ad-copy-qa` correctly **flag and point** rather than asserting rules. That behaviour is deliberate. Do not replace it with rules written from memory.

**2. Specs and safe zones.** Open `facebook.com/business/help/103816146375741` and `facebook.com/business/help/682655495435254`, transcribe with a date.

## How to change doctrine

Doctrine lives in exactly one place. Change it there, not in the skill that uses it.

| To change | Edit |
|---|---|
| A shared definition, the awareness↔flow mapping, the hook stack, the glossary, the iteration ladder, the metric rule | `shared/canon.md` |
| An evidence claim, a citation, a never-state entry, a schedule row | `shared/evidence.md` |
| A workflow step or a routing decision | the relevant `skills/*/SKILL.md` |
| A library entry (tactic, format, mechanic, model, template) | the relevant `skills/*/references/*.md` |
| A tactic or format entry | the alphabetical / medium **shard**, plus its row in the owning index (`hook-system/references/tactics.md`, `creative-concepting/references/visual-formats.md`). An entry with no index row is invisible |

**The invariant that keeps this maintainable:** no skill restates anything canon defines. If you find a duplicated definition, that's a bug — delete it and reference canon instead.

## Deliberately out of scope

**Meta's Advantage+ creative enhancements** (23 features as of v26.0, 28 Jun 2026 — `video_uncrop`, `video_filtering` with SDR-to-HDR conversion, `add_text_overlay`, `image_background_gen` and others). These can alter a delivered asset, and Meta flips features default-on with roughly a week's notice.

House ruling: this plugin produces great creative; it does not manage platform post-processing. Recorded here so a future reader knows it was a decision. If it needs revisiting, the list is at `developers.facebook.com/docs/marketing-api/creative/advantage-creative/get-started/`.

## Adding to the living libraries

Two references are designed to grow, and both carry their own update protocol:

- `hook-system/references/voice-patterns.md` — add hook templates found in the wild, and update the one-line cluster map at the top. Tag each with its tactic. A pattern with no matching tactic means either the tag is wrong or the tactic library needs a new entry; don't leave a dangling tag. (Four dangling references in the source skills are exactly how this plugin's predecessors decayed.)
- `creative-concepting/references/visual-formats.md` — add formats as they emerge. **Two edits per format, never one:** a row in the selection table here, and the full entry in the medium shard (`formats-static.md` / `formats-video.md` / `formats-either.md`). Map each to awareness stages and to a mechanic that actually exists. Update the format count in the title, the shard table and `creative-concepting/SKILL.md`'s reference index.

## Version log

| Version | Date | Change |
|---|---|---|
| 0.1.1 | 2026-08-11 | Latency pass. No library entry, rule, citation or template removed — counts verified identical (47 tactics, 46 formats, 8 mechanics, 25 voice templates, 72 models, 20 motivations, 15 desire moves, 12 checklist items, 5 flows, 6 passes, 14 copy checks, 126 distinct `[T p.N]` citations, 27 dated 2026-evidence citations). Restructuring only: `tactics.md` and `visual-formats.md` became indexes over shards; `copy-checks.md` split into fast/standard/policy/examples; the prelaunch and six-cause tables absorbed the fix column so the common verdict loads no reference; connector call hygiene, cadence and fatigue doctrine moved out of always-loaded SKILL.md files into references; the eight triggers and the eight mechanics inlined as one-line tables in their owning SKILL.md; `build_brief.py` marked EXECUTE-ONLY. Median atomic request now loads 48% fewer lines. |
| 0.1.0 | 2026-08-07 | Initial build. Book extracted cover to cover (99pp); 22 existing skills audited and superseded; 2026 verification across 10 topic areas; 4 doctrine corrections applied; 3 house rulings recorded (Meta auto-enhancements out of scope, AI avatars supported, broken inherited content dropped rather than repaired). |
