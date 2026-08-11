---
name: marketing-psychology
description: >
  This skill should be used when a VIDEN strategist needs a named psychological principle or mental
  model — to explain why an ad works, to pick the right lever for a stuck account, or to name the
  mechanism behind a winner so it can be reused. It is this plugin's single source of truth for named
  principles: 72 models across six categories, with a situation-to-model selection table so the right
  lever can be found without reading all 72. Trigger on "what's the psychology behind this", "why does
  this ad work", "which mental model applies here", "they keep saying it's too expensive, what's the
  play", "we need a stronger urgency lever", "how do we make this feel like a deal", "anchoring",
  "loss aversion", "social proof", "scarcity", "framing", "decoy pricing", "name the mechanism in this
  winner".
metadata:
  version: 0.1.0
---

# Marketing psychology

The plugin's named-principle library. **Other skills reference this one rather than redefining a principle** — if a hook tactic, a mechanic or an objection play needs the psychology named, the definition lives here and only here.

Never run a web search. These are established behavioural-science and business models, not 2026 platform facts; nothing here needs re-verification at runtime.

## Fast path (default)

**Do not read the model library.** Read the selection table below, pick one to three models, load only the one or two category files they sit in, and apply them. Two models applied well beat eight named.

## Deep path

Load a whole category file when auditing a piece of work for missed levers, when teaching, or when a diagnosis has resisted the obvious answers. Load more than one category only when the question genuinely spans them (pricing plus persuasion, for instance).

## Category index — load only what you need

| File | Models | Lines | What it covers |
|---|---|---|---|
| `references/foundational-thinking.md` | 14 | 59 | Strategy and diagnosis. Which problem to solve, where the constraint is, what would guarantee failure. |
| `references/buyer-psychology.md` | 22 | 91 | How buyers actually think, decide and misjudge. The largest and most-used file for creative work. |
| `references/persuasion.md` | 13 | 55 | The classic influence levers. What to do once you know what the buyer believes. |
| `references/pricing.md` | 5 | 23 | How price is perceived, framed and compared. |
| `references/design-and-delivery.md` | 10 | 43 | Behaviour design, friction, funnels and the systems around the ad. |
| `references/growth-and-scaling.md` | 8 | 35 | Compounding, loops, and why what works at one spend level stops working at another. |

## Selection table — situation to lever

| Situation | Models to reach for | File |
|---|---|---|
| Hook is not stopping anyone | Availability Heuristic, Zeigarnik Effect, Pratfall Effect, Curse of Knowledge | buyer-psychology |
| "It's too expensive" | Anchoring, Framing, Mental Accounting, Loss Aversion, Rule of 100 | persuasion + pricing |
| Nobody believes the claim | Authority Bias, Bandwagon / Social Proof, Contrast Effect, Pratfall Effect | persuasion + buyer-psychology |
| No urgency in the desire | Scarcity / Urgency Heuristic, Loss Aversion, Hyperbolic Discounting, Regret Aversion | persuasion + buyer-psychology |
| New category, nobody is looking for this | Jobs to Be Done, Curse of Knowledge, Mere Exposure, Status-Quo Bias | foundational + buyer-psychology |
| Crowded category, we look like everyone | First Principles, Inversion, Mimetic Desire, Unity Principle | foundational + buyer-psychology + persuasion |
| High ticket, long consideration | Commitment & Consistency, Foot-in-the-Door, Endowment Effect, Regret Aversion | persuasion + buyer-psychology |
| Retargeting audience that did not convert | Regret Aversion, Loss Aversion, Zeigarnik Effect, Status-Quo Bias | buyer-psychology + persuasion |
| Viewer paralysis, too many options or SKUs | Paradox of Choice, Hick's Law, Default Effect, Price Relativity | buyer-psychology + design + pricing |
| The offer needs to feel like a deal | Anchoring, Decoy Effect, Door-in-the-Face, Charm Pricing, Rule of 100 | persuasion + pricing |
| Justifying a premium price | Rounded-Price Effect, Contrast Effect, Price Relativity, Authority Bias | pricing + persuasion |
| Free trial, sample or freemium decision | Zero-Price Effect, Endowment Effect, IKEA Effect, Reciprocity | buyer-psychology + persuasion |
| Landing page loses them | Hick's Law, Activation Energy, BJ Fogg Behavior Model, Goal-Gradient Effect | design-and-delivery |
| Creative is forgettable | Peak-End Rule, Mere Exposure, Pratfall Effect, Availability Heuristic | buyer-psychology |
| Every test comes back flat | Local vs Global Optima, Theory of Constraints, Probabilistic Thinking, Survivorship Bias | foundational + growth |
| Account has plateaued at a spend level | Theory of Constraints, Law of Diminishing Returns, Exploration vs Exploitation, Critical Mass | foundational + growth |
| Winner is going stale | Mere Exposure, Peak-End Rule, Exploration vs Exploitation, Second-Order Thinking | buyer-psychology + growth + foundational |
| Brand is new and unknown | Mere Exposure, Authority Bias, Lindy Effect, Unity Principle | buyer-psychology + persuasion |
| Subscription churn | Endowment Effect, Switching Costs, Status-Quo Bias, Goal-Gradient Effect | buyer-psychology + growth + design |
| Naming the mechanism inside a winner | Start with buyer-psychology, then persuasion. The winner almost always ran one buyer model and one persuasion lever. | both |
| An incentive produced the wrong behaviour | The Cobra Effect, Second-Order Thinking, Goodhart-style metric drift via North Star Metric | design + foundational |

