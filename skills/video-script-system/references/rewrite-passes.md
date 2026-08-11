# The rewrite passes in detail

Source: `[T p.46–60]`. Pass 2 has its own file: `reinforce-desire.md`.

Each pass answers exactly one question. Run them in order on a first build; run any one alone on an existing script.

---

## Pass 1 — Draft

**Job: get the story on paper. Quality is not the point.**

> "I give you full permission to fail here. I encourage you to write the worst copy you've ever written. I only want you to promise me to let whatever thoughts flow in your head come out on paper." `[T p.50]`

Three sub-steps `[T p.50]`:
1. **Review the hook.** The script continues the hook's thought — it does not restart.
2. **Pick the video type** (see `creative-concepting`). The type dictates what the script must contain.
3. **Write.**

Two framing devices that reliably unlock a draft `[T p.50]`:

- **"How can I turn this into a story?"** Imagine you're the customer who has been drained by this problem for ages, finally cracked it, and is excited to tell the world what it's done for you.
- **The table.** You're sitting across a table from your ideal customer, who sat down *because of your hook*. They're listening. Now persuade them by telling stories.

The book's draft, in full `[T p.51]` — six lines, plain, unpolished:

> Using Emotion-Baiting to scale Facebook Ads past $100/day Fast
> I've tried a lot of other Facebook ad strategies to scale
> But nothing has come close to how fast I can scale with Emotion-Baiting
> This account was literally just at $100 daily a week ago
> And now we're spending $1,000/day on ads while maintaining profitably
> If you want to learn more about emotion-baiting, there is a free training below

**Do not polish here.** Polishing during a draft is the most common way writers stall.

---

## Pass 3 — Add more descriptive words

**Job: find words doing no work and replace them with words that carry emotion.**

> "The goal is not to add more 'big words' but more descriptive words that are easy to understand and invoke emotion." `[T p.57]`

**The caution is the whole pass: "avoid flexing your IQ here"** `[T p.57]`. A writer who uses this pass to sound clever has broken the simple-beats-clever rule `[T p.72]` and made the script worse.

The book's diffs `[T p.57]`:

| Before | After |
|---|---|
| past $100 per day **Fast** | past $100 per day **within a week** |
| other Facebook ad strategies | other **poor-performing** Facebook ad strategies |
| **how fast** I can scale | **the speed at which** I can scale |
| This account **was** at $100 daily | This account was **stuck at** $100 daily |
| we're spending $1,000/day | we're spending **over** $1,000/day |
| My inventory **ran out** | My inventory **went to zero** |
| burning time and money | burning **hours of your time** and wasting **hundreds of dollars** |
| a training below | a **detailed step-by-step** training below |

Notice the pattern: vague quantities become specific ones, neutral verbs become loaded ones ("was" → "stuck at"), and abstractions become countable ("time and money" → "hours" and "hundreds of dollars"). None of the replacements are longer words.

---

## Pass 4 — Cut the fat

**Job: delete anything that isn't selling.**

> "Every word in your script has to justify itself in the sales process. If it does not add to the script's selling power, it needs to be removed." `[T p.58]`

Working question: **"Where am I bored?"** `[T p.46]`

**This pass is allowed to delete what pass 2 added.** In the book's own progression the author cuts both lines he added one pass earlier `[T p.58]`. That is not a mistake in the example — layering generously then cutting hard is how the method works. Don't defend a line because you just wrote it.

What tends to go:
- Setup that the hook already did
- A second example where one already landed
- Qualifiers and hedges
- Any line the reader could skip without losing the thread

---

## Pass 5 — Flow

**Job: make it survive being read aloud.**

> "We want this script to roll off your tongue like a natural conversation. This means you have to read the script out loud. If you find spots where you stutter or are hard to read, that part needs to be rewritten for improved flow." `[T p.59]`

When running this pass, actually read for stumbles — don't assert that it flows. Look for: consonant pile-ups, clauses that need a breath in the wrong place, lines a real person wouldn't say, and repeated sentence rhythms.

The book's flow diffs `[T p.59]`:

| Before | After | What changed |
|---|---|---|
| "Using Emotion Baiting to scale past $100 per/day with Facebook Ads in just one week" | "**How I used** Emotion Baiting to scale past $100 per day with Facebook Ads in just one week" | First person, past tense — becomes a story someone lived |
| "My inventory went to zero after applying this" | "**The inventory I've been trying to sell for months completely sold out** after applying emotion baiting to my ad account" | Specific, and the pain of the months is now in the line |
| "There is a detailed step-by-step training" | "There is a detailed step-by-step training / **And you can access it by clicking the link below**" | CTA split into two beats so it lands |

---

## Pass 6 — Visual rewrite

**Job: give every line a visual direction, ready for a creator or editor.**

Per line, ask: **"How can I visually articulate this?"** `[T p.60]`

Every scene must be one of the four visual types — see canon §4. The output is handed off to content creators or video editors, so directions must be shootable, not conceptual.

The book's output `[T p.60]`:

| Line | Direction |
|---|---|
| How I used Emotion Baiting to scale past $100 per day with Facebook Ads in just one week | *(close-up of the ad account spending the $1,000 per day)* |
| This account was stuck at $100 daily | *(talking head)* |
| And now we're spending over $1,000 per day while maintaining profitably | *(close-up of Triple Whale showing the new profitable spend)* |
| The inventory I've been trying to sell for months completely sold out | *(inventory being shipped out)* |
| You can keep burning hours of your time and wasting hundreds of dollars on outdated Facebook Ad Strategies | *(talking head + rest of script)* |

**Quality bar for a direction:** a freelance editor who has never spoken to you could shoot or cut it without asking a question. "Show success" fails. "Close-up of the dashboard, revenue number visible, cursor moving" passes.

**Pacing note.** Aim for a new visual roughly every 3 seconds — the book's craft heuristic, contrasting with roughly 10 seconds in film and TV `[T p.77]`. Treat this as pacing craft, not a mechanism claim: see `${CLAUDE_PLUGIN_ROOT}/shared/evidence.md` for why the 3-second construct no longer supports a causal argument, and for the finding that attention is re-winnable later in the ad.

---

## Running a single pass on someone else's script

The most common real request. Diagnose first, then apply only the pass that fixes it.

| Symptom | Pass to run |
|---|---|
| "It's boring" | 4 (cut the fat), then 2 if it's now thin |
| "It doesn't sound like a person" | 5 (flow) |
| "It's flat / doesn't make me want it" | 2 (reinforce desire) |
| "It's too long" | 4 |
| "The words are generic" | 3 |
| "Editors keep asking me what I meant" | 6 |
| "It's trying to say too much" | Not a pass — a focus problem. See `craft-heuristics.md`. |
| "The hook is fine but nobody watches past it" | Check the sag point, don't scrap. See `diagnosis.md`. |
