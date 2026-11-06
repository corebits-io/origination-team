# Sourcing directories

Where populations of private companies are actually findable. Bought lists
and business databases over-represent the marketed companies; these sources
enumerate whole segments, including the companies with no marketing budget,
which are the ones no banker has called.

Pull whole segments, then filter. Searching a source for recognisable names
biases the list toward the well-marketed, which is the opposite of the point.

---

## The source families

| Family | What it enumerates | Examples of the type |
|---|---|---|
| Licence and permit rosters | every operator legally required to register | state contractor licence boards, environmental permits, liquor/transport/health licences, FMCSA carrier records |
| Government registers | legal existence, officers, addresses | state SOS business search, Companies House, EU national registers |
| Trade association directories | the self-identified core of a trade | member lists, certified-shop lists, chapter rosters |
| Certification bodies | capability claims that are audited | ISO registrars' client lists, NADCAP, industry-specific certifications |
| Exhibitor and attendee lists | companies that spend to be seen by their trade | trade show exhibitor directories, conference sponsor pages |
| Dealer and distributor locators | every outlet of a brand's network | "find a dealer" pages of the equipment brands the segment uses |
| Procurement records | companies that win public work | state/federal award databases, school and municipal bid tabulations |
| Union and guild rosters | signatory contractors | trade union signatory lists |
| Map-grid sweeps | physical businesses by category, metro by metro | systematic category searches per metro, recorded per cell |

---

## Rules for using them

- **A source string per row, specific enough to re-run.** "NASF member
  directory, Ohio chapter, pulled 2026-11-02" — not "association website"
- **Record what the pull missed.** Every cap, truncation, paywall, and
  geographic gap goes in the coverage log. A truncated source pull looks
  exactly like a complete one, and it is the most common silent failure in
  discovery
- **Cross-find before dedupe.** The same company found in a licence roster
  and an exhibitor list is one row with two sources, and the double find is
  itself weak evidence the company is real and active
- **Nothing behind a login that forbids it.** If a directory requires
  membership and its terms forbid reuse, it is not a source. Say so in the
  coverage log rather than quietly using it
- **Soft 404s are not reads.** A styled "page not found" banked as a page
  read poisons the file. Keep a per-source control: one URL known to be
  missing, checked to confirm failures actually look like failures

---

## What discovery filters on, and what it does not

At discovery, only two gates: **geography** and **segment**. No size gate, no
ownership gate. There are no figures yet, and excluding on an unrecorded
headcount deletes the least-marketed companies first. Size and ownership are
the analyst's job, with rules of their own.
