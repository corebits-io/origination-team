# Sample run — metal finishing, US Midwest

> Everything below is invented end to end: the buyer, every company, every
> person, every quote, every URL. It exists so you can see the shape and
> depth of a finished run before you install anything. No real company or
> person is referenced, and resemblance to any is coincidence.

---

## The input

The buy box from `templates/BUY-BOX-example.md`: Marden Holdings, a fictional
family holdco in Columbus, Ohio. Metal finishing and plating job shops,
industrial coating applicators, and anodizers. OH / IN / MI / KY / western
PA. Revenue $8M-$40M, EBITDA $1.5M-$5M, headcount 40-220 where revenue is
unreadable. Founder-, family-, or management-owned. Platform search.
Capacity: 6 owner conversations a month, 10 first touches a week.

Intake challenged two criteria and both were rewritten: "strong management"
became "a named GM or #2 visible on the site or register", and "no troubled
shops" became a soft negative ("OSHA citation in last 3 years") because it
was not cleanly testable as a hard gate.

The market map returned **SOURCE IT, NARROWED**: anodizing-only shops in the
region cluster under $5M revenue, so the run scoped to plating and coating
shops with anodizing as a line, not a specialty. Segment economics, sourced
from a fictional trade association's operating survey (2025): revenue per
employee $150k-$175k, typical EBITDA margin 12%-18%.

## The funnel

```
enumerated            473 rows from 3 sources
deduped               412   (61 cross-found in 2+ sources)
discovery gates       412   →  341 carried; 71 PASS (geography 54, segment 17)
fit screen            341   →  261 in-mandate; 80 PASS
                              (sponsor-owned 38, segment on closer read 22,
                               verified size outside box 9, hard exclusion 11)
owner research        261   →  214 named; 47 Not found
seller signals        261   →   96 with an in-window signal
                              (high 18, medium 51, low 27)
ranked                412   →  PRIORITY 12 · WATCH 249 · PASS 151
outreach prep          12   →  11 drafted · 1 returned to analyst · 0 sent
```

Read it right to left. Four hundred enumerated is a coverage claim; four
hundred contacted is a mistake. Research depth is earned: no owner research
was paid on the 38 sponsor-owned rows the screen caught first.

The coverage log's bias statement: all three sources favor shops that join
things — the association roster, the certification list, the trade show.
A profitable shop that joins nothing appears only in the state manufacturer
roster, and Kentucky's roster was the weakest of the five states. Kentucky
rows are under-represented and the log says by roughly how much.

## Three rows in full

**Kettle Ridge Plating Co. — PRIORITY** (fictional)
Dayton, OH · metal finishing job shop · found in NASF-style roster + state
roster. Family-owned, 2nd generation; Ohio SOS filing matches the About
page's "second-generation family owned" (tier 1 + 2). Sponsor screen clear.
Owner: Daniel Maas, President and owner (About page bio + SOS agent record).
Size: 85 employees (state roster) x $160k = $12M-$18M est. revenue, margin
midpoint gives $1.8M-$2.7M est. EBITDA, confidence medium. Signal
(leadership, 2026-09-14, trade-press profile): "After 34 years I am proud to
watch the next generation take our quality system forward." Strength medium.
Verdict: PRIORITY — ownership in scope, size inside box on labeled estimate,
dated leadership signal in window, owner named.

**Harwell Anodize & Coat — WATCH** (fictional)
Fort Wayne, IN · coating applicator · exhibitor list only. Founder-owned on
the company's own history page (tier 2); sponsor screen clear. Owner: the
wrong-person gate fired — the register lists "R. Harwell Jr." as agent while
the site bio describes the founder, and a same-named Harwell runs a Fort
Wayne fastener company. `owner_name: Not found`, conflict noted. Size: no
headcount anywhere; `est_revenue: Not found`. No signal in window. Verdict:
WATCH — in mandate, but no owner named, no size basis, no trigger.
`fit_reason` lists all three gaps, so next quarter's pass knows what to fill.

**Vantage Surface Technologies — PASS** (fictional)
Grand Rapids, MI · plating · association roster. The website still says
"family owned since 1979". The sponsor screen found a 2024 consolidator
announcement: "Vantage Surface Technologies joins the Meridian Finishing
platform" (fictional). Verdict: PASS — sponsor-owned, with the announcement
URL and date in `fit_reason`. The row stays in the file so nobody
re-researches it in March.

## The audit

1. **Gate check:** 151 PASS rows re-tested; 2 corrections. One row had been
   passed on "likely too small" with no verified figure — returned to WATCH
   under the estimate rule. One geography PASS had the HQ wrong (branch
   address recorded as HQ) — re-screened, carried
2. **Consistency check:** 20 similar-row pairs sampled; 1 inconsistency, two
   shops with identical evidence in different buckets because one signal sat
   two weeks outside its window. Both set to WATCH
3. **Estimate check:** clean. No PASS rests on an unverified number
4. **Capacity check:** 12 PRIORITY against 6 conversations a month — two
   months of pipeline. Inside range; no tightening needed

Reported with corrections applied. The audit found 4 errors in 412 rows and
that is the normal shape of a clean-ish run; an audit that finds zero twice
in a row is not reading anything.

## Two drafts from the queue

**To Daniel Maas, Kettle Ridge Plating (posted letter, 154 words):**

> Dear Mr. Maas,
>
> I run Marden Holdings, a second-generation family holdco in Columbus. We
> have owned and operated one plating business for 19 years and have never
> sold a company we bought.
>
> I read the Products Finishing profile from September. Thirty-four years in,
> with the next generation taking the quality system forward — that is a rare
> thing to have built, and it is exactly the kind of company we hope to own
> alongside the one we have.
>
> I am not a broker and I have no timeline to push. If you would ever be open
> to a conversation about what the long term could look like for Kettle
> Ridge, I would be glad to drive down to Dayton. And if the answer is
> simply "we are not sellers," I will take that cheerfully and still wish
> you a strong year.
>
> Tom Marden
> Managing Partner, Marden Holdings

Below the draft in its file: the hook ("34 years, second generation active,
quality system pride — trade-press profile, 2026-09-14") and every fact used,
each with its source cell. Note what the letter does not do: it never says
"exit", never names a number, and never claims to have "followed the company
for years".

**Returned to analyst:** one PRIORITY row's only available hook was the
owner's age, inferred from a graduation year. That is private-life material
and an inference besides. The row went back with a note: find a company-side
hook or the draft waits.

---

*This sample is fictional end to end. Built with the `/run-origination-team`
command from this repo.*
