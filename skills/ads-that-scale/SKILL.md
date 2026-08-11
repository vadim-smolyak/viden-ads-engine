---
name: ads-that-scale
description: >
  This skill should be used when the user wants to run the full creative process end to end, does not
  know which part of the system they need, or asks a broad question about building ads that scale.
  Trigger phrases include "build me some ads", "I need new creative for", "run the full creative
  process", "take this product through the full process", "where do I start with this client", "we
  need a new creative direction", "run the whole engine on this brand", and "use the ads engine".
  Also use when a request spans several stages and needs routing, or when someone asks how the plugin
  works. Do NOT use for an atomic ask that names its own stage — hooks, a format, a mechanic, a
  script, copy, a QA verdict, a post-launch read, a brief doc and a "why is this dying" diagnosis
  each have their own skill and should be reached directly. "What should we test next" is
  testing-and-iteration; turning finished work into a document is creative-brief-builder.
metadata:
  version: "0.1.0"
---

# Ads That Scale — router and full workflow

The VIDEN creative system for Meta paid social, built on Nick Theriot's *The Art of Creating Ads That Scale* (cited `[T p.N]`), merged with our libraries and verified against 2026 evidence.

**Route first, don't run the pipeline by default.** Most requests are atomic and want one skill, answered in one pass. Only run the full workflow when the user asks for it or when the work genuinely spans stages.

**If this file was loaded to route an atomic request, that load was already waste.** Every specialist's description sits in context permanently and names its own trigger phrases — "write me hooks", "what format should this be", "what's the reframe mechanic", "audit this script", "review this primary text and headline", "check this creative before launch", "did this ad win", "why is this campaign dying" all reach their skill directly. The table below is the fallback for a genuinely ambiguous or multi-stage ask, not the front door. **Never load this file and a specialist for one atomic request.**

## Routing table

| What they're asking for | Skill |
|---|---|
| Market/competitor/customer research, VOC from reviews | `market-research` |
| Positioning, mechanism, identity, angles, personas | `positioning-mechanisms` |
| Hooks, opening lines, scroll-stoppers | `hook-system` |
| Format, mechanic, casting, environment, photo vs video | `creative-concepting` |
| Video script — write, rewrite, tighten, add visual direction | `video-script-system` |
| Objections, beliefs, urgency, high-AOV framing | `belief-objection-engineering` |
| Primary text, headline, link description, copy QA, post-click | `ad-copy-qa` |
| A psychological principle or mental model | `marketing-psychology` |
| Check a creative before it ships | `prelaunch-qa` |
| Did it win, what next, hypothesis, roadmap, iteration | `testing-and-iteration` |
| "Why is this dying / not working" | `campaign-troubleshooting` |
| Brand facts, voice, catalogue, constraints | `brand-context` |
| Turn any of the above into a branded doc | `creative-brief-builder` |

Ambiguous request → pick the most likely skill and say which you picked in one line. Don't interrogate.

## The full workflow

Run only on request. Nine stages; each is a skill that also works alone.

```
brand-context → market-research → positioning-mechanisms → hook-system
   → creative-concepting → video-script-system → ad-copy-qa
   → prelaunch-qa → [launch] → testing-and-iteration
```

Three gates that stop expensive work happening on a broken premise:

| Gate | Before | Test |
|---|---|---|
| **Desire is proven and large** | Writing hooks | Did research show many people wanting this, in their own words? A perfect hook on an unproven desire cannot scale `[T p.65]` |
| **One desire, one avatar** | Scripting | Can you name both in one sentence? `[T p.69]` |
| **Page continues the thought** | Launching | Would a prospect land and think "what did I end up at?" `[T p.93]` |

Deliver interim output at every stage — never disappear for the whole pipeline. Default to markdown in chat; offer the branded doc rather than assuming it.

## Operating rules

**Read the cached brand context if it exists. Never gate a small ask on brand intake.** If context is missing, use what's given and note the gap in one line.

**Never run a web search for doctrine, benchmarks, specs or policy.** All of it is baked in and timestamped. `shared/evidence.md` is the authority even when a fresher-looking search result disagrees. Brand fact-gathering is the one exception, and it belongs to `brand-context`.

**Never invent a statistic.** Not in copy, not in a brief, not in a rationale. `shared/evidence.md` lists the numbers that circulate without any traceable source — including "the hook is 80% of the ad" and every hook-rate benchmark. If a number can't be sourced, say it's unavailable.

**Connectors, and how to fail well.** Foreplay for competitor and swipe research; Meta Ads for performance reads; BigQuery for ground-truth business KPIs. Batch and scope every call — explicit fields, tight dates, row caps. One well-formed query, never five exploratory ones. If a connector is unavailable, say so plainly and ask for the inputs. Never fabricate performance data.

**Flag policy risk, never adjudicate it.** Name the risk, give the specific policy URL, say it needs a human read. Never clear copy as compliant.

**The ethics line, from the book's own opening page.** Everything here can be used to manipulate people. Use it only for good `[T p.7]`.

## What this system believes

Compressed doctrine. Full canon: `${CLAUDE_PLUGIN_ROOT}/shared/canon.md`.

- **Research is the work; creativity is assembly.** "90% of great advertising is put together like a lego set. Market research is where you get your bricks" `[T p.12]`.
- **You cannot create desire — only call it out and channel it** `[T p.25]`.
- **How many solutions have they already tried?** The single question that most changes what the ad must say `[T p.25]`.
- **A hook must call out the audience, imply a benefit, and drive curiosity** `[T p.32]`. All three, every time.
- **Text creates the visual, so start with the text** `[T p.32]`.
- **People believe what they see, not what they hear** `[T p.40]`.
- **One desire, one avatar. People remember one thing** `[T p.69]`.
- **Every word justifies itself in the sales process** `[T p.58]`.
- **Simple beats clever, always** `[T p.72]`.
- **Desire has a clock.** Check calendar and fulfilment before blaming creative `[T p.38]`.
- **Every test carries a written hypothesis, logged with winner or loser** `[T p.95]`.

## Where the book was wrong, and what we do instead

Four corrections. Reasoning and citations in `shared/evidence.md`.

| Book | Our position |
|---|---|
| New visuals every 3 seconds, implying a 3-second window `[T p.77]` | Keep as pacing **craft**, drop the mechanism claim. Attention is re-winnable — Kantar (29 Jul 2024) found a product intro at second 7 created new attention. |
| 6–12 new creatives per week `[T p.95]` | Hypothesis-quality gate instead of a volume target. Motion's 578,750-creative dataset: top-quartile accounts launch ~3.0/week against a 3.3 median, 3.85% hit rate. |
| An ad wins if it lowers CPA `[T p.88]` | Keep the strategic definition — it wins if the account can spend more, profitably. But two lanes: attribution-independent diagnostics for creative decisions, attributed metrics with model and window stated for scale decisions. Meta ships two models 24% apart. |
| Repetition burns the account (fatigue implied) `[T p.86]` | Separate **message staleness** (real, and the book's actual finding) from **auction effects** (rising CPM and frequency are not fatigue — Meta's price per ad rose 12% YoY two quarters running). Require a concurrent control before declaring fatigue. No fixed refresh intervals. |

## Deliberately out of scope

Meta's Advantage+ creative enhancements — the 23 features that can alter a delivered asset. House ruling: this plugin's job is producing great creative, not managing platform post-processing. Recorded in `shared/evidence.md` so a future reader knows it was a decision, not an oversight.
