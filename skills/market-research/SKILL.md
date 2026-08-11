---
name: market-research
description: This skill should be used when a VIDEN strategist needs research inputs before creative — running the 5-level research ladder on a market, pulling competitor or indirect-competitor ads from Foreplay, mining voice-of-customer out of reviews and comments, or turning findings into named personas with hook and visual seeds. Trigger on "run market research on [brand]", "what does this market want", "research the competitors for [brand]", "pull [competitor]'s ads", "what hooks are competitors running", "what's been running longest in this category", "analyse these reviews", "run VOC on this export", "find the pain points", "build personas for [brand]", "what have they already tried", or "I need research bricks before I write hooks".
metadata:
  version: "0.1.0"
---

# Market Research

Research is the raw material, not the warm-up. "90% of great advertising is put together like a lego set. Market research is where you get your bricks." `[T p.12]`

Consume during a research session. Do not write ads, hooks or ideas inside one `[T p.14]`.

## Fast path vs deep path

**Default to fast.**

| Path | Trigger | Do this | Output |
|---|---|---|---|
| **Fast** — one pass | A single named question: "what are competitors hooking on?", "what do these reviews say?", "what have they tried before?" | Run only the level that answers it. Level 2/3 → Foreplay pull. Reviews/comments → VOC buckets. Tally repeats. | 5–15 tallied findings, markdown in chat |
| **Deep** — full ladder | "run market research on [brand]", new client, or a full-workflow start | Levels 1→5 in order, one tally sheet across all levels, then synthesise personas | Persona set + hook/visual seeds + tallied finding log |

Never run the full ladder to answer a fast-path question. Never search the web for doctrine, benchmarks or platform rules — those are baked in and timestamped in `shared/evidence.md`.

## Reference index — load only what the current level needs

| Load | When |
|---|---|
| `references/question-batteries.md` | Running any level. The file is split by level — read only the level's section, plus the closing synthesis battery when you reach synthesis. |
| `references/voc-extraction.md` | Reviews, comments, support tickets or survey text are in hand. Quality scoring + the 5 buckets. |
| `shared/canon.md` §2 | A finding has to select a script flow (awareness stage → flow mapping). |
| `positioning-mechanisms/references/repositioning-cases.md` | A finding looks like it re-aims the product at a new desire. |

## The 5-level ladder `[T p.14–20]`

Climb in order on the deep path. Each level answers a different question; skipping down the ladder is how research turns into guessing.

| Level | Source | The question it answers | Batteries |
|---|---|---|---|
| **1** | Your own assets — winning ads, ad comments, IG tagged posts, site reviews, support inbox | How do our actual buyers talk, and who are they buying for? | 5 batteries. Skip the whole level if pre-launch `[T p.14]` |
| **2** | Direct competitors — same product | What hooks, visuals and personas already work in this exact market? | Ads battery (10 questions) + reviews battery. **Foreplay-wired** |
| **3** | Indirect competitors — different product, same desire | How is this desire being sold by people we do not think of as rivals? | Same two batteries. **Foreplay-wired.** "We get a lot of good ad inspiration from understanding how indirect competitors are selling to the same desire" `[T p.17]` |
| **4** | Content around the desire or problem | What does the buyer see when they search as themselves? | Search as the buyer, not as the marketer. Comments are where "some of the best gold" sits `[T p.18]` |
| **5** | General niche content — not problem-specific | What content works in this niche, and what is the benefit behind the benefit? | Look specifically for what makes people happy and what makes them sad `[T p.19]` |

Level 2 reviews with no reviews on the competitor's own site: find the same product on Amazon `[T p.16]`.

## Prioritisation — the frequency tally `[T p.15]`

Every finding gets a line. Every time that finding is seen again, add a `*`. `Makes people money *****` was seen five times.

Do this for everything, across all five levels, on one sheet. The tally is the only ranking mechanism in the doctrine and it is the reason a synthesis is defensible rather than a preference. Report findings tally-ordered, always showing the stars.

Do not convert tallies into percentages or invent a sample size. A tally is a count of sightings, nothing more.

