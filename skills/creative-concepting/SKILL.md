---
name: creative-concepting
description: This skill should be used when an approved messaging angle and hook have to become a producible concept — photo or video, which visual format, which creative mechanic, who is on camera and where it is shot. Trigger on "what format should this be", "should this be a photo or a video", "turn this angle into 3 concepts", "concept this hook", "how do we visually articulate this", "what mechanic is this ad using", "what's the reframe mechanic again", "remind me what the Trojan Horse mechanic is", "which mechanic should this concept run", "who should we cast for this", "where should we film this", "can we run this with an AI avatar", or any request to spec a shoot from an angle that is already signed off. Not for writing the hook itself (hook-system) or the full script (video-script-system).
metadata:
  version: "0.1.0"
---

# Creative Concepting

Convert one angle + one hook into a concept a shooter, designer or editor can execute without asking a follow-up question.

Definitions are not repeated here. Load `shared/canon.md` only when a request turns on the four visual types (§4), the awareness-stage → script-flow mapping (§2), or the format / mechanic / tactic / mechanism glossary (§5) — the medium test and the mechanic table below are self-contained, so a plain format or mechanic question needs no canon load. Load `shared/evidence.md` only to justify a 2026 call.

**Never run a web search.** Everything needed is in this skill's `references/`.

## Fast path — default

For a single atomic ask ("what format should this be?", "photo or video?", "what's the reframe mechanic?"), answer in one pass:

1. Run the medium test below. One table lookup, nothing loaded.
2. **Name the mechanic** from the eight-row table in Step 5 below. Nothing loaded. Open `references/creative-mechanics.md` only for the structure beats, the worked examples, or when two mechanics are being layered.
3. **Name the format** from the selection table in `references/visual-formats.md` — that file is a 72-line index carrying medium, awareness fit, pick-it-when and mechanic pairing for all 46. **Load the index only.** Open one medium shard (`formats-static.md` · `formats-video.md` · `formats-either.md`) only when you need a format's full definition, production note or constraint text.
4. Stop. Do not produce a full brief unless asked.

## Deep path — full concept set

Run all six steps below, produce 2–3 concepts against one angle, and hand to `creative-brief-builder`. Load the format index, **one** medium shard, `creative-mechanics.md` and `actors-and-environments.md`. Use this only when the ask is a shoot brief, a concept round, or a new-concept slot on the iteration ladder (canon §6).

---

## Step 1 — Photo or video

The decision is not budget or preference. It is: **what has to be *shown* for this to be believed?** `[T p.40]` Apply canon §4's belief rule — people believe what they see, not what they hear `[T p.40, p.77]` — then look up the medium.

| What must be believed | Medium | Why |
|---|---|---|
| A state exists — the desire achieved, the problem, the product | Photo | One frame carries a state |
| The product survives, withstands or endures something | Video | The proof is the event, not the claim |
| A result accumulates over time | Video | Duration is the argument |
| The product is better on a spec the market already understands | Photo | It is a comparison of states |
| The mechanism is non-obvious and needs a sequence | Video | Steps cannot be stacked in one frame |
| Someone's situation changed and they will say so | Video | Needs a face and a voice |

**Worked example `[T p.40]`.** A construction worker needs a phone case that survives job sites. Option A: a photo with bold text, *"The world's toughest phone case."* Option B: a 10-second video of the case falling off a 100-foot building, phone still working. B wins — toughness is an event, and A only asserts it. Generalise: if the belief hinges on a process, a duration or an event, shoot video; if it hinges on a state, photo carries it at a fraction of the cost.

## Step 2 — Visually articulate the hook

Ask the core question of the whole craft, per line: **"How can I visually articulate this?"** `[T p.41, p.60]`

Then interrogate the hook's *implied* benefit from the consumer's point of view: what does that benefit look like once they have it, and how do they receive it? `[T p.41]` Write every candidate articulation, then **choose the most specific** — specificity raises the quality of the audience that stops `[T p.41]`.

Worked example `[T p.41]`. Hook: *"Facebook Ads That Convert."* Candidates: (1) new ads taking real spend at a good cost per purchase inside the ad account, (2) the channel's reported ROAS climbing, (3) total store revenue climbing. All three are true. (1) is the most specific to the ideal customer, so (1) gets shot.

## Step 3 — Build the photo

Every photo ad is one of canon §4's four visual types. Choose one per asset — never two.

**Photo is the foundation skill.** *"Video is the same as photo but done multiple times for a single creative"* `[T p.43]`, and every scene inside a video is one of the same four types `[T p.45]`. A video brief is therefore N photo briefs in sequence. Get the photo brief right before scripting video.

- **Production methods** `[T p.43]`: studio photographer; graphic design; shot on an iPhone; AI-generated (see AI production path).
- **Layouts seen working** `[T p.43]`: split screen, two images; split screen, one image plus a flat background carrying the text; image with the hook on it; image with the hook plus three benefits called out.
- **Script convention** `[T p.43]`: hook above the image; **about half the time**, three benefits called out on the image itself. Deliver a photo brief as hook line + visual type + layout + the three benefit lines if used.

## Step 4 — Build the video

Four video types `[T p.44–45]`. B-roll is filler footage with nobody speaking to camera, cut against the talking head to give the story context `[T p.44]`.

