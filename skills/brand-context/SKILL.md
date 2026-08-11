---
name: brand-context
description: This skill should be used when a VIDEN strategist is starting work on a brand and needs the cached context artefact that every other skill in this plugin reads — running the intake interview, researching the brand, or refreshing a context file that has gone stale. Trigger on "we're onboarding [brand]", "run brand intake", "build brand context for [brand]", "new client — [brand]", "set me up on [brand]", "refresh the context doc for [brand]", "what do we know about [brand]", or "update the brand context — their positioning changed". Do not trigger this for a single atomic request such as writing a few hooks or checking one competitor; those skills work from whatever the user supplied.
metadata:
  version: "0.1.0"
---

# Brand Context

Produces one cached artefact — `brand-context-[brand].md` — that every other skill in this plugin reads instead of re-asking the same questions.

It answers *what is true about this brand*. `market-research` answers *what is true about this market*. Neither duplicates the other.

## The latency rule — read this first

**This skill runs for a full-workflow start or when explicitly asked. It must never gate an atomic request.**

| Situation | Correct behaviour |
|---|---|
| "Write me five hooks for X" and no context file exists | The hook skill proceeds on what the user supplied, and notes the gap in **one line**: "No cached context for [brand] — working from your brief. Run `brand-context` when you want this persisted." |
| "Onboard [brand]" / "run brand intake" | Run the deep path |
| Full-workflow start (research → positioning → concepts → brief) | Run the deep path first, once |
| A context file exists | Read it. Do not re-interview |
| A context file exists but is thin in the one area the current task needs | Ask one targeted question. Do not re-run intake |

Never ask a strategist to complete an interview before answering a small question. A missing context file is a noted gap, never a blocker.

## Fast path vs deep path

**Default to fast.**

| Path | Trigger | Do this | Output |
|---|---|---|---|
| **Fast** — one pass | A context file exists, or the ask is "what do we know about [brand]?" | Read the cached file and answer from it. If it does not exist, say so in one line and answer from what the user gave you | Answer in chat, plus the one-line gap note |
| **Deep** — full build | Onboarding, an explicit request, or a full-workflow start | Phase 1 intake → Phase 2 research → Phase 3 build → Phase 4 confirm | The saved `brand-context-[brand].md`, presented in chat |

## Reference index

| Load | When |
|---|---|
| `references/intake-and-research.md` | Running the deep path. Section 1 is the intake block to send verbatim; section 2 is the 9-point research checklist with search operators |
| `references/context-template.md` | Phase 3, when writing the file. The fixed section order and the confirmed-vs-inferred convention |

Do not load either on the fast path.

## Phase 1 — Intake

Send the intake block from `references/intake-and-research.md` §1 **as one message**. Never drip the questions one at a time; a strategist answers seven grouped questions in a single reply and resents seven turns.

Then confirm and move on, in one line: "Got it. I'll research the rest and come back with the full context doc."

Accept partial answers. Anything unanswered becomes a research target, and if it survives research it becomes a labelled gap in the file.

## Phase 2 — Research

Work the 9-point checklist in `references/intake-and-research.md` §2. Each point carries its own search-operator guidance.

**Scope of outward reach.** This is the only skill in the plugin that fetches from the web, it happens only on the deep path, and it is scoped to brand facts: the brand's own properties, its named competitors, its reviews and its press.

**Never** search at runtime for doctrine, benchmarks, platform rules, ad specs or policy text. Those are baked in and timestamped in `shared/evidence.md`, and a fresher-looking search result does not override them.

**Live creative.** Pull the brand's own running ads through Foreplay rather than describing them from memory — `get_brands_by_domain` on the brand URL, then `get_ads_by_brand_ids`. Render any ad referenced in chat using the server-provided `foreplay_url` field as a markdown link; never construct a URL. If Foreplay is unavailable, say so in one line and record "existing creative: not retrieved" in the file rather than inferring it.

**Market-level research is out of scope here.** Competitor ad teardowns, the hate list, VOC extraction and personas belong to `market-research` and `positioning-mechanisms`. This file records who the competitors *are*, not what their creative does.

## Phase 3 — Build the file

Write to `references/context-template.md`'s fixed section order. Non-negotiable while writing:

- **Label every claim confirmed or inferred.** Confirmed = stated explicitly somewhere retrievable. Inferred = a reasonable read from category and signals. Anything else does not go in the file.
- **Quote the brand's own language** for differentiation and voice. A paraphrase of a positioning claim is a new positioning claim.
- **No invented statistics**, ever, including plausible-looking market sizes and customer counts (`shared/canon.md` §8).
- **State gaps as gaps.** An honest "could not verify their manufacturing claim" is worth more than a confident guess, because downstream skills treat this file as settled.
- Keep it short enough to be read in full by another skill. Detail that only matters once belongs in the conversation, not the artefact.

Save as `brand-context-[brand].md` in the working directory, using a lowercase hyphenated brand slug.

## Phase 4 — Confirm

Present the file, call out every labelled gap and every inference explicitly, then ask exactly one closing question:

> "Anything here look off, or anything important missing? Once you confirm, this is the working context for all creative on this brand."

Do not start downstream work inside the same turn as the confirmation request.

## Cache mechanics

| Question | Answer |
|---|---|
| Where does it live? | `brand-context-[brand].md` in the working directory |
| Who reads it? | Every other skill in this plugin, at the start of a deep-path run |
| How is a stale file detected? | The `Generated` date in the header, plus any user statement that the positioning, catalogue or constraints changed |
| Refresh or rebuild? | Refresh the changed sections and update the date. Rebuild only if the brand repositioned — see `positioning-mechanisms` |
| Does an atomic request check for it? | One cheap check, then proceed either way. Never block |

When a downstream skill contradicts the file — research surfaces a persona the file does not have, or a constraint turns out to be wrong — say so in one line, use the newer finding, and offer to update the file. Do not silently diverge, and do not silently overwrite.

## Handoff

Markdown in chat by default. For a client-facing version of this document, hand off to `creative-brief-builder`.

Onward from a completed file: `market-research` for the market and the personas, `positioning-mechanisms` for the anchor, mechanism and angles. Both read the file rather than re-asking.

Where the file records a constraint touching a Special Ad Category, health, financial products or a policy-sensitive claim shape, flag it in the Creative Constraints table and route the ruling to a human — `shared/evidence.md` sets out why this plugin does not clear copy as compliant.
