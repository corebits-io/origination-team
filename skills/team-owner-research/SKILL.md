---
name: team-owner-research
description: "Identify who actually owns each in-mandate company, from public sources, with a wrong-person gate on every name. Establishes the owner's name, evidenced role and tenure. Never finds or guesses contact details and never touches a person's private life. Triggers on: identify the owners, who owns these companies, owner research, find the decision maker, who do I write to, research the owner, put a name on each company."
---

# Owner Research

Outreach is personal or it is spam, and it cannot be personal without knowing
who the person is. This skill puts an evidenced name on every in-mandate row.
It is also the skill with the sharpest edges in the package: a wrong name, an
invented title, or a detail from someone's private life each turns a good
letter into a bad moment — in front of the exact person the run existed to
reach.

**Read first:**
- `references/owner-research-rules.md` — every rule in it, before the first row
- `references/evidence-rules.md` — tiers and attribution apply to people too
- `run-state.md` — which batch is next

Run only on rows still in-mandate after the fit screen (skip rows whose
screen results already guarantee a PASS: sponsor-owned, failed geography,
tested-true exclusions). Work in batches of 20-30. Write each batch before
the next.

---

## Step 1 — Gather candidates

For each company, from acceptable sources only:

- The register: officers, agents, incorporators (tier 1)
- The company site: about, team, history pages (tier 2)
- The owner in their professional capacity: trade press, conference bios,
  their own LinkedIn summary (tier 2-3)

Collect candidate names with role claims and where each claim comes from.

## Step 2 — The wrong-person gate, per name

Run all four checks from `references/owner-research-rules.md`:

1. Name + company co-occur in tier 1 or 2
2. Same-name collision check
3. Generational check (Sr/Jr/III, family names across officers)
4. Tenure sanity

A name that fails any check is not written. The row gets
`owner_name: Not found` and a note in `owner_evidence` saying what
conflicted, so the next pass does not repeat the work.

## Step 3 — Record

- `owner_name` — the person, or `Not found`
- `owner_role` — only a stated title (the person or the company said it), or
  the evidenced relationship ("registered agent and incorporator"). Never a
  title inferred from a database field or press shorthand
- `owner_evidence` — the source(s) with URL and tier. If the registered
  office address was recorded for the outreach queue, it is labeled
  "registered office, [register], [date]" — the only address this system
  ever records

Multiple owners: record the most evidenced operator-owner in the columns and
the others in `owner_evidence` ("co-owned with [name], same filing"). The
outreach skill writes to one person.

## Step 4 — Harvest the signals you tripped over

Owner research surfaces succession language constantly: "second generation",
"40th anniversary", a GM promoted to president. Do not analyse these here —
but record each verbatim with URL and date in a working note for the signals
skill, so the next phase does not re-crawl the same pages.

---

## What this skill never does

- No email addresses, guessed, patterned, or "verified"
- No phone numbers, no home addresses
- No age, health, family, wealth, or anything else from private life
- No pretexting, no scraping behind logins that forbid it
- No title the person never claimed

`Not found` on an owner is a real result. It makes the row WATCH at ranking
(you cannot personalize outreach to nobody), and WATCH is recoverable; a
wrong-person letter is not.

---

## The gate

Per batch, show: names found vs `Not found`, the evidence tier distribution,
every row where the wrong-person gate fired and why, and 5 full sample rows.
Stop for approval per batch. After the final batch, update `run-state.md` to
phase `signals`.
