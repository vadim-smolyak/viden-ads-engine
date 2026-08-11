---
name: hook-system
description: This skill should be used when a VIDEN strategist or copywriter needs opening lines for paid social — writing a hook set, choosing a tactic, diagnosing a hook that is not converting, or building a hook matrix off an approved angle. Trigger on "write me hooks for", "give me 20 hooks", "hook ideas", "scroll stoppers", "opening lines", "I need hooks for this ad", "hooks by tactic", "give me 3 contrarian hooks", "TikTok hooks", "Reels hooks", "hooks for a static", "primary text hook", "why isn't this hook working", "rewrite this hook", "score these hooks", "hooks for each awareness stage", "more variations of this winning hook", "seasonal hooks for [holiday]", or any request for the first line of a creative. Not for the full script (video-script-system), the visual concept (creative-concepting), or what the product stands for (positioning-mechanisms).
metadata:
  version: "0.1.0"
---

# Hook System

Write the first line. The hook's only job is to stop the right person from scrolling `[T p.32–33]`, and it does it by latching onto the conversation already running in their head `[T p.33]`.

Definitions are not repeated here. `shared/canon.md` §1 is the pass/fail gate, §3 is the four-altitude stack this skill implements, §2 is awareness stage → script flow, §5 resolves the terms that collide.

**Load nothing by default.** The fast path below is self-contained: the gate notation, the two pre-hook gates and the eight trigger names are all inline. Load `shared/canon.md` only when a request turns on §2's stage→flow mapping or §5's term boundaries; load `shared/evidence.md` only to justify a 2026 call. **Never run a web search.**

## The two pre-hook gates — check before writing

Canon §1 puts two gates outside the hook. Both are cheap, both fail silently, and craft cannot rescue either.

1. **Is the desire proven and large?** "If it's not a proven desire across the marketplace or large enough, it will not scale" `[T p.65]`. The book's $1,000 ad hit all three golden rules on "romanticising your life" and went nowhere.
2. **Is the audience unambiguous?** The $10,000 ad named "people who want a date night this weekend" and showed a woman alone `[T p.66]`.

If a gate is doubtful, say so in **one line** and write anyway — then flag which gate to confirm. Never block a hook request on it, and never send the user to another skill first.

## The scoring gate — every hook, every time

Score each hook against canon §1's three golden rules using this notation, appended to the line:

`[aud ✓ · ben ✓ · cur ✓]` — **aud** calls out the ideal audience · **ben** implies a benefit · **cur** drives curiosity

Any `✗` means rewrite before it reaches the user. If a hook ships with a `✗` it is because the user asked to see the failure — label why. This is the one thing that is never skipped, on either path. Tactic and trigger names stay **out** of the output unless the user asks for the breakdown; the score stays in.

## Fast path — the default

Most requests are "write me N hooks for X". One pass, no clarifying questions if the brief is workable, no connector calls.

1. **Take the brief as given.** Product, pain or desire, persona, awareness stage, static or video, count. Missing awareness stage → infer it from what they have tried before `[T p.25]` and say which you assumed in one line.
2. **Brand context:** if a cached `brand-context-[brand].md` exists, read it. If not, work from what the user supplied and note the gap in one line — *"No cached context for [brand] — working from your brief."* Do not run `brand-context`.
3. **Run the two gates.** One line if either is doubtful.
4. **Write the set.** Vary the trigger across it — ten hooks on one trigger is one hook written ten times. Spread across at least four of the eight. **The eight, inline, so nothing has to be loaded to do this:**

   | To… | Fire |
   |---|---|
   | Break autopilot | **Pattern Interrupt** |
   | Make them self-select | **Identity Call-Out** |
   | Make them feel understood | **Pain Agitation** |
   | Open a loop | **Curiosity Gap** |
   | Borrow trust fast | **Social Proof / Credibility** |
   | Flip a belief they hold | **Contrarian / Myth-Busting** |
   | Show what is possible | **Aspiration / Desire** |
   | Make waiting expensive | **Urgency / Stakes** |

   Full entries — what each fires, when to use it, which tactics execute it, the cautions, and the trigger-by-awareness-stage pairings — are in `references/triggers.md`. Not needed to write a set.
5. **Score every line.** Rewrite any `✗`.
6. **Stop.** No matrix, no tactic labels, no process narration.

**Load at most one reference, and only when the ask needs it — see the index below.** A plain hook set of any count loads **nothing**. If two references seem needed, this is a deep-path request: run the deep path and say so in one line, don't stop to ask.

## Deep path — the full process

For a hook workshop, a new concept round, a set built off a fresh angle, or a diagnosis. **The process lives in `references/writing-process.md` and is not restated here** — load it and run Steps 1–7 (three inputs `[T p.33]`; three positioning drafts `[T p.34]`; escalate one claim five ways `[T p.35]`; score against six `[T p.35]`; volume discipline `[T p.36]`; feed the swipe file `[T p.36–37]`; check the calendar `[T p.38]`).

