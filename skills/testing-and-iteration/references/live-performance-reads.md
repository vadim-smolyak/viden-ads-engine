# Reading live performance — the call-hygiene contract

Load this **only when a connector call is actually about to be made.** A "did this win?" answered from pasted numbers or from the roadmap needs nothing here. `campaign-troubleshooting` and every other skill in this plugin that touches Meta Ads or BigQuery uses this file rather than restating the conventions.

Never fabricate a number. Every attributed figure carries its model and window — canon §7.

---

## Reading live performance

**Meta first.** One well-formed query, never five exploratory ones.

Call hygiene, every time:
- **Explicit `fields`** — never the default set. Identity columns (`ad_id`, `ad_name`, `campaign_name`, `date_start`) must be requested explicitly at their level.
- **Explicit `level`** — `level="ad"` for creative reads. Never filter to a campaign at `level="account"`.
- **Tight date range** — `date_from`/`date_to` matched to the test window, or a `date_preset`. The two are mutually exclusive; omitting both silently gives `last_30d`.
- **Row caps** — set `limit`, and `sort` (e.g. `["spend_descending"]`) so the cap keeps the rows that matter.
- **Uppercase filter operators** — `IN`, `EQUAL`, `GREATER_THAN`, `CONTAIN`, `IN_RANGE`. Filters are AND-joined server-side; there is no OR, so split and merge rather than guessing.
- **Breakdowns: 1–2 maximum.** Combinations are API-enforced and undocumented. On a `ruleException`, split into two calls rather than dropping the breakdown.
- **Attribution: leave the default alone** — conversion metrics honour the ad-set-level unified setting, matching Ads Manager. Override `action_attribution_windows` only when the user asks for a fixed window, and then **state the window in the output** (canon §7).
- **Compaction is lossless** — columns constant across all rows move to `meta.constants`; row-by-row duplicates move to `meta.mirrors`. Read them as if the column were present; don't re-request them.
- **Over ~50 rows**, summarise top-N and say how many were omitted. Never paste raw tool output into a reply.

**BigQuery when the question is whether the problem is creative or commercial.** Platform-reported revenue is not ground truth. Locate the client's store-level table, then one aggregate query returning orders, net sales, AOV, new-customer share and refund rate over the same window as the Meta pull. Never select a `description` column. Keep it to one query — if the first is wrong, fix the query, don't explore.

**Degrading gracefully.** If a connector is unavailable, unauthorised, or returns zero rows: say exactly which call failed and what it would have told you, then answer from the roadmap and the creative itself. Never estimate, interpolate, or "assume typical" performance figures. A stated gap is worth more than a plausible fabrication.
