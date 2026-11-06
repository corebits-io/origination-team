---
description: Run the full origination chain — buy box to drafted outreach — with an approval gate before every write
argument-hint: "[optional: a segment or geography to scope this run]"
---

# Run the origination team

Run the full origination chain for the buy box in this folder. Scope for this
run, if the user gave one: `$ARGUMENTS`

You are driving eight skills across four phases. Each skill stops and shows
its output before it writes anything. Do not skip a gate, do not batch the
gates together at the end, and do not continue past a step the user has not
approved.

## Before you start

1. Look for `run-state.md` in this folder. If it exists, this is a resumed
   run: read it, read `targets.csv`, confirm the phase with the user in two
   sentences, and continue from the first incomplete item per
   `references/run-protocol.md`. Never restart a completed phase
2. Read `BUY-BOX.md` in this folder. If it does not exist, say so and offer
   to fill one out section by section from `templates/BUY-BOX.md`. Do not
   research anything first
3. Read, in order: `references/evidence-rules.md`,
   `references/estimation-rules.md`, `references/ranking-rubric.md`,
   `references/sourcing-directories.md`,
   `references/owner-research-rules.md`, `references/outreach-rules.md`,
   `references/run-protocol.md`

The `references/` files live in the cloned repo, not in this folder. If you
cannot find them, ask the user for the path to their clone rather than
proceeding without them.

## The run

**1. `team-buy-box-intake`**
Check the box, run the principal-buyer gate, challenge the untestable
must-haves, write the run plan.
→ Gate: the run plan and every challenge. Stop for approval.

**2. `team-market-map`**
Segment definition, population and fragmentation, segment economics, the
typical owner, who is already consolidating, where the companies are
findable, verdict.
→ Gate: the map and the verdict. Stop for approval.
→ If the verdict is DO NOT SOURCE IT, stop the run there and say why.

**3. `team-discovery`**
Enumerate from the sources the map named. Cross-find, dedupe, apply only the
geography and segment gates, write the coverage log.
→ Gate: counts by source, the coverage log, 15 sample rows. Stop for
approval.

**4. `team-fit-screen`**
Identity, ownership type, the sponsor screen, labeled size estimates,
platform or add-on role, exclusion tests.
→ Gate per batch of 20-30 rows. Stop for approval.

**5. `team-owner-research`**
The named owner behind the wrong-person gate, evidenced role, nothing from
anyone's private life, no contact details.
→ Gate per batch. Stop for approval.

**6. `team-seller-signals`**
The four families — leadership, financing, growth, hiring — quoted verbatim,
sourced, dated, and aged against their recency windows.
→ Gate per batch. Stop for approval.

**7. `team-ranking`**
Build the rubric, get it approved before ranking a single row, rank in the
fixed order, size PRIORITY against capacity, run the four-part audit.
→ Gate: the rubric before ranking. Then the ranked list with the full audit.

**8. `team-outreach-prep`**
Hooks, drafts built only from evidenced cells, the cross-draft check, the
queue.
→ Gate: every draft in full with its evidence trail, and the queue. Stop for
approval.

## What you hand over at the end

- `targets.csv` — every row ranked, with the rule that ranked it
- The PRIORITY rows summarised in chat, each with its owner, its signal, and
  its gap if any
- `drafts/` — one file per PRIORITY draft, evidence trail attached
- `outreach-queue.csv` — everything in `drafted` status, nothing sent
- `market-map-[segment]-[date].md` and `rubric-[segment]-[date].md`
- The audit in full, including every correction it produced
- `run-state.md` at phase `done`

## Rules that hold across the whole run

- **Never fabricate.** No invented domains, headcounts, quotes, URLs, owner
  names or revenue figures. `Not found` is a real answer and the most common
  one
- **Unknown is not failed.** A gap ranks as a gap, never as a negative
- **Estimates are labeled, and the label travels with the number**
- **Sponsor-owned is always PASS**
- **Fit and timing stay separate**
- **Signals are quoted verbatim or they do not exist**
- **Nothing about any person's private life; no contact details, ever**
- **Public sources only**
- **Rows are never deleted**, only ranked
- **Nothing is ever sent.** The run ends at a queue a human works by hand

## Where this stops

At the drafted queue. Finding contact details, sending, and handling replies
are the user's job, by hand, with their own tools and their own compliance
review. When the user asks for the next step, say that plainly rather than
improvising it.
