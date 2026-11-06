---
name: team-market-map
description: "Map the segment a buy box implies before any company is enumerated: fragmentation, who is already consolidating, the typical owner profile, the segment economics every later estimate depends on, and where the population is actually findable. Ends with a verdict that is sometimes do-not-source-this-segment. Triggers on: map the market, map my target markets, market map, how fragmented is this segment, where do I find these companies, is this segment worth sourcing, who is consolidating this space, segment economics."
---

# Market Map

The map is not optional context. It produces four inputs the run cannot
proceed without: the segment economics that price every estimate, the source
list discovery will pull, the consolidator list the sponsor screen checks
against, and a verdict on whether this segment is worth sourcing at all.

Get the map wrong and every later estimate is sized against the wrong
benchmark — quietly, on every row at once.

**Read first:**
- The approved run plan (in `run-state.md`)
- `references/sourcing-directories.md` — the source families to look for
- `references/estimation-rules.md` — what sizing will need from this map
- `references/evidence-rules.md` — everything here is sourced and dated too

---

## Step 1 — Define the segment precisely

Write the segment definition as an inclusion test a stranger could apply:
what the company does for whom, what it is often confused with, and the
confusions excluded by name. The buy box's section 2 wording is the start,
not the answer.

## Step 2 — Population and fragmentation

Estimate how many companies fit the definition inside the geography, from
enumerable sources (roster sizes, association membership counts, register
queries), not from market reports' vague "thousands". State the basis.

Then the structure: share of the top handful if readable, whether a typical
metro supports one shop or ten, and what that implies for platform vs add-on.

## Step 3 — Segment economics

The numbers every size estimate will be built on. Each one sourced and dated:

- **Revenue per employee** for a typical operator (trade association surveys,
  trade press benchmarks, public comparables scaled down with a stated haircut)
- **Typical EBITDA margin range**, same discipline
- **What size the segment's companies cluster at**, so the box can be sanity
  checked against reality

If revenue-per-head and typical margin are both `Not found` after a real
search, say so in the verdict. Sizing will stop, and it is better to know now.

## Step 4 — The typical owner

Who owns these companies, structurally: founder generation or second, how
owners exit today (competitor sale, family transition, consolidator), and the
trade's own language for transition. This shapes owner research and the
recency windows that matter most.

## Step 5 — Who is already consolidating

Name the active consolidators and sponsor-backed platforms in the segment and
geography. Two uses, both downstream: the sponsor screen checks acquisitions
against this list, and a crowded consolidator field is itself map output the
user should see.

## Step 6 — Where the population is findable

The concrete source list for discovery, chosen from the families in
`references/sourcing-directories.md`: the actual rosters, registers,
directories, certification lists, and exhibitor lists for this segment and
geography, each with a note on expected coverage and known bias. Every source
over-represents something; name what.

## Step 7 — The verdict

One of:

- **SOURCE IT** — population, economics, and sources all support a run
- **SOURCE IT, NARROWED** — with the specific narrowing (geography,
  sub-segment) and why
- **DO NOT SOURCE IT** — too few operators inside the box, mostly
  sponsor-owned already, no readable ownership information, or no source that
  enumerates the population. Say which, with the evidence

A mapper that always says SOURCE IT is not reading anything. "Do not source
this segment" is worth more than a list, because it is a fortnight of
associate time not spent proving it the slow way.

---

## The gate

Write `market-map-[segment]-[date].md` in the workspace **only after** showing
the user: the segment definition, population estimate with basis, the
economics with sources, the owner profile, the consolidator list, the source
list, and the verdict.

Stop for approval. If the verdict is DO NOT SOURCE IT and the user approves,
the run ends here and `run-state.md` records why. On a SOURCE IT approval,
update `run-state.md` to phase `discovery`.
