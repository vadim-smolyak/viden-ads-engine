---
name: belief-objection-engineering
description: This skill should be used when an ad has to defeat a reason not to buy — price, indifference, complexity, or a negative belief the market already holds about the category — or when it needs a legitimate reason to act now. Trigger on "how do we handle the price objection", "they think it's too expensive", "they don't think they need this", "nobody is searching for this product", "the market thinks these are all a scam", "how do we create urgency without lying", "write the objection-handling section", "why aren't they converting on the offer", "this is a $2,000 product, what changes", or any request to pre-empt an objection before the prospect forms it. Not for writing hooks (hook-system) or assembling the script (video-script-system).
metadata:
  version: "0.1.0"
---

# Belief and Objection Engineering

Engineer the ad so the reason not to buy never forms. The standard is the book's: **address the objection before it becomes an objection** `[T p.81]`.

Definitions are not repeated here. Load `shared/canon.md` for the awareness stages and script flows (§2) that decide *where* this work sits, and the glossary (§5) for mechanism versus mechanic. Load `shared/evidence.md` before writing anything in a health, financial or political category.

**Never run a web search.** Everything needed is in this skill and its `references/`.

## Fast path — default

For a single objection ("how do we handle price?"), answer in one pass:

1. Triage it against the three reasons below. One table lookup.
2. Apply the move. Write the two or three lines that execute it.
3. Check it against the ethics constraints. Stop.

Only open `references/objection-playbook.md` when the objection is not one of the three canonical reasons, when a worked precedent is wanted, or when the whole objection layer of a script is being built.

## Deep path — full belief layer

Run the belief audit, then the buy-now layer, then the per-line pass. Load the playbook. Use this when a product-aware audience is stalling, when the market holds a category-level negative belief, or when moving a client up an AOV tier.

---

## The three reasons people don't buy `[T p.79–80]`

| Reason | How it shows up in research | The move | Worked case |
|---|---|---|---|
| **Too expensive** | Price named in reviews, comments, abandoned-cart replies; comparisons to free or DIY alternatives | Compare to a **more expensive** solution — and establish that cost **before** introducing yours | Rose Skin Co.: thousands of pounds of laser appointments established first, then one $200 payment `[T p.79]` |
| **Not important enough** | Nobody is shopping the category; the problem is tolerated rather than solved | Extend to the **benefits of the benefits** — one step past the obvious outcome | Attic insulation: almost nobody shops insulation → a cooler house → **lower electric bills**, with visuals of the lower bill `[T p.80]` |
| **Too complicated** | Support inbox asks how it works; prospects restate the mechanism wrongly | Simplify the mechanism until a stranger repeats it correctly | PayPal: "sending currency over IP addresses" → **"you can send money over email"** `[T p.80]` |

### Price — order of operations

The move is the sequence, not the comparison. Reversing it makes your price the anchor.

1. Name the alternative the prospect is already pricing against — including the indirect one they are not counting as a purchase (their own time, a professional appointment, doing nothing).
2. Establish its full cost: money, time, hassle, repetition.
3. Only then introduce yours.

### Benefits of the benefits — where to stop

The extension has a ceiling. **Over-extending strains believability and creates confusion** `[T p.80]`. Stop at the last benefit the prospect can verify from their own life: they have seen an electricity bill, so "lower electric bills" holds. They have not seen the holiday that the saving eventually pays for, so that link breaks the chain. One extension is usually right; two is the outer limit.

### Complexity — the restatement test

Read the mechanism line to someone outside the category and have them explain it back. If they cannot, it is not simpler yet — regardless of how accurate it is. Accuracy is not the constraint; repeatability is.

---

## Beliefs `[T p.80–81]`

Beliefs are formed over a lifetime and govern buying. Where the market already holds a negative opinion of the product or its category, **address it before they will consider the product at all** `[T p.80]`.

**Separate the two kinds first.** A *misconception* is a wrong idea about how the product works — correct it with information. A *belief* is a position they hold about the whole category — information does not move it; it needs one of the three ways below.

**Per-line discipline.** As each line is written, ask: *"how would my prospect handle that?"* `[T p.81]` Where the honest answer is a raised eyebrow, that is where the objection is born, and it must be resolved on that line rather than later.

### The insurance four-step `[T p.81]`

Objection: *"this is no different from other insurance."* The fix ran in this order:

1. Call out people who hold **that** insurance — explicitly, by what they already have.
2. Call out a little-known fact about their existing insurance that could cost them thousands.
3. Show people upset they did not know sooner.
4. **Then** show the product.

