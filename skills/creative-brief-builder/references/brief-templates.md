# Brief templates

Three templates and the block schema the builder reads. Fill fields from the skill that owns them; never invent a field's content to make the document look complete.

Where a field's content is owned elsewhere: **angle** and **persona** from `creative-concepting` and `market-research`; **awareness stage** from canon §2; **hook** from `hook-system`, gated on canon §1; **mechanism** from `positioning-mechanisms`; **script** and **visual direction** from `video-script-system`, with visual types per canon §4; **objections** from `belief-objection-engineering`; **hypothesis** and **status** from `testing-and-iteration`.

---

## 1. Creative brief

The default deliverable. One document, one section per concept. Header block once, then repeat the concept section.

```
Title:     <Client> - creative brief
Subtitle:  <Month Year>

Callout "Brief summary":
  - how many concepts, against which awareness stage, for which one desire and one avatar
  - what the slate is testing, in one sentence
  - what is not in scope

## Concept N - <short name>

### Strategy
Angle:            the core-truth statement at the pain x persona intersection
Persona:          who, in one sentence, specific enough to cast
Awareness stage:  one of the five (canon section 2), and the script flow it selects
Desire:           the one desire or problem this ad carries
Mechanism:        the vehicle from where they are to where they want to be
Hook:             the exact opening line, verbatim
Hook gate:        confirmed against all three golden rules (canon section 1)
Format:           the production vessel
Mechanic:         the cognitive move the concept makes
Media:            photo or video, and what has to be SHOWN to build belief (canon section 4)

### Script and visual direction
  table: # | Line | Visual direction
  one row per line. Visual direction is a shot instruction, not a mood.
  Every scene is one of the four visual types (canon section 4).

### Copy surfaces
  table: Surface | Copy | Chars
  primary text, headline, link description. QA'd via ad-copy-qa before this doc ships.

### Production notes
  - Talent: archetype and why
  - Environment: where and why
  - Deliverables: ratios, caption treatment, cut lengths
  - Constraints: anything the brand, category or platform forbids
  - Flags: AI avatar use, restricted category, policy risk pointed at a human

### Hypothesis
  one sentence: why this will improve performance, and which metric will show it
  (fast-lane metric for the creative read, attributed metric with model and window
  for the scale decision - canon section 7)
```

Rules for this template:
- **One desire, one avatar per concept** (canon §8). A concept section carrying two desires is two concepts.
- **The hook is quoted verbatim.** Never paraphrase a hook into a brief; the exact words are the deliverable.
- **Visual direction is per line.** A brief with a paragraph of "vibe" instead of per-line direction is not shootable.
- **Every concept carries a hypothesis.** No hypothesis, no slot on the slate.
- Ship 3-5 concepts in a brief. More reads as a menu and gets cherry-picked.

---

## 2. Script doc for editors

Stripped to what the editor needs. No strategy, no angle language, no hypothesis — those are the strategist's, and in an editor's document they are noise.

```
Title:     <Client> - <concept name> - script
Subtitle:  Editor handoff - <Month Year>

Callout "Read first":
  - deliverable ratios and cut lengths
  - caption treatment
  - the one thing that must not be lost in the edit

## The cut
  table: # | Line (spoken / on screen) | Visual direction | Notes
  Notes column carries timing, on-screen text, and cut-to instructions.

### Assets
  - what footage exists, where it lives
  - what still needs shooting

### Non-negotiables
  - Hook: the first line and its shot, verbatim. Not to be trimmed or reordered.
  - Captions differ per scene and sit where the eye lands
  - New visual roughly every 3 seconds - a craft pacing heuristic, not a
    performance mechanism (see shared/evidence.md)
  - Muted-first: the cut has to work with sound off
  - Product on screen where belief has to be built, not only at the end

### Delivery
  - file naming convention
  - due date
  - who reviews
```

Rules:
- **Never send a strategy brief to an editor.** Convert it. An editor who has to read positioning language to find the shot list will miss the shot list.
- **Name what cannot change.** Editors reorder for rhythm; the hook's position is the thing that must survive.
- Keep the whole thing to one or two pages.

---

## 3. Concept / test matrix (XLSX)

One flat sheet. A tracker, not a workbook.

| Column | Contents |
|---|---|
| ID | `YYYY-WW-NN`, stable once assigned |
| Concept | Short name, matching the brief |
| Angle | The core-truth statement, abbreviated |
| Persona | Who |
| Awareness stage | One of the five |
| Hook | Verbatim first line |
| Format | Production vessel |
| Mechanic | Cognitive move |
| Media | Photo / video |
| Hypothesis | Why this will improve performance |
| Status | Briefed / In production / Live / Winner / Loser / Killed |
| Launched | Date |
| Fast read | Hook rate, hold rate, CTR - attribution-independent |
| Attributed read | CPA or ROAS, **with model and window in the cell** |
| Verdict | Winner / loser, plus the one thing carried into the next test |
| Iteration of | The winning ID this descends from, if any |
| Rung | Iteration 1-3, variation 1-6, or new concept (canon §6) |

Formatting: header row filled navy `202938`, white bold, frozen at `A2`, columns auto-sized to content, no merged cells. Build with `openpyxl`.

The `Rung` column exists so the iteration ladder is visible rather than remembered. When a concept reaches variation 6, the sheet says so and the next slot is a new concept.

---

## 4. Block schema for `build_brief.py`

The JSON the builder consumes. Full worked example in the script's `SELF_TEST` fixture; `--self-test` renders it.

| Block | Keys | Renders as |
|---|---|---|
| `callout` | `label`, `body` (list of strings) | Tinted box, brand-blue label |
| `h2` | `text` | Brand-blue marker plus navy section header, no rule |
| `sublabel` | `text` | Navy SemiBold sub-label |
| `body` | `text` | Body paragraph |
| `caption` | `text` | Muted caption |
| `fields` | `items` (list of `[label, value]`) | `Label: value` lines, navy label |
| `bullets` | `items` (strings, or `{lead, text}`) | One bullet block, bold navy lead-in |
| `table` | `columns`, `rows`, `widths`, `align`, `body_pt` | Navy header, white rows, hairlines |
| `spacer` | — | One blank line |
| `pagebreak` | — | Page break |

Widths are DXA and must sum to 9,360; the builder rescales if they do not, but set them deliberately. `align` is per column: `left`, `right`, `center`.

The markdown dialect maps onto the same blocks and is documented in the script's module docstring. Use markdown when the content already exists as markdown in the conversation; use JSON when assembling programmatically or when column widths matter.
