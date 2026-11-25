# Step 1. Audit

Goal: tell the user where they stand in search and in AI answers, what blocks
them first, and what to fix, in order. Time: 1 to 3 hours. Output:
`seo-geo-work/<domain>/audit.md` from `templates/audit.md`.

## 1. The brief (10 minutes)

Ask, and save to `seo-geo-work/<domain>/brief.md`:

- Domain, and what the business sells, in the owner's words.
- The buyer phrase: "who would search for this", plural ("accountants for
  freelancers", not the brand name). Every AI question is built around it.
- The 3 to 5 intents that make money: services, products, comparisons buyers
  make.
- Markets and languages. Do buyers research in English even if they buy in
  another language? (`knowledge/geo.md`)
- Up to 5 competitors, the user's list first.
- Places served, if any (triggers the local checks).
- What the user wants to move, with a number if they have one.

## 2. Access and eligibility (the blockers, 20 minutes)

Do these before anything else. If one fails, nothing else matters yet. Each has
its how in `knowledge/technical.md`.

- [ ] robots.txt: open `https://<domain>/robots.txt`. Googlebot, Bingbot and
      `OAI-SearchBot` are not blocked. Training bots (`GPTBot`,
      `Google-Extended`) are blocked or allowed on purpose, not by accident.
- [ ] CDN or firewall does not block those bots (ask whoever manages hosting).
- [ ] Money pages return 200, are indexable, and carry no stray `noindex` or
      `nosnippet`.
- [ ] Core content is in the raw HTML: view source, or fetch with JavaScript
      off. Empty shell means a finding.
- [ ] Search Console is verified. Check the generative AI setting if the
      account shows one.
- [ ] Sitemap submitted to Search Console and Bing Webmaster Tools.
- [ ] No manual action or security issue in Search Console.

## 3. AI visibility baseline

**With the MCP** (`references/mcp.md`): `list_brands` to find the brand, then
`list_scans`, `get_scan`, `list_prompts`, `list_competitors`,
`list_cited_sources`, `list_findings`. Save each result to `data/`. If there is
no scan and the user wants one, ask; call `run_scan` only on their plain yes.

**Without it** (`references/manual-checks.md`): build 10 buyer questions across
intents, ask each 3 times in each engine, record who is named and which pages
are cited.

Report per engine, never blended:

- Named in N of M answers, for the brand and each competitor.
- Recommended versus only mentioned.
- Which pages and sites the engines cited (the third-party list is the
  authority work).
- What each engine says about the brand when asked directly ("what do people
  say about [brand]"). Wrong or stale descriptions are findings.

Drop findings that name buying criteria as competitors (for example "price" or
"support" listed as a rival). Say how many you dropped.

## 4. Search baseline

- Search Console, if the user can share it: last 3 months, by page and by
  query. Use totals for trends and query rows as a sample, because query rows
  hide a large part of impressions (`knowledge/measurement.md`).
- MCP: `get_seo_snapshot` and `list_tracked_keywords` for what is already
  tracked.
- Without either: ask the user for the top 10 pages by clicks from Search
  Console, and run `site:<domain>` for rough indexed count. Mark it rough.

## 5. Page sample

Take the top 10 money pages. For each, check against the list in
`knowledge/content.md` ("Every page follows one structure"): title and H1 say
the answer in customer words, answer in the first 40 to 100 words, something
only the business knows, sourced facts, author and dates, internal links. Score
each as pass, partial, fail. Do not grade pages you did not open.

## 6. Authority and reputation

- Which review sites, lists and press the engines quote (from step 3).
- Review profiles: rating, count, recency.
- Presence on third-party "best X" lists in the category.
- Mentions in the last 12 months, linked and unlinked.

Detail and the how: `knowledge/authority.md`.

## 7. Local (only if the business serves places)

Run the checklist at the end of `knowledge/local.md`.

## 8. Risk sweep

Check the site and any past agency work against `knowledge/risk.md`: fake
press releases, parasite posts, self-ranked lists, bought links, mass AI pages,
fabricated authors. Report what you find without blame.

## 9. Write it

Fill `templates/audit.md`. Rank fixes: blockers first regardless of effort,
then what touches money pages, then the rest. For every fix write what you saw,
why it matters (one line with the grade), the exact fix, who does it, effort,
and how to verify. Finish with "Not covered by this audit" listing every check
you could not run and why.

## Gate

The user reads the audit and agrees on the three fixes to start with. Then go
to `references/2-plan.md`.
