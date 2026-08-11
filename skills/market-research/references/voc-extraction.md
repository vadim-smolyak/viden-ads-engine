# VOC extraction — scoring and the five buckets

For reviews, ad comments, support tickets, survey free-text, DMs or any body of raw customer language.

The goal is not to summarise. The goal is to find the raw material for ads.

Split output by product first. If the set covers several products, group before scoring — every step below runs separately per product. If product attribution is ambiguous, ask before starting.

---

## Step 1 — Score every item 1–5

Scoring first is what stops a thin review set from producing confident-sounding invented themes.

| Score | What it looks like |
|---|---|
| **1** | Garbage — gibberish, two or three meaningless words, zero signal. "great product", "love it", an emoji |
| **2** | Low signal — very short, vague, no specific detail or emotion |
| **3** | Moderate — mentions the product, some specificity, no vivid detail or emotional depth |
| **4** | High quality — specific, describes a real experience, references a before/after or a feeling |
| **5** | Gold — long, emotional, vivid, paragraph-level detail. The customer was moved enough to write an essay |

Score 5s are the priority. Read them in full and treat them as primary sources.

## Step 2 — Filter

- **Discard every 1.** It does not enter the analysis.
- **Analyse 2–5**, weighted to 4s and 5s.
- **2s and 3s confirm patterns; they never source quotes.**

Report the counts: analysed, and discarded at score 1.

## Step 3 — Extract into five buckets

Within each bucket, group similar findings, name the theme, and write a two-to-three sentence summary of the pattern. Apply the frequency tally — a theme seen five times carries `*****`.

Quotes live only in Bucket 5. Keep Buckets 1–4 as clean summaries.

---

### Bucket 1 — Pain points

*What problem were they experiencing before they found this product?*

Look for: the problem itself, how long they had it, what they tried before, how it affected their life, the emotional weight of living with it.

Feeds the pain anchor and the persona × pain matrix in `positioning-mechanisms`.

### Bucket 2 — Trigger moments

*What finally made them buy?*

Look for the specific moment, event or realisation that turned a maybe into an add-to-cart: a life event (wedding, diagnosis, vacation), a recommendation (friend, doctor, TikTok), hitting a breaking point, running out of patience with other solutions.

This is usually the strongest hook material in the whole set, because it captures the exact moment of emotional readiness. It is also where urgency comes from — "snoring" versus "not being able to sleep in the same bed as my wife because of my snoring" `[T p.92]`.

### Bucket 3 — Objections before purchasing

*What almost stopped them from buying?*

Look for skepticism they mention having had, comparisons to products they had already tried, price hesitation, disbelief that this would work, fear of wasting money again.

In positive reviews these are almost always past tense — "I was skeptical but…", "I almost didn't try it because…". Those are the most useful lines in the set, because they let an ad address the objection before it becomes an objection `[T p.81]`.

Also record the count of prior solutions tried. That count selects the awareness stage `[T p.25]`.

### Bucket 4 — Transformations

*What changed after they used it?*

Look for the specific result, how life is different now, the emotional shift — confidence, relief, freedom, pride — and above all how they describe the change in their own words. The more visceral and concrete, the better.

### Bucket 5 — Standout language and ad-ready phrases

*Exact language worth using.*

Not organised by theme. A curated swipe file of the most vivid, specific, emotionally charged phrases from across the whole set — the lines that need no rewriting.

What qualifies:

- Unusually specific descriptions of pain or transformation
- A phrase that captures an emotion better than you could have written it
- Before/after language that is visceral and concrete
- A line that would work as a hook with zero editing
- Anything that made you feel something while reading it

Pull verbatim, never smoothed, and note which product each came from. Route to `hook-system` as native phrasing material.

---

## Output shape

Per product:

```
PRODUCT: [name]
Analysed: [n]  |  Discarded (score 1): [n]

BUCKET 1 — PAIN POINTS
[Theme name] ****
Summary: [2–3 sentences on the pattern]

BUCKET 2 — TRIGGER MOMENTS
...
BUCKET 3 — OBJECTIONS BEFORE PURCHASING
...
BUCKET 4 — TRANSFORMATIONS
...
BUCKET 5 — STANDOUT LANGUAGE
"[verbatim]"
"[verbatim]"
```

---

## Honesty rules

- Under about 20 items: say so. Patterns are not meaningful at that size, but the language is still usable.
- Too few quality items for a product to support real themes: flag it. Never manufacture a theme that is not there.
- Never generalise a bucket into a statistic. "Six of the 41 reviews mention it" is a count; "15% of customers" is a claim.
- Never paraphrase a quote and present it as verbatim.
