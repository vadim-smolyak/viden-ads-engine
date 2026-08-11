---
name: creative-brief-builder
description: >
  This skill should be used when work produced anywhere in this plugin needs to leave the chat as a
  document — a creative brief, a script doc for an editor, or a concept and test matrix. It is the
  plugin's shared output layer: every other skill routes through it instead of carrying its own
  formatting logic. It documents work that already exists and does not produce the strategy — a brief
  requested from scratch for an untouched brand starts at `ads-that-scale`. Trigger on "build the
  creative brief", "turn this into a brief", "make this a doc", "export this as a docx", "send this to the editor", "script doc for the editor", "put the
  concepts in a spreadsheet", "brief this for production", "client-ready version of this", "add this
  to Notion". The default output is markdown in chat; the branded .docx is built on request.
metadata:
  version: 0.1.0
---

# Creative brief builder

The plugin's output layer. **All document-generation knowledge lives here once.** No other skill in this plugin carries formatting rules, palette values, python-docx code or template structure — they produce content and hand it here.

Never run a web search.

## `scripts/build_brief.py` is EXECUTE-ONLY — never read it

**Do not open, read, cat, grep or paste `scripts/build_brief.py`, and never re-implement what it does.** It is 874 lines of python-docx and reading it costs roughly 8,400 tokens to learn nothing you need: every input contract it honours is documented in `references/brief-templates.md` (the JSON block schema and the markdown dialect) and every style value it applies is in `references/docx-style-spec.md`. Run it, read its one-line stdout, report the path.

If you need the CLI surface, run `python3 scripts/build_brief.py --help`. If you need the input schema at the source, run `python3 -c "import ast;print(ast.get_docstring(ast.parse(open('scripts/build_brief.py').read())))"` — that returns the ~50-line module docstring instead of the whole file. Read the file itself only when the task is *editing the builder*, which is a maintenance job, not a brief job.

## Fast path — markdown in chat (the default)

For an atomic ask (one concept, three hooks, one script, a QA verdict) **return markdown in chat and stop.** Then offer the document:

> "Want this as a .docx brief? Takes a few seconds to build."

Generating a .docx costs real seconds and a script invocation. Do not assume it. Structure the markdown to the template in `references/brief-templates.md` so the same content converts later with no rework.

## Deep path — the branded .docx

Take it when the user asks, when the deliverable leaves VIDEN (client or freelance editor), or when the output is a full multi-concept brief. Steps:

1. Assemble the content against a template in `references/brief-templates.md`.
2. Write a brief JSON (or the markdown dialect) to a temp path.
3. Run the builder:
   ```
   python3 scripts/build_brief.py --in brief.json --out "<Client> - creative brief - <Month Year>.docx"
   ```
   Add `--fonts <dir> --embed` only when the recipient will not have Urbanist installed.
4. Report the path. Never paste the whole document back into chat as well.

Check the script runs before promising a file: `python3 scripts/build_brief.py --self-test --out /tmp/t.docx` builds a fixture exercising every block type.

## Reference index

| Load | For | Lines |
|---|---|---|
| **nothing** | An atomic ask answered as markdown in chat — the style paragraph below is enough to keep the structure convertible | 0 |
| `references/brief-templates.md` | The creative brief template, the editor script doc, the concept/test matrix columns, and the JSON block schema. **This is the only file needed to drive the builder.** | 158 |
| `references/docx-style-spec.md` | The full document style: font, palette, tables, headings, geometry, font embedding, the calm-report alternate and why the two never mix. Needed when a *style* question arises, not to build a standard brief | 108 |
| `scripts/build_brief.py` | **EXECUTE, NEVER READ** — see the rule above. `--help` for the CLI; `ast.get_docstring` for the schema | 874 (never loaded) |

Skills that route output here: `creative-concepting`, `video-script-system`, `hook-system`, `ad-copy-qa`, `market-research`, `positioning-mechanisms`, `testing-and-iteration`, `campaign-troubleshooting`, `prelaunch-qa`.

## Deliverables

| Deliverable | Format | When |
|---|---|---|
| **Creative brief** | `.docx` (deep) / markdown (fast) | Concepts going into production. The default deliverable. |
| **Script doc for editors** | `.docx` | Handing a shot script to an editor or content creator. Per-line visual direction is the point. |
| **Concept / test matrix** | `.xlsx` | A slate of concepts with hypotheses and status. Tracking across weeks. |
| **Notion page** | Notion | Only when asked. Convert the markdown; do not attempt to reproduce the docx styling. |
| **Anything in chat** | markdown | Everything else. |

## Style, in one paragraph

**Urbanist** throughout, body **13pt / 1.15 line spacing / zero paragraph spacing** (blank lines separate blocks, never paragraph spacing). Navy `202938` for titles, section headers and table-header fill; brand blue `3B63F6` for the section marker and links; graphite `2C313A` body. **Navy-filled table headers with white text, white body rows, `ECECEC` hairlines, no vertical borders.** **H2 carries no rule or border, above or below, anywhere.** **No logo, ever.** US Letter, 1" margins, 9,360 DXA content width, `WidthType.DXA` widths, `cantSplit` rows. Short hyphens only — never em or en dashes, and arrows as `->`. Full spec, including every value the builder reads: `references/docx-style-spec.md`.

## The alternate style, and the rule about it

`calm-report-style` (Montserrat, 10pt/1.5×, required H2 top border, white table headers, cream callouts, pastel pills) is the **alternate**, for non-client analytical documents. The two systems are **mutually incompatible — never mix them in one document.** Pick one before the first line is written. Client-facing or production-facing: the Urbanist system above. Internal analytical write-up: the alternate. Detail and the full conflict table in `references/docx-style-spec.md`.

## Visual deliverables

If a deliverable is *visual* rather than a document — an HTML prototype, a dashboard, a chart, a deck cover — the agency's visual identity is the one documented in VIDEN's separate `viden-growth-style` brand reference: Urbanist, primary blue `#3B63F6`, dark blue `#202938`, and the official logo files, which live in the agency brand drive rather than in this plugin. Named for orientation only — nothing here depends on it, and the verified values are repeated below. **Roughly half of that reference's content is self-flagged `[unverified]`** (secondary palette, the signature gradient, neutrals, the full type scale, corner radii) because the 2026 brandbook is an image-only PDF that could not be parsed. Treat those values as working defaults, never as brand law, and never present the gradient or secondary palette to a client as official. The verified set is only: the logo files, `#3B63F6`, `#202938`, white, lockup accent `#4A68FC`, and Urbanist.

## Rules for other skills calling this one

- **Content in, formatting out.** Pass the fields; do not pass styling instructions.
- **Do not restate the style.** If a sibling skill needs a colour or a font size, it loads `references/docx-style-spec.md`. Copies drift.
- **Do not re-implement python-docx.** There was no shared builder before this one and the code was duplicated across eight client report skills. `scripts/build_brief.py` is the one implementation.
- **Content standards stay with the content skill.** This skill will not fix a hook that fails canon §1, will not invent a statistic to fill a field (canon §8), and will render an incomplete brief with the gaps visible rather than filled.
- **Empty fields are stated, not guessed.** Write "not yet decided" in the document. A confidently filled blank is worse than a visible one.

## XLSX matrix

Use `openpyxl` for the concept/test matrix — one sheet, header row filled navy `202938` with white bold text, frozen at `A2`, columns sized to content. Column set is in `references/brief-templates.md`. Keep it one flat sheet: it is a tracker, not a workbook.
