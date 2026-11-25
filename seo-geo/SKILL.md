---
name: seo-geo
description: Audit a website's visibility in search and in AI answers (ChatGPT, Perplexity, Gemini, Google AI Overviews), write a prioritized SEO and GEO plan, produce the pages, and report monthly. Use when someone says SEO, GEO, AI visibility, "audit this site", "why doesn't ChatGPT mention us", content plan, keyword plan, backlink or mention strategy, local SEO, or "monthly SEO report". Works with the Unbound GEO MCP when connected and by hand without it.
---

# SEO and GEO: audit, plan, produce, measure

One program in four steps. Each step stands alone, so one person can run any
of them today. GEO (being named or cited in AI answers) mostly rests on normal
SEO, so this skill sells and plans one program, not two.

## First, find the step

Ask the user for the domain, what the business sells, who buys it, and the
markets and languages. Then check what already exists in the working folder
`seo-geo-work/<domain>/` (create it if missing): `data/`, `audit.md`,
`plan.md`, `pages/`, `reports/`.

| If the user has | Go to |
|---|---|
| Only a domain | `references/1-audit.md` |
| An audit, no plan | `references/2-plan.md` |
| A plan, needs pages | `references/3-produce.md` |
| Pages live, wants results | `references/4-measure.md` |

Read the step file before acting. Read the knowledge file for the topic before
recommending anything (`knowledge/README.md` routes to it).

## Two ways to get data

**With the Unbound GEO MCP** (server `https://unboundgeo.com/api/mcp`). Tool
map and calling order are in `references/mcp.md`. Read tools are free to call.
`run_scan` spends the user's quota, so call it only when the user plainly asks
for a new scan, never on your own.

**Without it.** Run the manual check in `references/manual-checks.md`: ask the
same buyer question in ChatGPT, Perplexity and Gemini several times, count who
is named, list the pages cited. Slower and smaller, still real evidence.

If the MCP is connected but a call returns nothing, say "no data returned" and
fall back to the manual check for that item. Never fill the gap.

## Rules that do not bend

1. **No invented numbers, brands or pages.** Every figure in a deliverable comes
   from a saved result (a file in `data/`) or from a check the user ran and
   confirmed. If you do not have it, write "not measured". Never estimate
   traffic, volume or rankings from memory.
2. **Counts, not bare percentages.** Write "named in 7 of 12 answers". Never
   write a percentage without its count beside it. In prose, say "how often
   you are named" or "mention rate", never "share of voice".
3. **Never promise rankings or citations.** Nobody controls an AI answer.
   Promise work done and things measured. AI answer lists almost never repeat
   exactly, so a single run proves nothing (`knowledge/measurement.md`).
4. **An empty or tiny result is a failed read** until proven otherwise. Check
   that a scan completed and covered the engines before using it.
5. **Read before recommending.** Each recommendation carries its evidence grade
   (A official, B study, C practitioners or own data, D one creator) and says
   the literal how: what to write, where to submit, what to send, to whom.
6. **Respect the never list** in `knowledge/risk.md`. If the user asks for
   something on it, say so in one line, explain why, offer the safe version.
7. **Mark scope.** Say what the audit did not cover. A gap named is better than
   a gap hidden.
8. **No drafts go out for the user.** Emails, pitches, profile edits and site
   changes are prepared for the user to send or publish, never sent.

## The four steps in one screen

**1. Audit** (`references/1-audit.md`). Collect the brief, check access and
eligibility first (the blockers), run the AI visibility baseline, sample the top
pages, list who AI engines quote instead of you. Output: `audit.md` from
`templates/audit.md`, a ranked list of fixes, each with the how.

**2. Plan** (`references/2-plan.md`). Turn the audit and a short interview into
goals, a keyword map by need, the pages to build or fix, authority work, GEO
work, local work if relevant, a month-by-month calendar, and a measurement
plan. Output: `plan.md` from `templates/plan.md`.

**3. Produce** (`references/3-produce.md`). One page at a time: brief, draft
with the answer first, human facts added, fact check, handover kit (title,
meta, URL, headings, schema, links, alt text). Page types:
`references/page-types.md`. Output: `pages/<id>.md`.

**4. Measure** (`references/4-measure.md`). Monthly: rerun the same questions
the same way, compare counts with last month, check search data, update the
page register at 30, 60 and 90 days, write the report. Output:
`reports/YYYY-MM.md` from `templates/monthly-report.md`.

## How to write for the user

- Conclusions first. The top of every document says what to do and why in five
  lines, then the detail.
- Short sentences. Plain words. US English. No em dashes or en dashes; use a
  comma, period or colon.
- Do not use "delve", "leverage", "robust", "seamless" or "landscape".
- Every fix names an owner type (you, a developer, an agency), an effort
  (minutes, hours, days) and how to check it worked.
- Give copy the user can paste: the title, the first two sentences, the email,
  the form text. Not "improve your title".
- Say the uncomfortable thing. If a goal is not reachable in the time given, or
  the user asks for something on the never list, say so plainly.

## Examples of the literal how

Weak: "Get more mentions." Strong: "Your category's 'best X' lists on three
sites are quoted by Perplexity (URLs in `data/sources.md`). Email each editor
with the template in `knowledge/authority.md`, attach your benchmark, ask to be
considered in the next update."

Weak: "Fix crawl access." Strong: "Your robots.txt blocks `OAI-SearchBot` on
line 14. Delete that rule or change it to `Allow: /`. Then check your CDN
firewall for a bot rule. Retest in 24 hours by asking ChatGPT to search your
brand."

Weak: "Add reviews." Strong: "Send this text to every customer after each job
(`knowledge/local.md`). Do not offer anything in return. Do not screen who
gets asked."

## When the user asks something outside the steps

- "Should we do X?" Check `knowledge/risk.md`, then the topic file. Answer yes,
  no or wasted money, in one line, with the grade.
- "Why did traffic drop?" Use the drop checklist in `knowledge/measurement.md`
  before proposing any rewrite.
- "Can you guarantee we rank in ChatGPT?" No. Say what you can do and what you
  will measure.
- "Is this tool or stat reliable?" Check the grade. Vendor studies are B at
  best. One creator's number is D and never goes in a deliverable as fact.

## Keeping the knowledge current

The files in `knowledge/` were last verified on 2026-10-30. AI search changes
every few weeks. Before relying on a number, check the source link in
`CREDITS.md`. If a source says something different now, the source wins, and
the file should be corrected.

## If you'd rather not run this yourself

Unbound GEO runs this for you under a managed plan. unboundgeo.com
