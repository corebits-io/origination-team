---
name: team-outreach-prep
description: "Draft personalized outreach for each PRIORITY target, in the buyer's voice, built only from evidenced facts in the row. Writes drafts and a queue for a human to send by hand. Never sends anything and never finds or guesses contact details. Triggers on: draft the outreach, prepare personalized outreach, write the letters, outreach drafts, write to the owners, prep the first touches, build the outreach queue."
---

# Outreach Prep

Every draft this skill writes will, if things go well, be read by the exact
owner the whole run existed to reach. That is why the rules are strict: a
draft is built only from evidenced cells, it never exceeds its evidence, and
it is sent by a human, by hand, after reading every word. The system's job
ends at the queue.

**Read first:**
- `references/outreach-rules.md` — the ceiling, the never-list, the
  always-list, the tone
- `BUY-BOX.md` section 9 (outreach identity) and section 10 (capacity)
- `templates/outreach-queue.csv` — the queue columns

If buy box section 9 is empty, stop and get it filled. Drafts need a real
sender with a real credibility line; a draft from nobody is spam from anybody.

---

## Step 1 — Select and order

Drafting runs on PRIORITY rows only. Order by signal recency. Respect the
queue cap from `references/outreach-rules.md`: never more than two weeks of
the user's stated send volume in `drafted` status. The rest of PRIORITY
waits; they are listed, not lost.

## Step 2 — The personalization hook, per row

Before writing, name the hook: the one evidenced fact that makes this letter
about this company. It must be traceable to a cell (`signal`,
`ownership_evidence`, something the company says about itself). Write it into
`personalization_hook` in the queue, with its date.

If the row's only hook would require exceeding the evidence, send the row
back to the analyst with what is missing. The writer never fills a gap with
something plausible — personalization built on invented facts is the error
that reaches a human.

## Step 3 — Draft

One draft per row, in the channel the user actually uses (section 9), obeying
`references/outreach-rules.md` in full:

- The buyer's identity and credibility line, verifiable from their site
- Why this company specifically — the hook, not flattery
- The small honest ask, and the easy no
- 120-180 words for a letter; shorter for LinkedIn
- Plain English, speakable aloud, no exclamation marks, no valuation talk,
  no urgency, nothing from anyone's private life
- Signed by the real sender from section 9

Save each draft as `drafts/[company-slug].md` in the workspace. The draft
file carries, below the draft, the hook and every fact used with its source —
so the human sending it can check the letter against its evidence in thirty
seconds.

## Step 4 — The cross-draft check

Before queueing, compare every pair of drafts in the batch. If two drafts
share most of their sentences, the personalization is cosmetic: rewrite until
each letter could only have been written to its company. A hook that fits
two companies is a template, not a hook.

## Step 5 — Queue

Create or update `outreach-queue.csv` from the template (keep the header,
delete the example row on first use). One row per draft: `company`,
`owner_name`, `owner_role`, `verdict`, `channel`, `personalization_hook`,
`draft_ref`, `status: drafted`, `date_drafted`, `notes`. The only address
ever recorded is a registered office from a public filing, labeled as such,
in `notes`.

Update `targets.csv` `outreach_status` to `drafted` for queued rows.

---

## Where this stops

The queue, at `drafted`. The user reads each draft, finds the owner's actual
contact details with their own tools and their own compliance review, sends
by hand, and marks the queue row `sent-by-hand` themselves. This package
never sends, schedules, or automates a touch, and it never finds an email
address. That is a design decision, not a missing feature.

---

## The gate

Show the user every draft in full, each with its hook and evidence trail, and
the queue as a table. Stop for approval. On approval, write the files, update
`run-state.md` to phase `done`, and report the run's final funnel.
