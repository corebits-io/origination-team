---
name: team-ranking
description: "Build a ranking rubric from the buy box, get it approved before ranking a single row, rank every row identically into PRIORITY / WATCH / PASS, then audit the ranking and report the audit whether or not it is clean. Triggers on: rank the list, prioritize the targets, which companies first, build the rubric, PRIORITY WATCH PASS, score the list, who do I contact first, rank my targets."
---

# Ranking

Ranking is where research becomes a decision, and where a bad system quietly
flatters its user. This skill ranks every row by the same written rubric, in
a fixed order, and then audits itself out loud. If the rubric is flattering
the list, the audit says so.

**Read first:**
- `references/ranking-rubric.md` — the law this skill applies
- `BUY-BOX.md` — sections 5, 8 and 10 especially
- `run-state.md`

---

## Step 1 — Build the run's rubric

Instantiate `references/ranking-rubric.md` with this buy box's specifics:
each hard gate with the exact criterion it tests, the soft negatives, the
PRIORITY requirements, and the capacity number from section 10.

Write it as `rubric-[segment]-[date].md` — but show it to the user first.

**Gate: the rubric is approved before a single row is ranked.** Changing the
rubric after seeing the results is how a list gets curated instead of ranked;
if the user wants a change later, re-rank everything under the new rubric and
say so in the file.

## Step 2 — Rank, in the fixed order

For every row, run the tests in the rubric's order: hard gates, the estimate
rule, fit-and-timing separation, the PRIORITY requirements. First PASS rule
that fires ends the evaluation.

- `verdict` — PRIORITY / WATCH / PASS
- `fit_reason` — the rules that fired, compactly, so a verdict can be argued
  with in March. A WATCH names its gap ("no signal in window", "owner Not
  found", "estimate below box"). A PASS names its rule and the false fact

Identical facts must produce identical verdicts. If judgment is needed, the
rubric was incomplete: fix the rubric (with the user), do not freelance row
by row.

## Step 3 — Capacity sizing

Compare the PRIORITY count to section 10 as the rubric prescribes: tighten
honestly and visibly if 3x capacity; never pad a short list. Report what was
tightened and every row demoted by it.

## Step 4 — The audit

Run all four parts from `references/ranking-rubric.md`:

1. Gate check — every PASS cites a false fact, not a missing one
2. Consistency check — similar rows, same bucket, same reasons
3. Estimate check — no PASS on an unverified number
4. Capacity check

Apply corrections, count them, and report the audit in full **whether or not
it is clean**. An audit that always comes back clean is not reading anything.

---

## The gate

Show the user: the funnel (enumerated → screened → in-mandate → with owner →
with signal → PRIORITY / WATCH / PASS, with arithmetic that adds up), every
PRIORITY row summarized in two lines each (who, why, the signal, the gap if
any), the audit in full with its corrections, and the demotions from capacity
sizing.

Stop for approval. On approval, write the verdicts to `targets.csv`, save the
rubric file, and update `run-state.md` to phase `outreach-prep`.
