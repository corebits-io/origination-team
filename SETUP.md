# Setup

> A free giveaway: a deal origination team that runs inside Claude Code, from
> investment criteria to a ranked target list with named owners, dated
> signals, and drafted outreach. Installed and running in about fifteen
> minutes.

## What this actually is

One command:

```
/run-origination-team
```

Behind it, eight skills (the steps) and four agents (the team):

| Skill | Step |
|---|---|
| `team-buy-box-intake` | check the box, principal gate, run plan |
| `team-market-map` | segment economics, sources, verdict |
| `team-discovery` | enumerate the population, coverage log |
| `team-fit-screen` | ownership, sponsor screen, labeled size |
| `team-owner-research` | the named owner, wrong-person gate |
| `team-seller-signals` | verbatim, dated, aged signals |
| `team-ranking` | PRIORITY / WATCH / PASS, the audit |
| `team-outreach-prep` | drafts with evidence trails, the queue |

| Agent | Phase |
|---|---|
| `team-mapper` | box → map → population |
| `team-analyst` | screen → owners → signals |
| `team-ranker` | rubric → verdicts → audit |
| `team-writer` | hooks → drafts → queue |

Both lists are the same system; the agents run the skills. To see a complete
finished run before installing anything, read
[samples/sample-run.md](./samples/sample-run.md).

## What you need