The one thing that file does not carry is the presentation grid. Build it as **tactic × trigger × voice pattern**, one column per axis, one row per hook:

| Hook | Tactic | Trigger | Pattern | Score |
|---|---|---|---|---|

Fill deliberately, not exhaustively: a tactic already covered by another row adds nothing. Coverage of the library is not a goal. Then hand off — chosen hooks → `creative-concepting` for the visual, `video-script-system` for the body.

## Reference index — the whole load budget for this skill

| The ask | Load (one only) | What it holds · lines |
|---|---|---|
| Plain hook set, any count | **nothing** | the fast path above is complete |
| "Hooks by tactic" · "3 contrarian hooks" · "what tactic is this" | `references/tactics.md` | **Index only** — all 47 entries in two tables (Set A 34, Set B 13 claim patterns `[T p.37–38]`) with job, fit, primary trigger and example shape, plus the 13-row duplicate mapping and the repair log. Enough to write the set on its own · 113 |
| A tactic's exact *Is / Not* boundary, book variant or caution | **one** alphabetical shard — `references/tactics-a-c.md` (10) · `references/tactics-d-h.md` (8) · `references/tactics-i-p.md` (5) · `references/tactics-q-w.md` (11) | Full Set A entries. Grep the name if you want only one · 45–93 |
| The book's five non-duplicate claim patterns in full | `references/tactics-claim-patterns.md` | Claim Size · Claim Speed · Claim Before/After · Limitation Removal · Newness, plus the one-claim-through-13 method · 45 |
| A trigger choice is contested, or you want stage pairings | `references/triggers.md` | The 8 in full + trigger-by-awareness-stage. Names are already inline above · 112 |
| "These sound like ads" · "make them native" · "TikTok-native" | `references/voice-patterns.md` | 25 templates in 10 clusters + the update protocol. Trigger index is at the top; read one cluster · 183 |
| Deep path, or "why isn't this hook working" | `references/writing-process.md` | The 7-step process, volume discipline, swipe-file sources, seasonality cases, three layers, hook slop, platform fit · 143 |

## Standards

**Do:** write in the reader's voice, not the brand's. Use their exact words from research. Specific numbers, timeframes and details — vagueness kills hooks. Lead with the pain or desire, never the product. Write for one person. Read it aloud; if it sounds like an ad, rewrite it. Simple over clever, always — "clever copy might boost your ego, simple copy will boost your bank account" `[T p.72]`.

**Don't:** open with "Introducing", "Discover" or "Are you looking for". Open with the brand name. Write a hook that would work for any product in the category. Repeat a trigger across a set. **Invent a statistic, ever** — canon §8; the book models this badly at `[T p.86]` and is wrong to. Quote a hook-rate or hold-rate benchmark: none are verifiable (`shared/evidence.md`). Ship a hook the ad cannot pay off — see hook slop in `references/writing-process.md`.

**One desire, one avatar, one hook.** People remember one thing from an ad `[T p.69]`. A hook carrying two desires is two hooks, badly.

## Output

Follow the user's requested format first. Absent one:

```
HOOKS — [product] · [persona] · [awareness stage]
ANGLE: [core truth, if one was supplied]

1. [hook]  [aud ✓ · ben ✓ · cur ✓]
```

For video, write all three layers per hook and label them — **SPOKEN** (the first words, working alone as a written line), **VISUAL** (the first frame, for the shooter), **TEXT OVERLAY**. For static, **HEADLINE** (on-image) and **PRIMARY TEXT** (first line of copy) are different hooks; write both.

## Platform notes

Meta is the default; write for it first. **TikTok** — front-load the spoken line, not the visual. **Reels** — visual-first and music-led; the line can arrive a beat later. **Both** — keep hook text high and central, because UI chrome eats the lower third and the right edge, and safe-zone margins are unverified in this plugin (`shared/evidence.md`): check the platform preview rather than a remembered number. Fit into the native feed first, then interrupt inside it. The per-placement container table is in `references/writing-process.md` → *Fit in, then stand out*.

## Seasonality and calendar risk

Before writing a seasonal or dated hook, confirm the fulfilment window and the last-order date, and write the expiry next to the hook. A hook whose promise cannot be delivered collapses without getting worse — canon §8. If a seasonal set just cratered, check the calendar and the fulfilment window before rewriting a single line. The Valentine's and hoodie cases are in `references/writing-process.md` → Step 7.

## Handoffs

Angle, mechanism and play in from `positioning-mechanisms`. Persona language and the tried-before count in from `market-research`. Cached brand facts from `brand-context`. Trigger theory and buyer psychology deepen at `marketing-psychology`.

Out: `creative-concepting` for the visual, `video-script-system` for the script that must continue the hook's thought rather than restart it `[T p.50]`, `ad-copy-qa` for the copy check, `prelaunch-qa` for the final gate. A belief blocking the sale is dismantled in the script, not solved by a cleverer hook.