| Type | Use it when |
|---|---|
| B-roll + music + captions | No usable talent, or the sell is lifestyle and uniqueness. The book's default for clothing brands — actor and environment do the work `[T p.45]` |
| B-roll + voice-over + captions | Footage already exists on file and no new shoot is possible `[T p.45]` |
| Actor talking to camera | Storytelling, **especially emotional products** `[T p.45]` |
| Actor talking to camera + b-roll | Most polished; use when claims must be *shown* while they are said `[T p.45]` |

Then assign every scene one of canon §4's four types and one visual direction per line — that is the handoff `video-script-system` expects.

## Step 5 — Choose the mechanic

Pick the cognitive move the whole concept makes, not the frame of the opening line (canon §5 draws that line). **Eight mechanics, and nothing else is one.** This table answers "which mechanic" and "what is mechanic X" without loading anything:

| To make the viewer… | Mechanic | The move, in one line |
|---|---|---|
| Conclude the truth themselves | **Implied Answer** | The hook asks a plausible question; the visuals answer it silently and nobody states the connection |
| Believe a result because someone else noticed | **Social Witness** | A third party clocks the change unprompted — a compliment, a double-take — instead of a claim |
| Drop the ad filter entirely | **Overheard Conversation** | Framed as something you were not meant to see: a thread, a DM, two friends talking |
| Think "I never looked at it that way" | **Reframe** | Validate the belief they hold, show them doing everything right by it, then flip what the real problem was |
| Recognise a competitor you never named | **Borrowed Enemy** | Describe the problem so specifically that only one rival fits, and never name them |
| Get invested before they register an ad | **Trojan Horse** | Real education, entertainment or story; the product enters in the last fifth as part of the resolution |
| Feel the gap without being told what to think | **Contrast Without Comment** | Two realities side by side, shot neutrally, with no voice-over verdict |
| Attach the product to something already wanted | **This and a…** | Pair the product with something aspirational and never explain why they belong together |

Full entries — why each works, awareness fit, the structure beats, the worked examples, the four layering pairings and the closed-list protocol — are in `references/creative-mechanics.md`. One **primary** plus one **secondary**, never three.

## Step 6 — Cast the actor and pick the environment

These are performance levers, not logistics `[T p.61–64]`. Three archetypes to test: people the ICP is **attracted to**, people the ICP **wants to look like**, people the ICP **looks like** `[T p.63–64]`. Environment sets perceived value before the price is seen and signals authority `[T p.61]`. Cases, the casting test, and the environment checklist: `references/actors-and-environments.md`.

---

## AI production path

VIDEN uses AI avatars proactively for many clients. This is a supported path — calibrate it, do not prohibit it.

**The operative variable is visibility, not AI-ness.** Kantar (4 Nov 2025, hundreds of LINK ads plus facial coding): seamlessly integrated AI put over 40% of ads in the top tier for branded cut-through, while obvious AI performed worse. Kantar LINK (26 Mar 2026): AI-generated ads average the 54th percentile against 65th for non-AI. Read together: **treat a visible AI artefact as a defect to fix, not a style choice.**

Artefact checklist before delivery — hands and fingers, teeth, blink cadence, lip-sync drift, warped text or logos, hair edges, background morphing between cuts, lighting that does not match the plate, prop continuity. Any hit is a re-render, not a caveat.

**Gen Z flag.** IAB + Sonata Insights (15 Jan 2026; 505 US Gen Z/Millennial respondents plus 104 execs): negative sentiment toward AI ads 37%, up 12 points from 2024, with Gen Z at 39% negative against Millennials at 20%. On a Gen Z-skewed audience, flag AI avatar use for a human call before shipping.

For EU-targeted campaigns using a synthetic human likeness, and for anything in a special ad category, stop and read `shared/evidence.md` — labelling obligations are live there and are not a creative decision.

## Reference index — the whole load budget for this skill

| Need | Load | Lines |
|---|---|---|
| Photo or video · which mechanic · what mechanic X is | **nothing** — Steps 1 and 5 above are complete | 0 |
| Which format, for any medium | `references/visual-formats.md` — the index: 46 rows of medium + fit + pick-it-when + mechanic + a constraint flag | 72 |
| One format's full definition, production note or constraint | **one** medium shard: `references/formats-static.md` (12) · `references/formats-video.md` (22) · `references/formats-either.md` (12) | 93–165 |
| A mechanic's structure beats, worked examples, layering pairings, or the add-a-mechanic protocol | `references/creative-mechanics.md` | 193 |
| Casting, environment, the book's cases | `references/actors-and-environments.md` | 84 |

Never load two format shards for one concept, and never load the mechanics file to answer "what is mechanic X" — Step 5 has it.

## Platform adaptation notes

Meta is the default. Only two things genuinely differ:

- **TikTok / Reels / Shorts:** platform UI chrome eats the lower third and the right edge. Keep hook text high and central. Safe-zone margins are **not verified** in this plugin (`shared/evidence.md`) — have a human check placement in the platform preview rather than trusting a remembered number.
- **Trend format has a live shelf life.** It only works while the sound or format is in active circulation, so it cannot be briefed on a normal production lead time.

## Handoffs

Hook in from `hook-system`. Angle, persona and language in from `market-research`; mechanism from `positioning-mechanisms`. Objection and belief work to `belief-objection-engineering`. Line-by-line script to `video-script-system`. Assembled brief to `creative-brief-builder`. Final gate at `prelaunch-qa`.
