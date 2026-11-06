# Ranking rubric

Three verdicts, never scores. A number between 1 and 100 invites an argument
about whether a 71 beats a 68 and tells nobody what to do on Monday.

- **PRIORITY** — in mandate, with a dated reason to engage now
- **WATCH** — fits the thesis, needs a better trigger or a filled gap
- **PASS** — a tested fact excludes it, and the rule that fired is written
  next to the verdict

---

## The order of tests

Every row goes through the same tests in the same order. The first PASS rule
that fires ends the evaluation and is written into `fit_reason`.

### 1. Hard gates (any failure = PASS)

- **Ownership:** `sponsor_screen` not clear → PASS. Sponsor-owned is always
  PASS, no exceptions, including companies that still say "family owned" on
  the website years after the sale
- **Ownership type** verified outside section 5 of the buy box → PASS
- **Geography** outside section 3 → PASS
- **Segment** outside section 2 → PASS
- **A hard exclusion** from section 8, tested true on evidence → PASS
- **Economics:** a *verified* figure outside the size box → PASS

### 2. The estimate rule

A *labeled estimate* outside the size box → WATCH, never PASS. See
`references/estimation-rules.md`. Only verified figures exclude.

### 3. Fit and timing, kept separate

Fit is sections 2-8 of the buy box. Timing is the signal. They never trade:

- A loud signal never promotes an out-of-mandate company past a hard gate
- A missing signal never deletes an in-mandate company; it makes it WATCH

### 4. PRIORITY requires all of

- Every hard gate passed on evidence (not on absence of evidence)
- Ownership type evidenced at tier 1 or 2
- Size inside the box, verified or labeled estimate
- At least one signal inside its recency window, strength medium or high
- An identified owner (`owner_name` not `Not found`) — you cannot
  personalize outreach to nobody

Everything in mandate that misses one of these is WATCH, with the missing
piece named in `fit_reason` so the gap can be filled later.

---

## Soft negatives

Section 8 soft negatives are recorded in `fit_reason` and may demote
PRIORITY → WATCH when two or more stack. They never produce a PASS.

---

## Capacity sizing

Read section 10 of the buy box. The PRIORITY bucket should be roughly 2-3
months of the user's stated conversation capacity. If the rubric produces 3x
that, the rubric is flattering the list and the thresholds tighten (signal
strength, evidence tier) until the bucket is honest. The demoted rows go to
WATCH with `fit_reason: demoted on capacity`. Tightening is reported, never
silent.

If PRIORITY comes back under 5 rows, do not loosen the rules to fill it. Say
which test is binding. A short honest list beats a padded one.

---

## The audit

Ranking ends with a four-part audit, reported whether or not it is clean:

1. **Gate check** — re-test every PASS: does the named rule actually fire on
   the evidence in the row? Every PASS must cite a false fact, not a missing
   one
2. **Consistency check** — same facts, same verdict: sample pairs of similar
   rows and confirm they landed in the same bucket for the same reasons
3. **Estimate check** — no row was PASSed on an unverified number; every
   estimate outside the box is WATCH
4. **Capacity check** — PRIORITY count against section 10

Corrections are applied, counted, and reported. An audit that always comes
back clean is not reading anything.

---

## Nothing is deleted

A PASS row stays in `targets.csv` with the rule that excluded it, so the same
company is not rediscovered and re-researched in six months. The file is the
institutional memory of the search.
