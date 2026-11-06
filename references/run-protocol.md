# Run protocol

A full run over a real segment is hours of work spread across days. This file
is what lets a run survive a closed laptop, a new chat, or a context window
ending mid-phase.

---

## The state file

Every run writes `run-state.md` in the workspace folder, updated at the end
of every phase and every approved gate. It holds, in plain markdown:

```markdown
# Run state — [segment], started [date]

## Phase
discovery        <- one of: intake / market-map / discovery / fit-screen /
                    owner-research / signals / ranking / outreach-prep / done

## Last completed gate
market map approved [date]

## Counts
enumerated: 412   screened: Not started   ranked: Not started

## In-flight
discovery: NASF roster done (214), state manufacturer roster done (171),
exhibitor list in progress (27 of ~60 pages)

## Decisions made at gates
- [date] user approved run plan; scoped to OH/IN/MI only for this run
- [date] user approved map; verdict SOURCE IT; chrome-majority shops excluded

## Open questions for the user
- none
```

## Resuming

A new session starts by looking for `run-state.md`. If it exists, read it,
read `targets.csv`, confirm the phase with the user in two sentences, and
continue from the first incomplete item. Never restart a completed phase
because the chat is new. Never re-research a row that already has evidence.

## Batching

- Research phases (fit screen, owners, signals) run in batches of 20-30 rows,
  written to `targets.csv` after each batch, so an interruption costs one
  batch, not a phase
- The CSV is the source of truth. The state file points at it; it never
  duplicates row data

## Honesty under interruption

If a phase was interrupted mid-batch, the state file says which rows are
half-done. Half-done rows are re-done from the start of the row, because a
row that is half-researched and looks finished is worse than one not started.
