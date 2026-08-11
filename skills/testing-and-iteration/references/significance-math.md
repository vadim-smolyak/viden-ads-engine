# Significance math — sample size, Z-tests, and validity

Load this when someone claims a winner, asks how long a test needs to run, or wants a sample-size number. Everything here is arithmetic on the user's own data — never a benchmark, never an assumed baseline.

---

## Sample size per variation

```
n = 2 × (Zα/2 + Zβ)² × p(1-p) / δ²

n   = sample size per variation
Zα/2 = 1.96 (95% confidence) or 2.58 (99%)
Zβ  = 0.84 (80% power) or 1.28 (90%)
p   = baseline conversion rate (the client's own, from BigQuery or the account)
δ   = minimum detectable effect, ABSOLUTE (a 20% relative MDE on a 5% baseline is δ = 0.01)
```

**Quick reference — computed from the formula above at 95% confidence, 80% power.** These are arithmetic, not benchmarks:

| Baseline CR | 10% relative MDE | 20% relative MDE |
|---|---|---|
| 2% | ~78,000 / variation | ~19,500 / variation |
| 5% | ~30,000 / variation | ~7,500 / variation |
| 10% | ~14,300 / variation | ~3,600 / variation |

**Read the implication out loud.** At a 2% baseline and a realistic 10% effect, a creative test needs ~78,000 sessions per variation. Most creative tests in most accounts will **never** reach significance on purchase rate. That is not a reason to skip the math — it is the reason canon §7 has a fast lane. Do the arithmetic, report the required n, and then say plainly which lane the decision actually rests on.

**Converting n to runtime.** `days = n / (daily traffic to that variation)`. If the answer exceeds the test window the account can afford, say so before launch, not after.

---

## Significance test — two proportions

```
SE       = √( p × (1-p) / n )         per variation
Z-score  = (pB - pA) / √( SE²A + SE²B )

|Z| > 1.96  → significant at 95%
|Z| > 2.58  → significant at 99%
```

Report the **confidence interval on the lift**, not just the verdict. A significant result with an interval spanning +2% to +38% is a weak instrument, and saying so is more useful than the checkmark.

Distinguish **statistical** significance from **practical** significance every time. A statistically clean 3% lift that doesn't change what the account can spend is not a winner under canon §7's strategic definition.

---

## Validity checklist — all five, before any winner claim

- [ ] **Ran 14 days minimum.** Shorter windows carry day-of-week structure. 7 days buys a directional read only.
- [ ] **Required sample size met** before concluding, computed from the client's own baseline.
- [ ] **No peeking.** Repeatedly checking and stopping when the line looks good pushes the false-positive rate materially above the nominal α — the more often you look, the more likely you stop on noise. Either fix the stopping point in advance, or use a method built for continuous monitoring (below).
- [ ] **Split was random and consistent** for the whole window. Mid-test budget changes, audience edits, or a new ad added to the same ad set all break this.
- [ ] **No external confounds** — promotions, outages, PR, seasonality, a competitor's sale, a shipping cutoff. `campaign-troubleshooting` covers the calendar and fulfilment checks that most often turn out to be the real cause.

Any unchecked box: report the result **with the caveat attached to the number**, not in a footnote.

---

## Frequentist or Bayesian

| Situation | Approach |
|---|---|
| Large samples, single yes/no decision | Frequentist |
| Continuous monitoring, early stopping wanted | Bayesian |
| The result goes in a client document or a contract | Frequentist |
| You need a probability statement ("82% likely to be better") | Bayesian |

Pick before the test starts. Switching after seeing the data is peeking with extra steps.

---

## What the math cannot fix

**Platform-reported conversions are not a clean measurement.** Canon §7 governs. Meta's incremental attribution "drove a 24% increase in incremental conversions compared to our standard attribution model" (Meta Newsroom, 28 Jan 2026) — two Meta models, 24% apart, and the Insights default window is `["1d_view","28d_click"]`. Running a Z-test on numbers from two different models or windows is arithmetic on incomparable inputs. State model and window, and never mix them inside one comparison.

**Haus (640 Meta incrementality experiments, 28 Jul 2025):** 58% of brands saw higher iROAS on Manual than Advantage+; forcing a 50/50 split cost 18% iROAS. Platform-reported and causal results routinely diverge — a significance test on platform numbers is a test of the platform's numbers.

**Denominator hygiene.** Hook rate is whatever the tool defines it as (canon §5) — check the denominator before comparing anything across tools, and never compute it on assets short enough that the definition breaks down.

---

## Worked example

**Input.** New hook tested. Control 10,000 sessions / 250 conversions. Variant 10,000 / 300. Ran 7 days.

```
pA = 0.0250   pB = 0.0300
SE_A = √(0.025 × 0.975 / 10000) = 0.00156
SE_B = √(0.030 × 0.970 / 10000) = 0.00171
Z    = (0.0300 - 0.0250) / √(0.00156² + 0.00171²) = 0.005 / 0.00231 ≈ 2.16
```

**Report it like this:**

> Relative lift +20% (2.50% → 3.00%). Z ≈ 2.16, significant at 95%, not at 99%. Confidence interval on the lift is wide — roughly +2% to +38% — so the effect size is poorly estimated even though the direction is credible.
>
> **Validity: 2 of 5 boxes fail.** Runtime is 7 days, under the 14-day floor, so day-of-week structure is unaccounted for. Power at this n and effect size is around 60%, below the 80% the sample-size figure assumed.
>
> **Decision.** This is a valid *directional* read: keep the variant running and build the next iteration on it. It is **not** a significance claim and must not be written up as one. Extend to 14 days before it goes in a client document.
>
> Attribution: unified ad-set setting, `1d_view`/`28d_click`.

That last line is not optional. A conversion number without its model and window is not a number.
