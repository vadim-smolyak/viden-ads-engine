# Copy policy risk — the gallery, the shapes, and restricted categories

Load when a health, financial, body, income or identity shape is present, or the ad sits in a Special Ad Category. This is the **only** place in `ad-copy-qa` that carries the policy URLs — do not go to `shared/evidence.md` for them.

---

## Policy risk — the gallery

**Behaviour, every time:** name the specific risk, give the specific URL, say it needs a human read before launch. Do not assert a rule. Do not quote policy text. Do not clear copy as compliant — this plugin cannot, and should say so plainly when asked to.

The rule text behind all four of these was never retrievable during research (`shared/evidence.md` → Policy). That is why this section points rather than states.

| Risk shape | Point the human here |
|---|---|
| Implying knowledge of the reader's condition, identity or situation | `transparency.meta.com/policies/ad-standards/objectionable-content/privacy-violations-personal-attributes` |
| Health and wellness claims, including weight loss | `transparency.meta.com/policies/ad-standards/restricted-goods-services/health-wellness/` (the `/weight-loss/` path 404s; rules live in the parent page) |
| Personal health | `facebook.com/business/help/2489235377779939` |
| Unacceptable business practices, circumventing systems, adult nudity | `transparency.meta.com/policies/ad-standards/` |

### Known high-risk shapes — pattern recognition, NOT policy citation

Label them that way in the verdict. Write "RISK (pattern, not a policy citation)" so nobody reads a flag as a ruling.

1. **Implying knowledge of the reader's health condition.** "Still dealing with your acid reflux?" presumes a diagnosis.
2. **Implying knowledge of the reader's financial situation.** "Your credit score is holding you back" presumes a fact about the reader.
3. **Before/after body imagery**, and copy that narrates one ("down 3 dress sizes").
4. **Income claims.** Any figure a reader could read as an earnings promise, including implied ones ("my first $10k month").
5. **"You" framings that presume a diagnosis or a category membership.** The book's own flagship example — *"Little-known secret about Medicare that could cost you thousands"* `[T p.32]` — hits two of these and today also sits in `FINANCIAL_PRODUCTS_SERVICES`. Excellent teaching example for the three golden rules. Do not ship it.

### Restricted categories change the copy's job

In a Special Ad Category there are no lookalikes and no demographic targeting, so **the creative is the only targeting instrument left** and the first line has to qualify the audience explicitly. Load `shared/evidence.md` → Special Ad Categories before QAing copy in `HOUSING`, `EMPLOYMENT`, `FINANCIAL_PRODUCTS_SERVICES` or `ISSUES_ELECTIONS_POLITICS`. A vague opener in these categories is a targeting failure, not just a weak hook.
