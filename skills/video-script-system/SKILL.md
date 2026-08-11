---
name: video-script-system
description: >
  This skill should be used when the user wants to write, rewrite, tighten, or diagnose a video ad
  script for Meta or paid social. Trigger phrases include "write a video script", "script this ad",
  "turn this hook into a script", "write me a UGC script", "rewrite this script", "audit this script",
  "score this script", "run a teardown on this script", "this script is flat", "cut this script down", "add visual direction", "make this script flow", "script for a
  talking-head ad", "30-second script", "why does this script feel boring", "reinforce the desire in
  this script", and "give me the shot list". Also use when a signed-off hook needs to become a
  producible script, or when an existing script needs a specific rewrite pass applied.
metadata:
  version: "0.1.0"
---

# Video Script System

The plugin's core production skill. A script is built in **one draft plus five rewrite passes** — each pass does exactly one job, and each is runnable on its own against an existing script.

Doctrine: Nick Theriot, *The Art of Creating Ads That Scale*, cited `[T p.N]`. Canon: `${CLAUDE_PLUGIN_ROOT}/shared/canon.md`.

## Before writing anything

Three inputs must exist. Missing any one of them produces a script that cannot be fixed by rewriting.

| Input | Where it comes from | If missing |
|---|---|---|
| A hook that passes the three golden rules | `hook-system` | Stop. Write the hook first. |
| Awareness stage → script flow | canon §2 | Ask one question: what has this market already tried? |
| One desire, one avatar | `positioning-mechanisms` | Stop. A script serving two avatars serves neither `[T p.69]`. |

Read the cached brand-context artefact if one exists. Do **not** trigger a full brand intake for a single script request — use what the user gave you and note the gap in one line.

## Fast path (default)

For "write me a script for X" — one pass, no reference loading beyond the flow:

