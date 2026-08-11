# The creative roadmap — schema and export spec

The log of every creative test, with its hypothesis and its outcome `[T p.89, p.95]`. Its purpose is the **macro** view: what is and isn't working across the account, visible only because every test was logged the same way.

One row per creative. Not per concept, not per ad set.

---

## Test log — column definitions

| Column | Type | Fill rule |
|---|---|---|
| `test_id` | text | `YYYYWW-NN`. Stable; referenced by later iterations. |
| `date_launched` | date | Upload date, not build date. |
| `concept` | text | The core messaging. New messaging = new concept (canon §5). |
| `angle` | text | The pain × persona core-truth statement (canon §5). Not a tactic. |
| `awareness_stage` | enum | Unaware / Problem / Solution / Product / Most (canon §2). |
| `format` | text | The production vessel (canon §5). |
| `hook` | text | The verbatim first line or first-frame text. Verbatim, so staleness is auditable. |
| `tactic` | text | The hook frame, from `hook-system`. |
| `media_type` | enum | video / photo / carousel. |
| `hypothesis` | text | The full four-slot sentence. Written **before** launch. Blank = the creative should not have shipped. |
| `falsifier` | text | Carried from the hypothesis so the review can't move the goalposts. |
| `ladder_position` | enum | `new concept` / `iteration 1-3` / `variation 1-6` (canon §6). Makes the ladder visible instead of remembered. |
| `iteration_variable` | enum | environment / ethnicity / gender / age / length / removal. Exactly one, or blank if not an iteration. |
| `parent_test_id` | text | The winner this descends from. Empty for new concepts. |
| `days_live` | int | Actual delivery days, not calendar days. |
| `spend` | currency | Over the read window. |
| `fast_lane_read` | text | The attribution-independent read defined in canon §7. Available from day 7. |
| `attributed_read` | text | CPA or ROAS **with model and window stated inline** (canon §7). Blank before day 14. |
| `attribution_note` | text | Model + window, e.g. `unified ad-set setting, 1d_view/28d_click`. Never blank when `attributed_read` is filled. |
| `verdict` | enum | winner / loser / **no read** — use `no read` when spend never reached a decision threshold. Roughly half of all ads never get meaningful spend (Motion, 2026); recording that honestly stops phantom learnings. |
| `went_right` | text | Review Q2. Required for losers too. |
| `went_wrong` | text | Review Q3. Required for winners too. |
| `carry_forward` | text | Review Q4. **One** item. Becomes the next hypothesis's observation slot. |
| `next_action` | enum | iterate / vary / new concept / retire / rerun. Driven by canon §6, not by feel. |

**Two integrity rules.** A blank `hypothesis` is a process failure — flag it, don't backfill a plausible one. A filled `attributed_read` with a blank `attribution_note` is not a number; treat it as missing.

---

## The matrix sheet — coverage, not results

A second view over the same data, for spotting what has **never** been tried. Rows are `concept × angle`; columns are `hook × format × awareness_stage`. Cells hold the count of tests and the winner count.

Read it for three things:

| Pattern | Meaning |
|---|---|
| Empty cells in a column that wins everywhere else | Untested upside. Cheapest next hypothesis in the account. |
| A row with many tests and no winners | The angle is the problem, not the executions. Stop iterating it. |
| Dense clustering in one or two cells | **Message staleness risk.** The 90%-of-underperforming-accounts failure `[T p.93]`. Cross-check against the last 8 weeks of `hook` text. |

The matrix is the tool that makes staleness visible before performance shows it.

---

## XLSX export — only when asked

Two sheets, in this order: `test_log` (every column above, one row per creative), `matrix` (the coverage view). Do not offer the export unprompted; the roadmap lives wherever the client keeps it.

Build with a short openpyxl script. Requirements:

- Header row bold, frozen (`freeze_panes="A2"`), autofilter across the used range.
- `date_launched` as a real date; `spend` as a number with a currency format — never as text.
- Column widths set explicitly; `hypothesis`, `falsifier`, `went_right`, `went_wrong`, `carry_forward` wrap.
- `verdict` and `next_action` as data-validation dropdowns over the enums above, so the sheet stays clean when a human edits it.
- Conditional formatting on `verdict` only. No decorative colour — this is a working log.
- One file, two sheets. Do not split into two files, and do not add a summary sheet nobody asked for.
- If the roadmap already exists as a client file, **extend it** — match the existing column names and order rather than imposing this schema. Report which of these columns are missing rather than silently adding them.

---

## Weekly ritual — the 20-minute version

1. Pull the week's creatives at `level="ad"` with an explicit field list and a tight range (one call).
2. Mark each row's verdict. Anything under the decision spend threshold is `no read`, not a loser.
3. Answer the 4 review questions per creative; write exactly one `carry_forward` each.
4. Set `next_action` from canon §6 — check `ladder_position` first, not instinct.
5. Read the matrix for empty high-value cells and for hook clustering.
6. Write next week's hypotheses from the `carry_forward` column, not from a blank page.

Step 6 is the point of the whole document. A roadmap that gets filled in but never read back is bookkeeping.
