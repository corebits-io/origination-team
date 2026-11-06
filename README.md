# Origination Team

A deal origination team living inside Claude Code. Type your buy box. Get
back a ranked target list with named owners, dated seller-intent signals, and
drafted first-touch outreach — queued for you to send by hand.

Eight skills, four agents and one command that take a firm's investment
criteria — sectors, geography, EBITDA range, ownership preferences — and run
the whole chain: map the target markets, enumerate the population, filter out
the businesses that do not fit, identify the owners, track seller-intent
signals, rank, and prepare personalized outreach for each qualified target.
With the rule that produced every verdict written next to it.

No associate reading four hundred companies one at a time.

Built for PE funds, family offices, search funds, independent sponsors,
holdcos and corporate development teams.

Runs on [Claude Code](https://www.anthropic.com/claude-code) and local files.
No database, no API keys, no signups.

---

## 👉 Start here: [SETUP.md](./SETUP.md)

About fifteen minutes from zero to a running origination team. Every step in
plain English.

Want to see the end product first?
**[samples/sample-run.md](./samples/sample-run.md)** is a complete finished
run, invented end to end, so you know exactly what you are getting before you
install anything.

---

## Came from the LinkedIn post? — this is the system

### One command

Fill in one file, then type:

```
/run-origination-team
```

The run stops and shows you its work before every write. Eight steps, a gate
at each one, nothing happens behind your back.

| The post said | The system does |
|---|---|
| "Define your firm's investment criteria... target sectors, geography, EBITDA range, and ownership preferences" | `templates/BUY-BOX.md` — ten sections, with a worked example, and an intake skill that challenges the untestable parts before anything runs |
| "Find me 100 founder-owned businesses that match my buy box" | `/run-origination-team` — one command drives the whole chain |
| "First, it maps companies across your target markets" | `team-market-map` + `team-discovery` — segment economics, then whole-source enumeration from rosters and registers, with a coverage log |
| "Then it filters out businesses that don't fit" | `team-fit-screen` — ownership, the sponsor screen, labeled size estimates, exclusion tests. Drops on false facts, never on absent ones |
| "Research agents identify owners" | `team-owner-research` — named owners from public sources, behind a wrong-person gate. No contact guessing, nothing from private life |
| "track potential seller-intent signals" | `team-seller-signals` — four signal families, quoted verbatim, dated, aged against recency windows |
| "and prepare personalized outreach for each qualified target" | `team-ranking` + `team-outreach-prep` — PRIORITY / WATCH / PASS, then drafts built only from evidenced facts, queued for you to send by hand |
| "It's basically a deal origination team living inside Claude Code" | The four agents below. Both lists are the same system; the agents run the skills |

### The eight skills

| Skill | What it does |
|---|---|
| `team-buy-box-intake` | Checks the box is complete enough to originate against, rewrites untestable must-haves into tests, scopes the run. Runs a principal-buyer gate that has no override |
| `team-market-map` | Maps the segment: fragmentation, who is already consolidating, the typical owner, the segment economics every later estimate depends on, and where the companies are actually findable. Ends with a verdict that is sometimes "do not source this segment" |
| `team-discovery` | Enumerates the population from licence rosters, registers, association directories, certification lists and exhibitor lists — the sources bought lists never cover — with a source per row and a coverage log that names what the pull missed |
| `team-fit-screen` | What the company actually is, who owns it, the sponsor screen, a defensible size read on companies that publish nothing, and the platform or add-on call |
| `team-owner-research` | The named owner, evidenced role and tenure, behind a four-check wrong-person gate. Never a contact detail, never anything from a person's private life |
| `team-seller-signals` | The four families — leadership, financing, growth, hiring — quoted verbatim, sourced, dated, and aged against a per-family recency window |
| `team-ranking` | Builds a rubric from your box, gets it approved before ranking a single row, ranks every row identically, sizes PRIORITY against your real calendar, then audits itself |
| `team-outreach-prep` | Drafts a first touch per PRIORITY target, built only from evidenced facts with the evidence trail attached, cross-checked so personalization is real, and queued. Never sent |

Install, then run `/skills` to see all eight.

### The four agents

| Agent | What it does |
|---|---|
| `team-mapper` | Box, map, population. Stops at the list of company names |
| `team-analyst` | Fit screen, owners, signals. Fills in what the ranking needs to know |
| `team-ranker` | Rubric, verdicts, audit. Turns research into decisions |
| `team-writer` | Hooks, drafts, the queue. Writes the only words an owner will ever see |

Install, then run `/agents` to see all four.

> Both lists are the same system. The agents run the skills.

### The chain

```
team-buy-box-intake          box checked, principal gate, run plan
      ↓
team-market-map              segment economics, sources, verdict
      ↓
team-discovery               population enumerated, deduped, sourced
      ↓
team-fit-screen              ownership, sponsor screen, labeled size, role
      ↓
team-owner-research          the named owner, behind the wrong-person gate
      ↓
team-seller-signals          the dated reason to call this quarter
      ↓
team-ranking                 PRIORITY / WATCH / PASS, then the audit
      ↓
team-outreach-prep           drafts with evidence trails, queued, never sent
```

### Every row comes back with this

| Field | What it holds |
|---|---|
| company, domain, HQ | identity and geography |
| sector, segment, source | where it sits, and the source specific enough to re-run |
| ownership_type, ownership_evidence | founder, family, management, ESOP, sponsor, corporate, or `Not found` — with the filing or page that establishes it, tiered |
| sponsor_screen | the check that catches companies already bought but still marketing themselves as family owned |
| owner_name, owner_role, owner_evidence | the person, their stated role, and the sources — or `Not found` with what conflicted |
| est_revenue, est_ebitda, size_basis | ranges, labeled estimates, with the arithmetic attached |
| financial_confidence | verified / high / medium / low / `Not found` |
| fit_role | `platform` or `add-on`, and for an add-on, the named platform |
| signal, signal_family, signal_date, signal_url | the reason to call this quarter, quoted verbatim, with a working URL and a date |
| signal_strength | high / medium / low / `Not found` |
| verdict | **PRIORITY** / **WATCH** / **PASS** |
| fit_reason | the rules that fired, so a verdict can be argued with in March |
| outreach_status | drafted / sent-by-hand (you mark that one yourself) |

Three verdicts, not a score out of 100. A number between 1 and 100 invites an
argument about whether a 71 beats a 68 and tells nobody what to do on Monday.

**PRIORITY** — in mandate, owner named, dated signal in window
**WATCH** — fits the thesis, needs a better trigger or a filled gap
**PASS** — a tested fact excludes it, and the rule is written next to it

---

## Repo contents

- [`SETUP.md`](./SETUP.md) — the full setup guide, start here
- [`commands/`](./commands/) — the `/run-origination-team` command
- [`skills/`](./skills/) — the eight skills Claude Code reads
- [`agents/`](./agents/) — the four subagents
- [`references/`](./references/) — evidence rules, estimation rules, the
  ranking rubric, sourcing directories, owner research rules, outreach rules,
  and the run protocol that survives interruptions
- [`templates/`](./templates/) — the buy box template, a fully worked example,
  the 28-column `targets.csv` and the outreach queue
- [`samples/`](./samples/) — a complete finished run, invented end to end

---

## A word on the research

Everything here runs on public sources: registers, licence rosters, filings,
trade press, association directories, and what companies publish about
themselves.

Nothing in this package scrapes behind a login that forbids it, pretends to
be somebody it is not, researches anyone's private life, or guesses an email
address. If you are a fee-based intermediary rather than a principal buyer,
the intake skill will stop and tell you to talk to securities counsel before
it researches anybody on your behalf. That gate is deliberate and has no
override.

---

Free and MIT licensed. Built by [Corebits](https://corebits.io).
