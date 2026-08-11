# Hypothesis templates

Five templates, ported from the book's own examples `[T p.95–96]`. Each carries the case it came from, the fill-in form, the falsifier, and which metric lane reads it (canon §7).

**Universal form.** Every hypothesis, whichever template, resolves to this sentence:

> Because **[observation, with source]**, changing **[one variable]** will **[predicted effect on named metric, named lane]**. This is wrong if **[falsifier]**.

If it doesn't fit that sentence, it isn't a hypothesis yet.

---

## 1. Comfort / attribute positioning — reposition against a known dissatisfaction

**The book's case.** Anti-snoring mouthpiece. Hundreds of competitor reviews showed failure due to discomfort; the client's version is genuinely more comfortable and wearable for all 8 hours. Hypothesis: positioning as *the most comfortable mouthpiece* will improve sales by standing out from prior dissatisfaction `[T p.95]`.

**Form.**
> Because reviews of [competitor set] repeatedly name [failure attribute] as the reason the category disappointed them, and our product genuinely fixes it, leading on **[attribute]** will beat leading on [current lead] on purchase rate.

**Fill-in slots.** Failure attribute · evidence count and source · the substantiating product fact · what the current ads lead on instead.

**Falsifier.** The attribute-led cut does not beat the incumbent on the fast lane after 7 days, or wins on CTR but not on attributed CPA at 14 days — meaning the attribute earns clicks from people who don't want the product.

**Lane.** Fast lane for the read, attributed at 14 days for the claim.

**Precondition.** The attribute must be *true and demonstrable*. If the ad can only assert it, this is a belief problem, not a positioning test — route to `belief-objection-engineering`.

---

## 2. Awareness-stage shift — open a wider market

**The book's case.** Currently running problem-aware creative; spend goals require a bigger pool, so shift to an **unaware** market — people on Medicare who don't know about the hidden costs `[T p.96]`.

**Form.**
> Because [current stage] audiences are saturated at [spend level] and CPA rises above [threshold] beyond it, moving to **[target stage]** with a [script flow from canon §2] will let the account spend more at target CPA.

**Fill-in slots.** Current stage · target stage · the symptom or problem the new stage feels · the script flow canon §2 assigns to that stage.

**Falsifier.** The new stage does not lower CPA at higher spend, or delivers volume at a CPA the margin can't carry.

**Lane.** Attributed, 14 days minimum — this is a spend-ceiling question, not a creative-craft one.

**Warning.** Stage shifts change the whole script, not the hook. An unaware ad with a problem-aware body is neither. Canon §2 selects the flow; the stage comes from research, never from preference.

**Policy note.** The book's own Medicare example sits inside `FINANCIAL_PRODUCTS_SERVICES` in 2026 and hits two high-risk copy shapes — see `prelaunch-qa/references/policy-risk-shapes.md` before shipping anything patterned on it.

---

## 3. Audience precision — name them more exactly

**The book's case.** Ads call out "Americans"; the belief is that **"Seniors"** will resonate better `[T p.96]`.

**Form.**
> Because the current hook addresses **[broad label]** while the buyers are **[specific label]**, naming [specific label] in the first line will raise hook-rate and qualify traffic better.

**Fill-in slots.** Broad label in the current copy · the specific label from research or from account demographics · the evidence they are the actual buyer.

**Falsifier.** Hook-rate flat or down; or hook-rate up while CPA is flat, meaning the broader label was already reaching them and precision only shrank reach.

**Lane.** Fast lane — this reads in days.

**When this is the highest-leverage test available.** In Special Ad Categories there are no lookalikes and no demographic targeting, so **the creative is the only targeting instrument left** (`shared/evidence.md`). Audience precision in the first line stops being a nice-to-have and becomes the targeting mechanism.

---

## 4. Constraint workaround — say it a legal or platform-safe way

**The book's case.** Cannot show before/after because the content would be explicit, so **use an analogy with everyday items**; get specific about which objects, write a hypothesis per analogy, run them as separate concepts `[T p.96]`.

**Form.**
> Because [the direct demonstration] cannot be shown due to **[constraint]**, demonstrating with **[analogue]** will carry the same belief without the constraint.

**Fill-in slots.** The blocked demonstration · the constraint (policy risk, client rule, physical impossibility, sensitivity) · the specific analogue object or scenario · what belief the analogue must transfer.

**Falsifier.** The analogue is understood but doesn't transfer belief — engagement holds, conversion doesn't. That is a real, useful result: it says the analogy was legible but not persuasive.

**Lane.** Fast lane for legibility (do people understand it?), attributed for belief transfer.

**Discipline.** One analogue per concept. The book is explicit: make a hypothesis for *each* analogy and run them as separate concepts. A single ad hedging across three analogies tests nothing and breaks canon §8's one-idea rule.

---

## 5. Media-type change — the claim needs showing, not saying

**The book's case.** The account is heavy on photos, but the product's nature means photos lack the believability of video. Hypothesis: video with a person doing X raises believability and results `[T p.96]`.

**Form.**
> Because **[the load-bearing claim]** cannot be believed from a still, moving to **[video / product-in-action / demonstration]** will raise conversion rate at the same or lower CPM.

**Fill-in slots.** The claim that has to be believed · why the current media can't carry it · the exact action to film.

**Falsifier.** Video matches or loses to the photo on attributed CPA at equal spend — meaning belief was not the binding constraint.

**Lane.** Attributed, 14 days. Production cost makes this a slow-lane decision.

**Anchors.** Canon §4's belief rule decides photo vs video: pick whichever *shows* what has to be believed. Length follows the message, never a fixed number — `[T p.74]`, and Kantar (29 Jul 2024) found a 15s cut beat the 6s cut where the idea needed setup, while Kantar (5 Feb 2026) found 15s can carry full brand-building punch. Fit length to message.

---

## Auditing someone else's hypothesis

| Symptom | Verdict |
|---|---|
| "Testing a new hook / new format / new creative" | Not a hypothesis. No observation, no predicted effect, no falsifier. |
| Two or more variables changed | Not testable. Split it, or accept it as a concept launch with no read. |
| Predicted effect names no metric | Reject. "Will perform better" cannot be marked winner or loser. |
| No falsifier | Reject. Every result will be rationalised into support. |
| Falsifier is impossible to observe in the window | Reject or extend the window. |
| Metric named but no lane, and it's an attributed metric with no model or window | Fix before launch — canon §7. |
| Observation cites "we think" with no source | Weak. Route to `market-research` or the roadmap before spending on it. |