## How to apply a model (four steps, in order)

1. **Name the behaviour you want**, in one sentence, before choosing a model.
2. **Name what the buyer currently believes** that stops it. This is the input, not the model.
3. **Pick the model that operates on that belief** — not the one that sounds most impressive.
4. **Write the line, then check the model is still visible in it.** If the mechanism disappeared in the writing, the copy is decoration.

Then hand off: the model tells you *what lever*, `hook-system` tells you *what shape*, `video-script-system` tells you *where in the script it lands*.

## Cross-links — where these models are used, not redefined

**`hook-system`'s 8 psychological triggers are the hook-layer subset of this library.** A trigger is a model narrowed to the opening line; the model is the general case. Do not redefine a trigger here or a model there.

| `hook-system` trigger | Models underneath it |
|---|---|
| Pattern Interrupt | Availability Heuristic, Pratfall Effect, Contrast Effect |
| Identity Call-Out | Unity Principle, Liking / Similarity Bias, Mimetic Desire |
| Pain Agitation | Loss Aversion, Regret Aversion, Fundamental Attribution Error |
| Curiosity Gap | Zeigarnik Effect, Curse of Knowledge (inverted), Framing Effect |
| Social Proof / Credibility | Bandwagon Effect, Authority Bias, Mimetic Desire |
| Contrarian / Myth-Busting | Confirmation Bias, Contrast Effect, Framing Effect |
| Aspiration / Desire | Mimetic Desire, Hyperbolic Discounting, Goal-Gradient Effect |
| Urgency / Stakes | Scarcity Heuristic, Loss Aversion, Hyperbolic Discounting |

**`belief-objection-engineering`** owns the *sequence* — how to surface a belief, and how to answer it before it becomes an objection `[T p.81]`. This skill owns the *named mechanism* it uses to do that. When that skill calls for authority, social proof or a direct call-out, the definitions are in `references/persuasion.md`.

**`positioning-mechanisms`** owns mechanism-as-vehicle `[T p.26]`, which is a positioning concept and not one of these models. Canon §5 keeps those two words apart; do not conflate them.

## Constraints

- **One model per ad, usually.** The one-desire-one-avatar rule (canon §8) applies to psychology too. Stacking four levers in thirty seconds produces an ad that remembers none of them.
- **Never dress a model up as evidence.** "Loss aversion says losses feel twice as painful" is a description of a research finding, not a performance prediction for this ad. Do not attach percentages to it, and do not invent one (canon §8).
- **The ethics line is canon §8 and it applies hardest here.** Every model in this library is a way of moving a person who has not asked to be moved. Use them to make a true thing land, never to make an untrue thing believable.
