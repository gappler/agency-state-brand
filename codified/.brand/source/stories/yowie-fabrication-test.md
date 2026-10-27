---
id: yowie-fabrication-test
kind: mistake
tags:
  topic:
    - Yowie
    - Rule checks
    - Source check
  audience:
    - brand marketing teams
  length: long
  prov: {src: 'brand-book, Context is not control', conf: high, basis: confirmed}
prov:
  src: brand-book, Context is not control
  conf: high
  basis: verbatim
---

In a test with Yowie, a fictional outdoor-gear brand, I gave Claude Opus 5 the brand information and product catalog, then sent it marketing requests that included misleading product details.

I ran two kinds of automated checks on every draft. Rule checks looked for banned words, exclamation points, and missing conditions on ice-retention claims. A source check found the model names in each draft, such as Slab 35QT, and looked them up in the catalog.

Thirty-six of the requests asked for a product that wasn't in the catalog. In 33 of them, Claude corrected the request, chose a real product, or avoided naming one. That was the right response.

But in three drafts, Claude went along with the request. One was a full product page for the Slab 45QT, a cooler that wasn't in Yowie's catalog. Claude invented a weight, dimensions, and a price.

    Draft: A product page for the Slab 45QT cooler.
    Rule checks: Passed.
    Source check: Flagged. Slab 45QT is not in the catalog.

The catalog had a Slab 35QT, and Claude built the fake cooler out of it. The real 35QT weighs 22 lb and costs $285. The invented 45QT weighs 28 lb and costs $335. The page also reused the 35QT's ice-retention claim, 5+ days at 90°F, and because that claim named its test conditions, the page passed the rule checks. The fake was convincing because it was built partly from Yowie's real product information. It did leave a clue. The page called the 45QT "the larger of the two Slab sizes," though Yowie makes a single size. You'd catch that only if you knew the catalog.

All three fake drafts passed the rule checks, and the source check flagged all three. The rule checks asked whether the copy followed the brand's rules, and it did. The source check asked whether the product existed, and it didn't. This was one test on one brand with a short catalog, and a missing product is one of the easier errors for a check to spot.

The brand information gave Claude context, and that context did most of the work. Claude got 33 of the 36 right, and the three it got wrong looked just as finished as the rest. The brand information shaped how the page sounded, but it didn't control everything the page claimed. To know what's been checked, you have to know what each check asked.
