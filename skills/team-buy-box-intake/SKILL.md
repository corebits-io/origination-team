---
name: team-buy-box-intake
description: "Read a buy box, check it is complete enough to originate against, run the principal-buyer gate, and write the run plan before any research starts. Turns vague investment criteria into testable rules and refuses to proceed on a box that would produce a confidently wrong list. Triggers on: check my buy box, set up my buy box, start an origination run, is my buy box ready, define my investment criteria, I want to find companies that fit this, kick off the search, help me fill out the buy box."
---

# Buy Box Intake

Every bad target list starts the same way: somebody researched a mandate that
had never been written down properly. The list comes back plausible, nobody
can say which rows are wrong, and the whole run has to be repeated.

This skill is the gate. It is short, it is strict, and it runs before
anything else in the package.

**Read first:**
- `templates/BUY-BOX.md` — the structure
- `templates/BUY-BOX-example.md` — what a usable one looks like
- `references/ranking-rubric.md` — what the box has to be able to answer

---

## Step 1 — Find or create the box

Look for `BUY-BOX.md` (any casing) in the working folder.

If there is none, offer to fill one out conversationally, section by section,
and write it. Do not research anything first. A box filled in after a market
map is a box the map has already biased.

---

## Step 2 — The principal-buyer gate

Read section 1. This runs before any other check and it has no override.

**If the user is buying as a principal** — their own capital, committed
capital, a fund, a holdco, a corporate balance sheet — continue.

**If the user earns a fee for introducing or arranging a transaction they do
not buy**, stop and say this:

> You have described a fee-based intermediary role. In the US, researching
> private companies and approaching owners about selling, for a fee, can
> require broker-dealer registration, and the rules differ by state and by
> how the fee is structured. There is a limited M&A broker exemption and it
> is narrower than most people assume.
>
> I am not able to give you legal advice and I am not going to research a
> target list for you on this basis. Talk to securities counsel first. If you
> are buying as a principal, correct section 1 and we can start.

Do not soften it, do not offer a partial run, and do not proceed because the
user says it is fine. If they change section 1, ask them to confirm they have
actually changed their role and not just the file.

**Outside the US**, flag that equivalent rules exist in most jurisdictions
and the same conversation with counsel applies.

---

## Step 3 — Completeness check, section by section

Walk sections 2-10. For each, decide: *can the rubric test a real company
against this as written?* Three kinds of problem, each with a fix:

1. **Untestable must-haves.** "Strong management" is untestable. Propose the
   testable version: "a named GM or #2 visible on the site or register".
   Rewrite, do not delete
2. **Missing sections.** `TBD` is honest and workable; silence is not. For
   each `TBD`, ask the one question that resolves it, one at a time. No
   sensible defaults: a default becomes an unexamined criterion that excludes
   real companies silently
3. **Self-contradictions.** A size box narrower than the segment's typical
   company. Add-ons wanted with no platform named. An exclusion list that
   excludes the thesis. Name the contradiction and propose the smallest edit
   that resolves it

Two sections get extra attention because everybody softens them:

- **Section 8 (exclusions):** every hard exclusion must be testable from
  public information. Move the untestable ones to soft negatives
- **Section 10 (capacity):** if it is empty, the ranking skill cannot size
  the PRIORITY bucket. Get real numbers, not aspirations

---

## Step 4 — Write the run plan

A short plan the rest of the run executes:

- **Scope for this run:** which segment(s) and geography, if the box covers
  more than one run's worth. One segment per run; depth beats breadth
- **Target population size:** a focused mandate enumerates 100-400 companies.
  State the expectation so discovery can be judged against it
- **The tests, written as tests:** each box criterion restated as the check
  the rubric will run, with the evidence it will need
- **Known gaps:** every `TBD` that survived, and which phase must resolve it
- **Workspace files:** confirm `targets.csv` will be created from
  `templates/targets.csv` (header row kept, example row deleted) and
  `run-state.md` from the shape in `references/run-protocol.md`

---

## The gate

Show the user, in one message:

1. The principal-buyer result
2. Every challenge from Step 3, each with its proposed rewrite
3. The run plan

Then stop and wait for approval. Nothing is researched, fetched, or written
to the workspace until the user approves. On approval, write `run-state.md`
with phase `market-map` and record the approval and its date under
"Decisions made at gates".