| Thing | Needed? |
|---|---|
| [Claude Code](https://www.anthropic.com/claude-code) | Yes |
| A folder for your search | Yes |
| Your buy box, filled in (Part 4) | Yes |
| Everything else — databases, API keys, signups, spreadsheet licences | No |

---

## Part 1 — Install Claude Code

Follow [anthropic.com/claude-code](https://www.anthropic.com/claude-code).
Then verify in a terminal:

```bash
claude --version
```

If a version prints, you are done with Part 1.

## Part 2 — Install the package

### macOS / Linux

```bash
git clone https://github.com/corebits-io/origination-team.git
mkdir -p ~/.claude/skills ~/.claude/agents ~/.claude/commands
cp -r origination-team/skills/* ~/.claude/skills/
cp -r origination-team/agents/* ~/.claude/agents/
cp -r origination-team/commands/* ~/.claude/commands/
```

### Windows (PowerShell)

```powershell
git clone https://github.com/corebits-io/origination-team.git
New-Item -ItemType Directory -Force "$HOME\.claude\skills", "$HOME\.claude\agents", "$HOME\.claude\commands"
Copy-Item -Recurse -Force "origination-team\skills\*" "$HOME\.claude\skills\"
Copy-Item -Recurse -Force "origination-team\agents\*" "$HOME\.claude\agents\"
Copy-Item -Recurse -Force "origination-team\commands\*" "$HOME\.claude\commands\"
```

**Keep the cloned folder.** The skills read `references/` and `templates/`
from it at run time; deleting it after install breaks the run.

Verify: start `claude` anywhere and run `/skills` — the eight `team-` skills
should be listed. Run `/agents` — the four agents should be listed. If not,
see Troubleshooting.

## Part 3 — Set up the workspace

Your search lives in its own folder, separate from the clone:

```bash
mkdir my-search && cd my-search
cp ../origination-team/templates/BUY-BOX.md .
```

> **Never commit this folder anywhere public.** It will hold target company
> names, owner names, and the reasoning behind a live acquisition thesis.
> Owner names are personal data in most jurisdictions. The repo's
> `.gitignore` assumes a `my-*/` or `workspace/` folder stays out of version
> control.

## Part 4 — Fill out the buy box

The most important step in the whole guide. Open `BUY-BOX.md` and fill in all
ten sections, with `templates/BUY-BOX-example.md` beside you for calibration.

- Write `TBD` where you genuinely do not know — the intake skill will help
  you resolve each one. Write `N/A` only where a section truly does not apply
- The sections people skip are the ones the run needs most: **8**
  (exclusions must be testable), **9** (outreach identity — no drafts without
  it) and **10** (capacity — the PRIORITY bucket is sized from it)
- If you would rather fill it in conversationally, start `claude` in the
  folder and type "help me fill out my buy box" — the intake skill walks it
  section by section

## Part 5 — First run

In your workspace folder, start `claude` and type:

```
/run-origination-team
```

The run walks eight steps and stops at a gate before each write:

1. **You approve:** the run plan, and every challenge to your box
2. **You approve:** the market map and its verdict (sometimes the verdict is
   "do not source this segment" — that is the system working)
3. **You approve:** the discovered population, counts by source, the
   coverage log
4. **You approve:** each fit-screen batch of 20-30 rows
5. **You approve:** each owner-research batch, including every wrong-person
   gate firing
6. **You approve:** each signals batch, with quote and interpretation shown
   separately
7. **You approve:** the rubric *before* any row is ranked, then the ranked
   list with the full audit
8. **You approve:** every draft, each with its evidence trail, and the queue

A full run over a few hundred companies takes hours, not minutes, and can
span days. It saves state (`run-state.md`) after every gate; close the laptop
whenever you like and type the command again to resume where it stopped.

## Working with the agents directly

The command is the paved road; the agents also respond on their own:

```
Use team-mapper to check my buy box and map the segment, no discovery yet.

Use team-analyst to run the fit screen on the attached CSV of 80 companies
I already have — columns are company, city, state, website.

Use team-ranker to re-rank targets.csv after I widened the EBITDA range in
my buy box.

Use team-writer to redraft the Kettle Ridge letter warmer, same facts only.
```

Bring-your-own-list works: give `team-analyst` any CSV with company names and
locations, and it will screen, research and hand off to ranking exactly as if
discovery had produced it.

## The safety rails

Each of these is non-configurable, and each exists because of a specific
failure:

- **Nothing is ever sent.** Drafting and queueing is the ceiling; you send by
  hand. Automated sending at research quality is how owners end up
  forwarding your letter around the trade
- **No contact details, found or guessed.** A pattern-guessed email that
  bounces is a nuisance; one that lands in the wrong inbox is worse
- **The principal-buyer gate has no override.** Fee-based intermediation
  touches broker-dealer law; the system refuses to research on that basis
- **Signals are quoted verbatim or they do not exist.** The gap between "the
  quote" and "what it probably means" is where fabrications live
- **Nothing about any person's private life.** Age, health, family, wealth —
  not even when public
- **Unknown is not failed.** `Not found` never demotes a row; false facts do
- **Sponsor-owned is always PASS**
- **Estimates are labeled and never exclude.** Only verified figures PASS a
  row on economics
- **Nothing is deleted.** Every PASS keeps the rule that fired, so the file
  is institutional memory, not a snapshot

## Troubleshooting

- **`/skills` does not show the team skills** — the usual cause is a skills
  folder inside skills: check you copied `skills/*` (the folders) into
  `~/.claude/skills/`, not the `skills` folder itself
- **"Cannot find references/..."** — the clone was moved or deleted. The
  skills read rules from the cloned repo; restore it and tell Claude the path
- **It keeps saying `Not found`** — working as intended. Most private
  companies publish nothing; `Not found` rows are ranked on what is known,
  and the WATCH list tells you which gaps to fill
- **Too few PRIORITY rows** — read the ranker's report: it names the binding
  test. Usually the signal window or the owner requirement. Widen the box or
  wait a quarter; do not loosen the evidence rules
- **Too many PRIORITY rows** — your section 10 capacity is set high, or the
  rubric tightening was declined. A PRIORITY list bigger than your calendar
  is a WATCH list wearing a costume
- **Windows paths** — if a skill cannot find your workspace, give the full
  path with backslashes once; Claude Code handles it from there
- **"It is slow"** — a real run reads hundreds of pages. Hours per phase is
  normal and still replaces a fortnight of associate time

## FAQ

**What does it cost to run?** Claude Code usage only. There is nothing else
to pay for: no data subscriptions, no per-contact fees.

**Why three buckets instead of scores?** A 71-vs-68 argument tells nobody
what to do on Monday. PRIORITY / WATCH / PASS each carry an action.

**Why no email finding or sending?** Legal exposure and error cost both
concentrate there, and both depend on your jurisdiction and channel. The
system stops where generic rules stop being safe. That is a design decision,
not a missing feature.

**I already have a target list.** Hand it to `team-analyst` as a CSV. It
enters the chain at the fit screen.

**Is my data safe?** Everything lives in local files in your workspace
folder. Nothing is uploaded anywhere by this package. Keep the workspace out
of version control; it holds personal names.

**Does it work outside the US?** Yes. The source families (registers,
licence rosters, associations) exist in most jurisdictions; the market map
finds the local versions. The compliance notes flag where rules differ.

**How many searches at once?** One segment per run, one run per workspace
folder. Parallel searches are parallel folders.

**Can I change the rules?** The rubric adapts to your box by design. The
safety rails do not — they are the difference between this and a scraper.

## When you outgrow files

The signs: three people working the same queue, re-runs every month across
five segments, or a pipeline that needs stages a CSV cannot hold. At that
point you want a database behind the same rules, and dedicated sending
infrastructure with its own compliance review. The rules in `references/`
port; the files were never the point.

## What's next

Run one segment end to end. Read every draft against its evidence trail.
Then go have the conversations — that part was never automatable, and it is
the part you are actually good at.

---

Free and MIT licensed. Built by [Corebits](https://corebits.io).
