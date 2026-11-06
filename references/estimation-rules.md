# Estimation rules

Most companies worth calling publish no financials. If the system can only
rank companies that publish numbers, it ranks the marketed ones and misses the
point. So it estimates — under rules that keep an estimate from ever being
mistaken for a fact.

---

## The one law

**Estimates are labeled, and the label travels with the number.**

`est_revenue` and `est_ebitda` are ranges, never points. `size_basis` states
how the range was built, specifically enough that someone else could rebuild
it. `financial_confidence` states how much to trust it. If a number moves to
another document — a ranking note, an outreach brief, a partner memo — the
label moves with it.

---

## How to build a size estimate

In order of preference:

1. **A verified figure.** The company or a filing states revenue or EBITDA.
   Rare. `financial_confidence: verified`
2. **Headcount x segment revenue-per-head.** The workhorse. Headcount from a
   state manufacturer roster, a licence filing, or the company's own site;
   revenue-per-head from the market map's segment economics, which must be
   sourced and dated. `financial_confidence: medium`, or `high` if headcount
   is tier 1
3. **Physical capacity.** Plant square footage, fleet size, seat count,
   number of locations — times a sourced segment benchmark.
   `financial_confidence: medium` at best
4. **A tier 4 database figure.** Recorded, labeled
   `financial_confidence: low`, and never the sole basis for a PASS

EBITDA is estimated as segment typical margin applied to the revenue range,
and the margin source is named in `size_basis`. If the market map could not
source a segment margin, `est_ebitda` is `Not found` — not a guess.

---

## What an estimate may and may not cause

| Situation | Verdict effect |
|---|---|
| Verified figure inside the box | normal ranking |
| Verified figure outside the box | PASS on economics |
| Labeled estimate inside the box | normal ranking |
| Labeled estimate outside the box | **WATCH, never PASS** |
| No figure and no basis for one | `Not found`; ranked on everything else |

Only a verified figure excludes on economics. An estimate is the system's own
work product; the system does not get to delete a company on the strength of
its own guess.

---

## Sanity checks that run on every estimate

- Revenue-per-head outside 0.5x to 2x the segment benchmark gets re-derived
  or discarded
- A single-digit headcount with a mid-eight-figure revenue estimate is
  contradictory; the row keeps the headcount, drops the estimate, and gets
  flagged in the audit
- Estimates never compound silently: an estimated revenue times an estimated
  margin is the floor of confidence (`low` x anything = `low`)
- When two bases disagree by more than 2x, write both in `size_basis` and
  take the wider range
