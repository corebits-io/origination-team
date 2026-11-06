---
name: team-discovery
description: "Enumerate the population of companies the market map pointed at, from licence rosters, registers, association directories, certification lists and exhibitor lists, with a source on every row and a coverage log that names what the pull missed. Applies only geography and segment gates. Triggers on: find the companies, enumerate the population, build the long list, pull the rosters, find me 100 founder-owned businesses, run discovery, source companies in this segment, build the universe."
---

# Discovery

Discovery decides whose list this is. Pull from the sources the map named and
the list is yours; pull from the same databases everyone buys and the list is
everybody's. The companies worth finding are the ones with no marketing
budget, and they live in rosters and registers, not in lead databases.

**Read first:**
- `market-map-[segment]-[date].md` — especially Step 6, the source list
- `references/sourcing-directories.md` — the rules for using sources
- `templates/targets.csv` — the exact columns this skill fills
- `run-state.md` — in case a previous session already pulled some sources

---

## Step 1 — Set up the file

If `targets.csv` does not exist in the workspace, create it from
`templates/targets.csv`: keep the header row exactly, delete the example row.
Never change column names; every later skill addresses them by name.

## Step 2 — Pull whole sources, one at a time

For each source in the map's list:

- Pull the **whole segment slice**, not a search for names you recognise
- Record per company: `company`, `domain` (if listed), `hq_city`, `hq_state`,
  `country`, `sector`, `segment`, `source`, `source_detail`
- `source_detail` is specific enough to re-run: the roster name, the chapter
  or filter, and the pull date
- Update `run-state.md` after each source, with its row count

Caps and truncations happen. When a source caps at N results, say so in the
coverage log and narrow the query (by county, by letter, by category) until
the slices are complete, or record the gap honestly.

## Step 3 — Cross-find and dedupe

Merge duplicates across sources into one row carrying all its sources in
`source_detail`. Match on domain first, then on name + city with manual care:
"Precision Plating of Dayton" and "Precision Plating (Dayton)" are one
company; "Precision Plating" in two states is probably two.

A company found in two independent sources is weak evidence it is real and
active; note the multi-source rows, they are worth it later.

## Step 4 — The only two gates

Apply **geography** and **segment** from the buy box. Nothing else. No size
gate, no ownership gate, no website-quality judgment. There are no figures
yet, and excluding on an unrecorded headcount deletes the least-marketed
companies first.

Rows failing a gate stay in the file with `verdict: PASS` and the rule in
`fit_reason` (e.g. `PASS: HQ outside scope (TX)`). Rows are never deleted; a
geography PASS recorded today is a company not re-discovered next quarter.

## Step 5 — The coverage log

Write into the run state and the gate report:

- Every source pulled, rows before and after dedupe
- Every cap, truncation, paywall, login wall, and skipped source, each with
  what it likely cost
- A one-paragraph bias statement: given these sources, who is
  over-represented in this list, and who is missing

A truncated pull looks exactly like a complete one. The log is the only
defense.

## Step 6 — Judge the count

The run plan stated an expected population. Compare:

- **Within range** — proceed
- **Under 60 carried rows** — say which it is: the segment is genuinely small
  (the map said so), the sources under-cover it (name the missing source
  family), or the gates are tighter than the box intended. Do not hand over a
  thin list without the diagnosis
- **Over ~500** — the segment definition is too wide for one run; propose the
  narrowing rather than researching a thousand rows shallowly

---

## The gate

Show the user: counts by source, the dedupe result, the coverage log with the
bias statement, and 15 sample rows across different sources. Stop for
approval before any research phase begins. On approval, update `run-state.md`
to phase `fit-screen`.
