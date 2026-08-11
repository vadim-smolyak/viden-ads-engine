# Document style spec

The values `scripts/build_brief.py` implements. **Change them here first, then in the script's constant block.** This is the VIDEN client-document system: the one that drives the agency's live client reports and is therefore the de facto standard for anything client- or production-facing.

Note on this file: the hyphen rule below governs **generated documents**, not the plugin's own skill files.

---

## Output and font

- Build with **python-docx** via `scripts/build_brief.py`.
- Font: **Urbanist** everywhere. Native in Google Docs. Fallback Montserrat, then Arial.
- **Body 13pt.** Line spacing **1.15** on every paragraph. **Zero** space-before and space-after — separate logical blocks with **blank lines**, never with paragraph spacing.
- US Letter, **12,240 x 15,840 DXA**. Margins **1,440 DXA** (1") all sides. Content width **9,360 DXA**.
- Inject `<w:view w:val="web"/>` into `settings.xml` for Web Layout in Word and Pageless in Google Docs. It belongs early in `w:settings` — the builder inserts it at a schema-legal position rather than blindly at index 0.
- **No logo anywhere.** The document opens with the title line only: title = client name and document type; subtitle = the period. No "Prepared by", no methodology sentence in the header.

## Palette

| Token | Hex | Use |
|---|---|---|
| Navy | `202938` | titles, section headers, table-header fill, big numbers, bullet lead-ins |
| Brand blue | `3B63F6` | section marker `▪`, arrows, hyperlinks, callout label |
| Graphite | `2C313A` | body text |
| Muted | `6B7280` | labels, captions, source notes, subtitles, neutral deltas |
| Positive | `1B8A5A` | a metric that moved the better way |
| Negative | `C0392B` | a metric that moved the worse way |
| Callout fill / border | `EEF2FB` / `D7E0F5` | summary and note callouts |
| Row hairline | `ECECEC` | thin separator under table body rows |

Restrained by design. No second accent, no rainbow, no alternating row colour.

## Dashes and arrows

Short hyphens (`-`) everywhere. **Never** em dashes (U+2014), en dashes (U+2013), minus signs (U+2212) or non-breaking hyphens. Arrows are `->`, never `→`. This applies to body text, callouts, bullets, table cells and headings. The builder's `sanitize()` replaces all of them on output, so source content containing them is safe — but write hyphens anyway.

## Headings, labels, bullets

- **Title** — Urbanist SemiBold ~23pt, navy.
- **Subtitle** — the period only, muted, ~11pt.
- **Section header (H2)** — brand-blue `▪ ` marker plus navy SemiBold ~15pt, sentence case. Blank line before and after. **No rule or border line under or above headers anywhere.** This is the single most visible difference from the alternate style and it is not negotiable.
- **Sub-label** — navy SemiBold ~10.5pt, sentence case, blank line before. Used for "Strategy", "Script and visual direction", "Production notes".
- **Bullets** — zero spacing, 1.15, bold navy lead-in then graphite continuation. A list is one block: blank line around the group, not between items. Left indent 360 DXA, hanging 200.
- **Caption** — muted ~10.5pt, directly under the thing it captions.

## Tables

The signature pattern. Header-only fill, white rows.

1. **Header row** — fill navy `202938`, white SemiBold ~9pt, sentence-case labels, vertically bottom-aligned. `tblHeader` set so it repeats across page breaks.
2. **Body rows** — white, no fill, **never alternating**. Thin `ECECEC` hairline (size 4) under each row; **the last row has none**.
3. **No vertical borders, ever** — `left`, `right`, `insideV` all nil. Also nil on `top` and `insideH`; the hairline is a per-cell bottom border.
4. Numeric columns right-aligned, first column left. Fixed layout (`w:tblLayout type="fixed"`).
5. `WidthType.DXA` always, on the table **and** on every cell. Percentages break Google Docs. Widths must sum to 9,360; the builder rescales if they do not.
6. `cantSplit` on every row.
7. Body cells ~10pt. Dense tables (a long shot list) may drop to 8.5-9pt.
8. Cell margins: header `{top 90, bottom 80, left 110, right 110}`, body `{top 110, bottom 110, left 110, right 110}`.

## Callout

One-cell, full-width table. Fill `EEF2FB`, all four borders `D7E0F5` size 4, cell margins `{top 180, bottom 180, left 220, right 220}`. First paragraph is the label in brand blue SemiBold ~10.5pt; body paragraphs follow at 13pt graphite. `cantSplit` on the row.

Use it once per document, at the top, for the summary. A document with four callouts has none.

## Delta colouring

Where a brief carries performance numbers:

- Every delta is a **relative % change** `(current - comparison) / |comparison|`, including rate metrics. **Never** percentage points or "pp". Always print the sign. A missing comparison prints `-`, never "N/A" and never blank.
- **Colour encodes the direction of improvement, not the sign.** Green `1B8A5A` when the metric moved the better way, red `C0392B` when worse.
- Higher-is-better: revenue, sales, net profit, MER, ROAS, AOV, purchases, conversions, CTR, hook rate, hold rate, reach, impressions.
- Lower-is-better: CPA, NCAC, CPC, CPM, ACOS, frequency.
- **Always neutral muted `6B7280`:** every spend or cost figure, and any delta within ±2% regardless of metric.
- Any attributed metric prints its **model and window** beside it (canon §7). A delta with no stated window is not reportable.

## Font embedding

Only needed when the recipient will not have Urbanist installed. Google Docs does not need it. The builder handles it via `embed_fonts()` with `--fonts DIR --embed`:

1. `<w:embedTrueTypeFonts w:val="true"/>` in `settings.xml`, inserted at a schema-legal position.
2. Each TTF obfuscated to `.odttf`: generate a GUID, take its 32 hex digits, build a 16-byte key by reading the pairs **in reverse order**, XOR the **first 32 bytes** of the font file with that key repeated twice. Write to `word/fonts/fontN.odttf`.
3. `<Default Extension="odttf" ContentType="application/vnd.openxmlformats-officedocument.obfuscatedFont"/>` in `[Content_Types].xml`.
4. A `.../relationships/font` entry per file in `word/_rels/fontTable.xml.rels`.
5. `word/fontTable.xml` carries one `<w:font w:name="Urbanist">` with `<w:embedRegular>` / `<w:embedBold>` / `<w:embedItalic>` / `<w:embedBoldItalic>`, each with its `r:id` and `w:fontKey` GUID and `w:subsetted="0"`.

Urbanist SemiBold occupies the **bold** slot — the document uses SemiBold where a bold weight is called for, which is why nothing in this system asks for Urbanist Bold. Urbanist is SIL Open Font License, so embedding is permitted.

## The alternate style — `calm-report-style`

For **non-client analytical documents**: an internal audit, a research write-up, a methodology memo. Not for briefs, not for scripts, not for anything a client or an editor sees.

Its specifics, so a document built in it is recognisable: **Montserrat**, body 10pt at 1.5× line spacing with paragraph spacing before 60 / after 80; grayscale text `1A1A1A` / `434343` / `666666`; cream callouts `F5F3EE` bordered `EBE6DB`; pastel status pills (sage / peach / pink / coral / pale blue, always a pale fill with darker matching text, never a saturated fill); **white table headers with small-caps tracked grey labels and a thick 1.5pt dark rule beneath**; sand `EBE6DB` row separators; **H2 with a required top border** — a rule *above* the heading, which that system calls its distinctive move.

### The two are mutually incompatible. Never mix them in one document.

| Dimension | This system (default) | `calm-report-style` (alternate) |
|---|---|---|
| Font | Urbanist | Montserrat |
| Body / line spacing | 13pt / 1.15, zero paragraph spacing | 10pt / 1.5×, paragraph spacing on |
| H2 rule | **None, anywhere** | **Top border required** |
| Table header | Navy fill, white text | White, small-caps grey text, thick bottom rule |
| Palette | Navy / brand blue / graphite + green-red deltas | Grayscale + pastel pills |
| Logo | Explicitly forbidden | Not addressed |
| Scope | Client- and production-facing | Internal analytical documents |

They agree on the substrate, which is the only part shared: US Letter, 1" margins, 9,360 DXA content width, `<w:view w:val="web"/>` for Pageless, hyphens never em or en dashes, `WidthType.DXA` always, `cantSplit` on rows. Everything above that line is a choice made once per document.

**Decide before writing.** Retrofitting a half-built document from one system to the other produces a document that reads as broken in both.
