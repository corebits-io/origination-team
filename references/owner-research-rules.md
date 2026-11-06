# Owner research rules

The post-worthy sentence is "research agents identify owners". The rules below
are what keep that sentence from becoming a privacy problem, a wrong-person
letter, or both.

---

## What owner research is

Establishing, from public sources, three things:

1. **Who owns the company** — name(s), and the evidence
2. **What they do there** — role, and roughly how long
3. **Whether this is the same person everywhere** — the identity check

It stops there. This system never finds, guesses, or verifies contact
details. No email patterns, no phone numbers, no home addresses. The one
address it may record is the registered office from a public filing, labeled
as exactly that.

---

## Acceptable sources

- State / national business registers: officers, agents, incorporators
- The company's own site: about pages, team pages, history pages
- The owner speaking publicly in their professional capacity: trade press
  interviews, conference bios, their own LinkedIn profile summary
- Court and property records where lawfully public, used only to establish
  ownership of the business

## Never

- **Nothing about a person's private life.** Age, health, family, divorce,
  wealth, home address, hobbies. Not even when it is public. A letter that
  says "I understand your daughter chose medicine over plating" is
  surveillance wearing a smile
- **No contact guessing.** `jim@company.com` deduced from a pattern is a
  guess. `Not found` is the answer
- **No pretexting.** No calling the front desk pretending to be a customer,
  no fake quote requests, no scraping behind logins that forbid it
- **No titles the person never claimed.** A title needs the person or their
  employer stating it. Press shorthand and database fields do not count. When
  no stated title exists, record the evidenced relationship ("registered
  agent and incorporator") instead

---

## The wrong-person gate

Wrong-person errors are common enough to deserve their own gate. Before an
`owner_name` is written:

1. **Name + company must co-occur** in at least one tier 1 or tier 2 source
2. **Same-name collision check:** search the name alone; if another person
   with the same name is prominent in the same region or trade, require a
   second co-occurring source
3. **Generational check:** Sr/Jr/III suffixes and shared family names across
   officers mean the register entry and the website bio may be two different
   people. Match on role, not surname
4. **Tenure sanity:** if the register says incorporated 1987 and the
   identified "founder" graduated in 2015, somebody is wrong. Flag, do not
   average

A failed gate writes `Not found` plus a note of what conflicted. An unnamed
owner is recoverable; a letter opening with the wrong name is not.

---

## Succession language

Owner research often surfaces the best signals: "second generation",
"celebrating 40 years", a long-time GM promoted to president. Record them as
signals under `references/evidence-rules.md` — verbatim, sourced, dated.
Interpretation ("likely succession window") goes in `fit_reason`, clearly
marked as inference.
