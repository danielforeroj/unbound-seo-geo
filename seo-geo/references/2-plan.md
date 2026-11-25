# Step 2. Plan

Goal: a plan the user can execute alone or hand to a writer. Built from the
audit plus a short interview. Output: `seo-geo-work/<domain>/plan.md` from
`templates/plan.md`.

## The interview (15 to 30 minutes, with the owner or an expert)

Ask one at a time. Questions 2 and 3 matter most: they are the raw material for
content nobody else can publish (`knowledge/content.md`).

1. How do your customers describe the problem before they find you? Their
   words, not yours.
2. What do you know or measure that nobody else in your market does?
3. What proof do you have: cases, numbers, reviews, press, awards?
4. What have you tried in SEO or content before, and what happened?
5. Which competitors do you lose deals to, and why?
6. Topics, claims or comparisons that are off limits.
7. Who publishes on your site today, and on what (CMS, code repo, agency)?
8. Can you connect Search Console and Analytics?
9. Physical locations or service areas, if any.
10. Seasons, launches or events the calendar must respect.

Save the answers to `seo-geo-work/<domain>/interview.md`. Quote the owner's own
words in briefs, never invent examples or customers.

## Sections of the plan

1. **Goals, restated** in the user's words with their number.
2. **Keyword map.** Group by need, not by phrase. One page per genuinely
   distinct need. Sources: Search Console queries, the interview language,
   People Also Ask, autocomplete, the questions in the AI panel. With the MCP,
   `list_tracked_keywords` and `get_seo_snapshot`. Without a keyword tool, mark
   volume "not measured" and use rank of need (money first) instead.
3. **Pages to build or fix**, by type (`references/page-types.md`). Each page:
   the need, the keywords, the AI questions it should answer, and what the
   business must supply.
4. **Web fixes.** From the audit: blockers first, then money pages, then rest.
5. **Authority.** The third-party sites the engines already quote; the lists,
   directories and press to approach, with a named pitch for each
   (`knowledge/authority.md`).
6. **GEO.** Questions to add to the AI panel, wrong descriptions to correct at
   the source (the page or profile the engine read), source gaps to fill, and
   what to measure per engine.
7. **Local**, only if relevant (`knowledge/local.md`).
8. **How changes reach the site.** Pick one per change: paste-ready handover
   kit (always), CMS draft, pull request for code sites, dev ticket for
   technical fixes, listing profile edits.
9. **Calendar.** Month by month, which pages and which authority tasks, who
   supplies what. Track it in the table in `templates/tracker.md`.
10. **Measurement plan.** Which 10 to 50 keywords to track, the AI panel (same
    questions every month), report date, and what counts as success at 90 days,
    stated as actions done and counts measured, never as a promised rank.
11. **What we will not do**, from `knowledge/risk.md`, where the user asked for
    it or a past habit needs stopping.

## Prioritization rule

Order work by: (1) blockers, (2) fixes to pages that already earn clicks or
sales, (3) commercial pages that do not exist yet (service, comparison,
pricing), (4) authority work that places the business on pages the engines
already quote, (5) informational content that carries the business's own data.
Informational posts without original data come last. Cadence is set by how many
genuinely useful pieces the business's material supports, typically 4 to 8 a
month for a team, 1 to 3 for one person. Judge nothing before 90 days.

## Gate

The user approves the plan, or changes it. Then go to `references/3-produce.md`.
