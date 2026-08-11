# VIDEN Ads Engine

The VIDEN Growth creative system for Meta paid social. One plugin covering the whole arc — market research → positioning → hooks → concepts → scripts → copy → pre-launch QA → post-launch review → iteration → troubleshooting.

**Doctrine:** Nick Theriot, *The Art of Creating Ads That Scale* (2024), read cover to cover and distilled into VIDEN-authored rules with page attribution (`[T p.N]`). Merged with our creative libraries and pressure-tested against 2026 evidence. Nothing from the book is reproduced verbatim.

## Design principles

**Every skill stands alone.** Ask for hooks, get hooks. Ask why a campaign is dying, get a diagnosis. Nothing forces you through the pipeline, and no skill gates a small request on a full brand intake.

**Fast by default.** Every skill declares a fast path (the common atomic ask, one pass, minimal loading) and a deep path (the full treatment, on request). No skill runs a web search at runtime — all doctrine, benchmarks and platform rules are baked in and timestamped.

**Index first, shard second.** Every big library is split into a dense selection index plus entry shards, and the index is designed to answer the common ask on its own. `hook-system/references/tactics.md` is a 113-line index over all 47 tactic entries (job, awareness fit, primary trigger, example shape) with the full entries in four alphabetical shards. `creative-concepting/references/visual-formats.md` is a 72-line index over all 46 formats (medium, fit, pick-it-when, mechanic, constraint flag) with the entries in three medium shards. Every SKILL.md carries a reference index with the line cost of each file and an explicit "load nothing" row for the fast path. The invariant: **a new library entry needs two edits — the shard and its index row.** An entry with no index row is invisible.

**Scripts are executed, never read.** `creative-brief-builder/scripts/build_brief.py` is 874 lines and is marked EXECUTE-ONLY in its SKILL.md; its input contract lives in `references/brief-templates.md` and its style values in `references/docx-style-spec.md`, so nothing ever needs to read the code to drive it.

**One canonical definition per concept.** `shared/canon.md` owns the shared models; no skill restates them. That's what stops fourteen skills contradicting each other.

**Self-contained.** Nothing here depends on a standalone account skill. It keeps working if those change or disappear.

## Skills

| Skill | Fires when | Connectors |
|---|---|---|
| **ads-that-scale** | Broad or multi-stage requests; "build me some ads"; how the system works. Routes to the rest. | — |
| **brand-context** | New client, brand facts, voice, catalogue, constraints. Writes a cached artefact everything else reads. | web (brand facts only) |
| **market-research** | The 5-level research ladder, competitor and indirect-competitor ads, VOC from reviews, persona synthesis. | Foreplay |
| **positioning-mechanisms** | Mechanism theory, identity marketing, angles, personas, depositioning, Special Ad Category doctrine. | — |
| **hook-system** | Hooks, opening lines, scroll-stoppers. The most-used skill. | — |
| **creative-concepting** | Photo vs video, 46 visual formats, 8 mechanics, casting, environments. | — |
| **video-script-system** | Write, rewrite, tighten or diagnose a script. Six passes, each runnable alone. | — |
| **belief-objection-engineering** | Objections, beliefs, buy-now urgency, high-AOV framing. | — |
| **ad-copy-qa** | Primary text, headline, link description, copy QA, post-click alignment. | — |
| **marketing-psychology** | 72 named mental models. The single cited source for psychological principles. | — |
| **prelaunch-qa** | Check a creative before it ships. Pass / needs-changes verdict. | — |
| **testing-and-iteration** | Hypotheses, the creative roadmap, post-launch review, winner iteration, significance. | Meta Ads, BigQuery |
| **campaign-troubleshooting** | "Why is this dying." Six-cause tree, cost-ordered. | Meta Ads, BigQuery |
| **creative-brief-builder** | The shared output layer. Markdown by default, branded `.docx` on request. | — |

## How the pieces compose

```
brand-context → market-research → positioning-mechanisms → hook-system
   → creative-concepting → video-script-system → ad-copy-qa
   → prelaunch-qa → [launch] → testing-and-iteration
                                      ↓ (when it's not working)
                              campaign-troubleshooting
```

Three gates prevent expensive work on a broken premise: **desire is proven and large** before hooks, **one desire one avatar** before scripting, **the page continues the thought** before launching.

## Setup

Three connectors are declared in `.mcp.json`. The plugin works without them — skills degrade by saying so plainly and asking for the inputs. They never fabricate data.

| Connector | Used for |
|---|---|
| **Foreplay** | Real competitor and indirect-competitor ads during research, instead of asking you to paste them |
| **Meta Ads** | Live performance for post-launch review, winner detection and troubleshooting |
| **BigQuery** | Ground-truth business KPIs, to separate a creative problem from an offer, margin or funnel problem |

## Outputs

Markdown in chat is the default for atomic asks, because `.docx` generation costs real seconds. The branded creative brief is offered, not assumed.

The branded `.docx` — Urbanist, navy table headers, no H2 rules, no logo — is the default for full-workflow runs and anything client-facing. `creative-brief-builder/scripts/build_brief.py` is a working python-docx builder; it's the first properly factored one at VIDEN, replacing logic that was duplicated inline across eight client report skills. **It is run, never read** — see the execute-only rule in that skill. XLSX (concept × angle × hook × format × awareness stage, plus a test log) and Notion are available on request.

## Where the book was corrected

Four calls, with reasoning and citations in `shared/evidence.md`:

1. **The 3-second rule** survives as pacing craft, not as a mechanism. Meta is retiring 3-second viewer metrics; the evidenced attention window is 1.5–2.5s; and Kantar found a product intro at second 7 created new attention — so **attention is re-winnable** and a weak second half is fixable rather than fatal.
2. **6–12 creatives a week** is replaced by a hypothesis-quality gate. Motion's 578,750-creative dataset shows top-quartile accounts launching ~3.0/week against a 3.3 median, at a 3.85% hit rate. The book's own quality caveat was the better instinct.
3. **CPA as the winner test** becomes two lanes — attribution-independent diagnostics for creative decisions, attributed metrics with model and window stated for scale decisions. Meta ships two attribution models that disagree by 24%.
4. **Fatigue** splits into message staleness (real) and auction effects (not fatigue — Meta's price per ad rose 12% YoY two quarters running). A concurrent control is required before declaring fatigue, and no fixed refresh intervals are given.

## Honest gaps

Three first-party sources were unreachable during research (robots.txt, JS-only rendering, paywall). Consequently **ad specs, safe zones, and most Meta policy rule text are not asserted** — the plugin flags risk and points at the source URL instead of stating a rule, and platform character limits are labelled house defaults rather than documentation. `MAINTENANCE.md` lists exactly which URLs someone needs to open in a browser to close these.

The plugin will not clear copy as policy-compliant. That's deliberate.

## Deliberately out of scope

Meta's Advantage+ creative enhancements — the 23 features that can alter a delivered asset. House ruling: this plugin produces great creative; it doesn't manage platform post-processing.

## Ethics

The book opens with it, so this does too: everything here can be used to manipulate people. Use it only for good `[T p.7]`. No invented statistics in generated copy, ever — including in the book's own examples, which model this badly.

---
`shared/canon.md` — shared definitions · `shared/evidence.md` — 2026 evidence and the never-state list · `MAINTENANCE.md` — what rots and when
