---
name: team-seller-signals
description: "Find and record dated, verbatim, sourced seller-intent signals for every in-mandate company: leadership and succession language, financing events, growth events, and transition-shaped hiring. Ages every signal against a per-family recency window. Triggers on: find seller intent signals, track seller signals, timing signals, who might sell, succession signals, reasons to call this quarter, which owners are ready, signal research."
---

# Seller Signals

A target list without timing is a phone book. The signal is the dated reason
to start this conversation this quarter rather than next year — and it is
also the easiest thing in the file to fabricate by over-reading. This skill
exists to find real signals and to refuse to improve them.

**Read first:**
- `references/evidence-rules.md` — the verbatim rule and the recency windows
  are the whole law of this skill
- The owner-research working notes — signals already tripped over
- `run-state.md` — which batch is next

Run on in-mandate rows, batches of 20-30, written per batch.

---

## Step 1 — Search the four families

For each company (and its named owner, professional capacity only):

| Family | What to look for |
|---|---|
| **leadership** | succession language, anniversary retrospectives, retirement language, a long-time #2 promoted, "next generation" phrasing, obituary-adjacent transitions handled respectfully or not at all |
| **financing** | UCC filings and releases, announced credit facilities, sale-leasebacks of the plant |
| **growth** | expansions, new facilities, major contract awards, new certifications |
| **hiring** | postings that imply transition: General Manager, President, "succession", a first-ever sales leader |

Search trade press, local business journals, the register's filing trail, the
company's own news page, and posting boards. Tier 4 sources never produce a
signal.

## Step 2 — Record under the verbatim rule

For the strongest signal per row (note others in working notes):

- `signal` — the exact words in quotation marks plus one clause of neutral
  context. If there are no exact words, there is no signal
- `signal_family` — leadership / financing / growth / hiring
- `signal_date` — the date of the source, ISO format
- `signal_url` — opened and read during this run, not reconstructed
- `signal_strength` — high / medium / low / `Not found`, judged on
  specificity, recency inside the window, and source tier

What never happens here: "the founder is looking to sell" written over a
quote that says less than that. The interpretation belongs in `fit_reason` at
ranking, clearly the system's opinion, never inside the signal cell.

## Step 3 — Age against the windows

Apply the per-family windows from `references/evidence-rules.md` (leadership
12 months, financing 9, growth 9, hiring 90 days). A signal outside its
window stays recorded with its date but `signal_strength` falls to low and it
cannot support PRIORITY.

## Step 4 — Absence is a finding

`signal: Not found` after a real search is a legitimate, common result. It
means WATCH with "needs a trigger" — a row the user re-checks next quarter —
not a failure. Do not stretch a weak mention to fill the cell. Roughly a
third to a half of in-mandate rows having no current signal is the normal
shape of an honest file.

---

## The gate

Per batch, show: signals found by family, the strength distribution, every
signal where the quote and the likely interpretation differ enough to matter
(show both), and 5 full rows. Stop for approval per batch. After the final
batch, update `run-state.md` to phase `ranking`.
