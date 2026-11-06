# Evidence rules

Every claim in `targets.csv` is either evidenced under these rules or it is
`Not found`. There is no third state. A plausible guess written into a cell is
the most expensive kind of error in this system, because it looks exactly like
research and it ends up in a letter to the owner.

---

## The tiers

Every piece of evidence gets a tier, and the tier travels with the claim.

| Tier | What it is | Examples |
|---|---|---|
| 1 | A filing or register entry | state SOS filings, Companies House, UCC filings, licence rosters, court records, property records |
| 2 | The company speaking about itself | its website, its press releases, its job postings, its signed filings' narrative sections |
| 3 | Credible third parties | trade press, local business journals, association directories, conference programs |
| 4 | Aggregators and databases | business data sites, directory listings, map listings |

Rules of use:

- **Ownership** needs tier 1 or tier 2. A data aggregator saying
  "privately held" is not ownership evidence; half of those fields are stale
- **Size** can rest on any tier, but the tier is written into `size_basis`
  and tier 4 size figures are always `financial_confidence: low`
- **Signals** need tier 1, 2 or 3 with a URL and a date. Tier 4 never
  produces a signal
- **Owner identity** needs tier 1 or 2, or two independent tier 3 sources
  that agree

---

## The verbatim rule

Signals are quoted verbatim or they do not exist.

"We are exploring options for the next phase" is a quote. "The founder is
looking to sell" is a fabrication built on top of it, and fabrications of this
kind are the ones that end up quoted back to you, by the owner, on the phone.

The `signal` cell holds the exact words inside quotation marks, plus one
clause of neutral context. The interpretation lives in `fit_reason`, where it
is clearly the system's opinion and not the owner's words.

---

## Recency windows

A signal older than its window is not a signal. It stays in the row for
context with its date, but it cannot make a company PRIORITY.

| Signal family | Window | Why |
|---|---|---|
| leadership (succession language, retirement language, new GM) | 12 months | these situations move slowly |
| financing (UCC filings, new credit facility, lien releases) | 9 months | stale financing events read wrong |
| growth (expansion, new facility, major contract) | 9 months | an old expansion is just history |
| hiring (postings that imply transition, e.g. "General Manager") | 90 days | postings close |

---

## URL discipline

- Every `signal_url` and `owner_evidence` URL must have been opened and read
  during the run, not reconstructed from memory
- If a page cannot be fetched, the claim it supported drops to `Not found`.
  A snippet of an unreadable page is not evidence
- Archive links are acceptable; note `(archived)` after the URL

---

## The attribution check

Before any evidence is written into a row, answer one question: **is this page
talking about this company?** Name collisions, franchise networks, and
same-named companies in other states produce confident wrong rows. If the
page does not anchor to the company's domain, HQ city, or a named officer,
it is not evidence for this row.

---

## Unknown is not failed

`Not found` is a real value, written exactly like that, and it is the most
common value in a well-run file. A row is never dropped or demoted because a
fact is absent. Rows are dropped on facts that are false, never on facts that
are missing. Ranking gaps as negatives systematically deletes the
least-marketed companies, which is to say the proprietary ones.
