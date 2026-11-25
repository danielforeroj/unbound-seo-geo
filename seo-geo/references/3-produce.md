# Step 3. Produce

Goal: one live page at a time, each with something only the business knows.
Output per page: `seo-geo-work/<domain>/pages/<id>.md` (brief, draft, kit).

## The path of one page

1. **Calendar row.** Type, need, target keywords, target AI questions, owner,
   due date (`templates/tracker.md`). Ids stay stable: `P-001`.
2. **Brief.** The need in one sentence. Keywords and sub-questions. The facts,
   numbers and quotes from the interview. Sources to cite. Internal links in
   and out. The rules for the page type (`references/page-types.md`).
3. **Draft, answer first.** The direct answer to the main question goes in the
   first 40 to 100 words. Then proof, then detail. Structure rules are in
   `knowledge/content.md`. An AI assistant may draft from the brief.
4. **Human pass.** The owner or an expert adds what the model cannot: real
   numbers, a customer case, a price range, a point of view, an opinion. This
   step is what earns citation. A page with nothing only the business knows
   does not ship.
5. **Fact check.** Every claim, number, name and date. Also every metadata
   field: title, description, schema, alt text. Google's guidance on AI
   content asks for this (`knowledge/content.md`). Link sources inline where
   the claim is made.
6. **No AI rewrite of a finished body.** Do not run a finished human page
   through an AI "GEO optimizer". In a lab test, rewriting body text lowered
   visibility (`knowledge/geo.md`). Tightening titles, descriptions and
   headings helped.
7. **Remove AI tells.** Read it aloud. Cut filler, generic claims and stacked
   adjectives. Replace "we help you grow" with the number.
8. **Handover kit.** Always produce these, paste-ready, at the top of the page
   file:
   - Title (short enough not to truncate in results, answer first, brand last)
   - Meta description (one or two sentences, a reason to click)
   - URL slug in plain words (`/services/geo-recovery/`)
   - H1 and H2 list
   - Schema JSON-LD that matches the visible page (Article, Product,
     LocalBusiness, FAQPage only where questions are visible)
   - Internal links with anchor text
   - Image alt text
   - Author and published and updated dates
9. **Publish.** Pick the route: paste into the CMS, a pull request for sites in
   code, or a ticket for a developer. Never edit the site without the user's
   go-ahead.
10. **Register.** After it is live, add the URL and date to the register in
    `templates/tracker.md`. Step 4 measures from that row.
11. **Ask the engines to notice.** Submit the URL in Search Console (URL
    Inspection, "Request indexing") and keep the sitemap current, including in
    Bing Webmaster Tools. Then link to the page from two or three existing
    pages that already get traffic.

## Quality bar (Google's own questions, rewritten as a checklist)

- Does it give original information, analysis or data?
- Does it cover the topic completely, not just the head term?
- Does it say something beyond the obvious?
- Is it more useful than what already ranks?
- Was it made for people, not to catch a search?

If two are "no", do not publish. Rework or drop the page.

## Never in this step

- A page per query variant or per AI fan-out phrasing.
- City pages where only the city name changes.
- Invented authors, credentials, reviews or statistics.
- Date changes with no content change.
- Dozens of generated FAQs.

Details and grades: `knowledge/content.md` and `knowledge/risk.md`.
