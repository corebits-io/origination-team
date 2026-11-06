---
name: team-fit-screen
description: "Screen every discovered company against the buy box: verify what the company actually is, establish ownership type with the sponsor screen, and size it under the estimation rules. Filters out businesses that do not fit, on evidence, never on absence of evidence. Triggers on: screen the list, filter out companies that do not fit, run the fit screen, check ownership, is it founder owned, size these companies, which of these fit my buy box, sponsor screen."
---

# Fit Screen

This is where "filters out businesses that don't fit" has to mean something.
The screen drops companies on facts that are false, never on facts that are
absent — because the companies that publish nothing are the proprietary ones,
and a screen that punishes silence deletes exactly the rows the run exists to
find.

**Read first:**
- `references/evidence-rules.md` — tiers, attribution, `Not found`
- `references/estimation-rules.md` — how to size companies that publish nothing
- The market map — segment economics and the consolidator list
- `run-state.md` — which batch is next

Work in batches of 20-30 rows. Write the batch to `targets.csv` before
starting the next. Update `run-state.md` per batch.

---

## Step 1 — Identity: what is this company?

Open the company's own site (or register entry when there is no site). Three
checks before anything is recorded:

1. **Attribution.** Is this page about this company? Name collisions,
   franchise pages, and brand sites answer for the wrong entity. Anchor on
   domain, HQ city, or a named officer
2. **Segment confirmation.** Does what it actually does match the segment
   definition? Fix `segment` or mark the gate result accordingly
3. **Liveness.** A dead site is not a dead company. Check the register before
   concluding anything; a fetch failure is never a verdict

## Step 2 — Ownership type and the sponsor screen

Fill `ownership_type` (founder-owned / family-owned / management-owned /
ESOP / sponsor-owned / corporate subsidiary / `Not found`) and
`ownership_evidence` with the tier-1-or-2 evidence and its tier.

Then the **sponsor screen**, on every row including the obvious-looking ones,
because companies keep the family-owned language for years after a sale:

- Search the company name with acquisition terms and against the map's
  consolidator list
- Check the news trail, not just the website. Judge direction from the text:
  who bought whom
- Result in `sponsor_screen`: `clear`, `sponsor-owned ([who], [date],
  [source])`, or `unresolved ([what conflicts])`

A row with `sponsor_screen` not `clear` will PASS at ranking. Record it and
move on; do not research it further.

## Step 3 — Size, under the estimation rules

Fill `est_revenue`, `est_ebitda`, `size_basis`, `financial_confidence`
exactly as `references/estimation-rules.md` prescribes: ranges, labeled
bases, the segment economics from the map, the sanity checks. `Not found`
where no defensible basis exists — a blank basis beats an invented one.

## Step 4 — Platform or add-on

Fill `fit_role` from buy box section 6: `platform`, `add-on ([named
platform])`, or `Not found`. For add-ons, additive means what section 6 says
it means; name the specific capability, certification, or metro.

## Step 5 — Test the exclusions

Test each hard exclusion from buy box section 8 against the evidence
gathered. Record tested-true exclusions in `fit_reason` material; record soft
negatives too. Do not assign verdicts — that is the ranking skill's job, with
the whole file in view. This skill gathers the facts the rubric will fire on.

---

## The gate

After each batch, show: rows screened, `ownership_type` distribution,
`sponsor_screen` hits, size-confidence distribution, rows where identity
could not be confirmed, and 5 full sample rows. Stop for approval per batch.
After the final batch, update `run-state.md` to phase `owner-research` and
report the headline: how many rows remain in-mandate on current evidence.