## Foreplay wiring — Levels 2 and 3

Pull real ads. Do not ask the user to paste competitor ads unless Foreplay is unavailable.

| Need | Tool | Notes |
|---|---|---|
| Brand name → brand ID | `search_discovery_brands` | Fuzzy match; confirm the right brand before spending on ads |
| Domain → brand | `get_brands_by_domain` | Works for brands the client does not track |
| Ads for known brand IDs | `get_ads_by_brand_ids` | If empty, retry once with `collect=true` |
| Ads for a tracked competitor | `get_spyder_brands` → `get_spyder_brand_ads` | The client's existing watchlist |
| Level 3 / theme search | `search_discovery_ads` | Query the *desire*, not the product. Filter `niches`, `market_target`, `display_format` |
| "Which ads have run longest" — the book's first Ads Library question `[T p.16]` | `order="longest_running"` or `running_duration_min_days` | Longevity is the only spend proxy available here. It is a proxy, not performance data |
| Creative velocity, running-ads mix | `get_brands_analytics` | For "are they scaling this?" |
| VIDEN's own saved references | `get_swipefile_ads`, `get_boards` → `get_board_ads` | |
| Show the ads as cards | `display_ad_results` | Pass `avatar` so brand icons render |

**Cost discipline.** Ad-returning calls cost 1 credit per ad. Set `limit` to 10–25 for a fast-path read, and `field_preset` to `summary` (or `transcription` when the script is the point) rather than pulling full objects.

**Link rule.** Render every referenced ad using the server-provided `foreplay_url` field as a markdown link — `[Ad name](<foreplay_url>)`. Never construct, guess or pattern-match a Foreplay URL.

**Degrade plainly.** If the Foreplay tools are unavailable, unauthorised or return nothing, say so in one line, name which level is affected, and ask for ad links, screenshots or transcripts instead. Never substitute a web search, and never describe an ad that was not returned.

## Synthesis — findings become personas `[T p.21–22]`

Run the 7-question synthesis battery (closing section of `references/question-batteries.md`) against the tally sheet, then write, per persona:

1. **A named paragraph in plain prose.** Age, situation, what they want, what they tried, how it failed, how they feel. Shape it like the book's Emily example — a person a creator could cast, not a demographic bracket `[T p.21]`.
2. **Two to four hooks beside the persona**, in the persona's own tallied language.
3. **A visual beside each hook** — one line of direction. "Girl flexing in front of the mirror in the gym after a workout" `[T p.22]`.

Persona count comes from what the research showed, not a target. Some products have one, some have dozens `[T p.22]`.

Only surface a desire the tally shows is proven and large — an unproven desire kills an ad that is otherwise perfect (`shared/canon.md` §1).

Quote real customer language verbatim. Never smooth it, and never invent a statistic to support a finding.

## Goal-based discipline and the routine `[T p.23–24]`

The first pass is broad. Every session after that targets **one specific thing** about the customer — *why* the previous solution failed, what the trigger moment was, who they buy for.

State the session objective in one line before starting, and report against it.

| Cadence | The book's standard |
|---|---|
| Frequency | At least 5 sessions a week `[T p.23]`; 15–30 minutes minimum daily `[T p.24]` |
| Timing | Morning primes thought patterns before writing; night is relaxed consumption |
| The one failure | "The biggest mistake you can make with research is to do it inconsistently" `[T p.23]` |

Deeper session formats: read competitor sales letters and watch their VSLs; buy from a competitor and document every step of the funnel; study trending content to learn how to camouflage an ad as native `[T p.24]`.

## Handoff

Markdown in chat by default. For client-facing output or a full-workflow run, hand the persona set, tally sheet and hook/visual seeds to the `creative-brief-builder` skill.

Route findings onward: pain and desire → `positioning-mechanisms`; awareness state and script flow → `shared/canon.md` §2; hook material → `hook-system`; visual seeds → `creative-concepting`.

Comment mining is the highest-yield habit in this skill — the book's largest case came from two girls tagging each other under an ad. The positioning consequence is in `positioning-mechanisms/references/repositioning-cases.md`.