Result, in the book's words: *"we were able to address the objection before it became an objection."* Generalise the shape: qualify by their current solution → destabilise it with a specific, verifiable fact → show the emotional consequence of not knowing → introduce the product as the resolution. The product cannot appear before step 3 without collapsing the whole structure.

**Policy gate.** Step 2's shape — a little-known fact about a financial product that could cost you thousands — sits in `FINANCIAL_PRODUCTS_SERVICES` in 2026 and is close to the personal-attributes line. `shared/evidence.md` records that Meta's policy text was never retrieved, so nothing here clears it. Name the specific risk, cite the specific policy URL, and send it for a human read. Never assert a rule and never approve the copy on this plugin's authority.

### Renaming the category `[T p.81]`

Where the belief attaches to the *name*, change the name. The belief "all courses are scams" is why creators began selling **"systems"** — the same thing under a name the belief does not attach to. The constraint: rename only where the new name is true. A course called a system is still a course; if it is delivered as a course, the rename buys a click and loses the customer, and canon §8's ethics line applies.

### The three ways to overcome a belief `[T p.82]`

| Way | Execute it as | Use when |
|---|---|---|
| **Authority** | A person with standing in the market says it — a clinician in medical, or anyone the market already credits | The belief is technical, or risk of harm is the block |
| **Social proof** | Multiple people who held the objection and turned out to be wrong | The belief is "it won't work for someone like me" |
| **Directly calling it out** | Make the false belief the **hook**, then tell the story of one person who held it and was wrong | The belief is widespread, stated openly, and the market is tired of being sold to |

Directly calling it out is the strongest and the most demanding: the story has to be real, and the person has to be identifiable enough to be credible. Hand the hook itself to `hook-system`; specify the belief being flipped, not the wording.

---

## Making people buy now `[T p.83]`

For most-aware audiences on offer-led ads (canon §2's Offer flow). Four devices, each with a hard constraint.

| Device | Execute it as | Constraint |
|---|---|---|
| **Limited-time offer** | Tie it to a current event or season and **name the offer after something relevant to the audience** — the back-to-school special. Naming lifts relevance and urgency together | The window must be real and must close |
| **Price increase** | Be transparent. Announce it the day before | *"If you don't actually raise the price, you risk losing customer trust"* `[T p.83]`. Never announce a rise that does not happen |
| **Limited inventory** | State the number. A 25-seat mastermind, with emails showing the seats going | **Cap the order form at the number announced.** The cap is what makes the claim true rather than a tactic |
| **Reward for buying now** | Something extra for the first N buyers. The book's case: a free limited-edition $50 t-shirt to the first 100 Black Friday buyers → over $100,000 in sales within an hour | *"Be ethical — don't promise what you can't deliver"* `[T p.83]` |

**Two absolutes.** Do not promise what cannot be delivered. Do not announce a price rise that will not happen. Both are cheap to write and expensive to unwind, and both are recoverable-once at most.

Scarcity is also where fabrication is most tempting. Canon §8: no invented statistics, ever — that covers unit counts, seats remaining and buyer numbers. If the client cannot supply the number, the device is unavailable, not approximable.

---

## Higher-AOV scriptwriting `[T p.84]`

**The fundamentals do not change. The persona does** `[T p.84]`. Typical DTC sits at $25–150; high AOV starts around $1,000+. The mistake is treating the step-up as a pricing change and re-running the same script.

A higher-AOV persona has **different symptoms, different problems and different needs**, and therefore needs **different scripts and different visuals** — not the same ad at a higher price. The book's own case: the agency moved from clients who could barely afford $500/month to $10,000+/month by changing the persona to businesses already doing $100,000+/month — *"easier to make them more money, and easier to get them to pay $10,000"* `[T p.84]`.

Re-derive, in this order, before writing anything: the new persona's symptom → their problem → what they have already tried and why it failed → the objection that actually blocks them (rarely the same one) → the visuals that carry belief at that price. Send the persona work to `market-research` and the environment and casting implications to `creative-concepting` — perceived value in the frame has to match the new price point.

---

## Reference index

| Need | Load |
|---|---|
| Objection → diagnosis → move → worked case, for objections outside the three reasons | `references/objection-playbook.md` |
| The four-step template generalised, and the pre-ship gate | `references/objection-playbook.md`, last two sections |
| Where the objection layer sits in the script | `shared/canon.md` §2 |
| Policy risk in health, financial or political categories | `shared/evidence.md` |

## Handoffs

Objection language and frequency in from `market-research` — objections are found, not guessed. Mechanism simplification with `positioning-mechanisms`. Hook execution to `hook-system`. Placement in the script to `video-script-system`. Visual proof of the objection being answered to `creative-concepting`. Compliance and claim check at `prelaunch-qa`.