1. Confirm hook + awareness stage + avatar (infer from what's given; state your inference in one line).
2. Pick the flow from canon §2.
3. Write the draft, then apply passes 2–6 **inline in a single response** rather than showing six versions.
4. Output: script with per-line visual direction, plus a one-line note on which desire-reinforcement moves you used.

Do not show the intermediate drafts unless asked. The user wants a script, not a lesson.

## Audit / diagnose path — "audit this script", "why is this flat"

**Load exactly one file: `references/diagnosis.md`.** It carries the 10-rung diagnostic ladder (read in order, stop at the first failure — fixing a lower rung while an upper one is broken wastes the reshoot), the sag-point procedure, the spend-tier case studies, and the failure patterns the ladder does not cover. Every rung already names the pass or the sibling skill that owns the fix, so **do not also load `rewrite-passes.md` or `craft-heuristics.md`** — reach for one of those only if the audit lands on a rung whose fix you then have to execute in the same turn.

## Deep path

When the user asks for the full treatment or a specific pass run visibly — one pass at a time, showing the diff and the reasoning. Load `references/rewrite-passes.md`.

## The six passes

Each pass has one job. Never combine them when running visibly — the discipline is the value `[T p.46]`.

| # | Pass | The one question it answers | Reference |
|---|---|---|---|
| 1 | **Draft** | What's the story? | `references/rewrite-passes.md` |
| 2 | **Reinforce Desire** | How else does the product deliver this? | `references/reinforce-desire.md` |
| 3 | **Descriptive Words** | Which words are doing no work? | `references/rewrite-passes.md` |
| 4 | **Cut the Fat** | Where am I bored? | `references/rewrite-passes.md` |
| 5 | **Flow** | Does it survive being read aloud? | `references/rewrite-passes.md` |
| 6 | **Visual Rewrite** | How do I visually articulate each line? | `references/rewrite-passes.md` |

Two rules that matter more than they look:

- **Pass 4 is allowed to delete what pass 2 added.** In the book's own worked example the author cuts both lines he had just added `[T p.58]`. Layering then cutting is the method, not a mistake.
- **Pass 5 requires reading it out loud.** "If you find spots where you stutter or are hard to read, that part needs to be rewritten" `[T p.59]`. When running this pass, read for stumble points explicitly rather than asserting it flows.

## Standing craft rules

Applied during every pass, not as a separate step. Full detail and worked before/after pairs in `references/craft-heuristics.md`.

| Rule | The test | Cite |
|---|---|---|
| **Focus** | One desire or problem, one avatar. People remember one thing. | `[T p.69]` |
| **Simple beats clever** | Clever writing makes people solve a puzzle. Cut it. | `[T p.72]` |
| **Every word justifies itself** | If it doesn't add selling power, remove it. | `[T p.58]` |
| **Emotional ↔ logical balance** | Alternate. Too much logic up front bores; too much emotion up front loses belief. | `[T p.67]` |
| **Bright side, not dark side** | State the pain once, then sell the new reality. Don't wallow. | `[T p.67–68]` |
| **Feature → benefit → desire** | Only surface benefits and features serving the *one* desire. | `[T p.71]` |
| **Repetition builds belief** | Show the product delivering, from multiple angles. | `[T p.52]` |
| **Length fits the message** | Complexity of product × stage of buying mindset. No fixed number. | `[T p.74]` |
| **Entertainment + selling power** | People scroll to escape. An ad with no entertainment gets swiped. | `[T p.39]` |

On length specifically: the book refuses to give a number, and 2026 evidence vindicates that. Kantar (5 Feb 2026) found 15-second cuts can carry full brand-building weight, while a 30-second cut pulled 1.4× higher active attention in a different context. Fit length to what the idea needs to land — never to a convention.

## Attention is re-winnable

Do not treat a weak second half as fatal. Kantar (29 Jul 2024, 40 ads, ARF Attention Validation Initiative) found **a product introduction at second 7 created new attention.** Diagnose and fix the sag; don't scrap the script.

Corollary: front-load *recognisable* cues rather than merely arresting ones. Amplified + VCCP Media (16 May 2025) found outcomes achievable in 1.5 seconds, with brand distinctiveness — not novelty — as the lever.

## Writing with AI

The book's own guidance, and it holds up `[T p.75]`. The failure mode is **not providing enough data**.

Supply: product, ICP, prior failed solutions *and why they failed*, positioning, awareness stage, and the hook patterns you want the structure to follow. Then treat the output as a **rough draft only** and run the manual passes on it.

Useful sub-prompts during rewriting `[T p.75]`: "What's a better word for X?" · "What's a more descriptive way to say X?" · "How can I cut this down?" · "How can I visually articulate this script?" · "As a high-level marketing expert, what am I missing?"

## The CTA

The most-neglected element — the author wrote this section of the book last, having nearly forgotten it `[T p.76]`.

**An effective CTA reminds people why to click, or gives them a reason to act now.** Never "click to buy now."

| Don't | Do |
|---|---|
| Click to buy now | Click below to get smooth, hair-free skin |
| Click to buy now | Click below to take advantage of our back-to-school special |
| Click below to get a quote | Click below to get protected today! |

## When you get stuck

Treat it as a puzzle, not a block `[T p.76]`. Write down each specific problem — "how do I transition this thought?", "how do I address this objection?", "how do I strengthen belief here?" — then solve them one at a time. For objection and belief problems specifically, hand to `belief-objection-engineering`.

## Handoffs

| Need | Skill |
|---|---|
| The hook isn't landing | `hook-system` |
| Format, casting, environment, shot design | `creative-concepting` |
| Objections, beliefs, urgency, high-AOV framing | `belief-objection-engineering` |
| Primary text, headline, link description | `ad-copy-qa` |
| Pre-launch check before it ships | `prelaunch-qa` |
| Branded script doc for editors | `creative-brief-builder` |

## Reference index — load one, or none

| The ask | Load this | Lines |
|---|---|---|
| "Write me a script for X" | **nothing** — the flow comes from canon §2, and the six passes plus the craft rules above are the standard | 0 |
| "Audit this script" · "why is this flat" | `references/diagnosis.md` — the 10-rung ladder, the sag point, the spend-tier case studies, the off-ladder failure patterns | 95 |
| Which flow, or the flow looks wrong | `references/script-flows.md` — the five flows with worked examples, selection detail and the wrong-flow symptom table | 97 |
| Running a pass visibly, or a named pass on someone else's script | `references/rewrite-passes.md` — passes 1, 3, 4, 5, 6 in detail with the full worked progression | 136 |
| Pass 2 specifically | `references/reinforce-desire.md` — the 15 ways to reinforce desire, how to choose and layer them | 72 |
| A craft rule is contested, or you want the before/after pair | `references/craft-heuristics.md` — emotional/logical, dark/bright, focus, feature-benefit-desire, clever/simple, length | 127 |
