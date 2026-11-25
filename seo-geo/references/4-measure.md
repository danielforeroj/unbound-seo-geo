# Step 4. Measure

Goal: a monthly report that says what moved, what shipped, what did not work
and what changes next month. Same questions, same method, every month.
Output: `seo-geo-work/<domain>/reports/YYYY-MM.md` from
`templates/monthly-report.md`.

## Rules for this step

- The AI panel (the question list) stays fixed month to month. Add questions
  only at quarter boundaries and say so, otherwise trends mean nothing.
- Counts, always: "named in 9 of 15 answers on Perplexity". A percentage may
  follow the count, never replace it.
- Per engine, never blended. A good month on one engine says nothing about
  another.
- Never report a position inside an AI answer. Order and list length change
  from run to run (`knowledge/measurement.md`).
- Wait. Changes show in days or take months. Do not judge a page before 30
  days, and call it winning or losing only at 90.
- Do not invent a cause. Write "we think" when it is a hypothesis.

## Each month

1. **Save what you measure.**
   - With the MCP: `list_scans`, `get_scan` for the latest, and the previous
     one for comparison, `list_cited_sources`, `list_findings`,
     `get_share_of_voice` (call the number a mention count in the report),
     `get_seo_snapshot`, `list_tracked_keywords`. If the user wants a fresh
     scan and none ran this month, ask. Call `run_scan` only on a plain yes.
   - Without it: rerun the manual check (`references/manual-checks.md`) on the
     same panel, same engines, same number of runs. Save the table.
2. **Compare with last month.** For each engine: named in N of M, change in N
   and M. If M changed, say so, because counts on different totals do not
   compare directly. Note competitors that appeared or vanished and any new
   cited sources.
3. **Search.** Search Console, page level: clicks and impressions for every URL
   in the register, and the totals. Use query rows as a sample only. Rank
   tracking from `get_seo_snapshot` for the tracked keywords, if available.
4. **Conversions.** Ask the user for leads, sales or revenue for the month and
   the source if known. AI referrals undercount (people see a brand in an
   answer, then search or type the URL), so judge on conversions, not AI
   clicks.
5. **Register.** For each page that reached 30, 60 or 90 days, fill clicks,
   impressions, and the AI count on its questions. Mark `winning`, `flat` or
   `losing` at 90 days only. Action: refresh, merge, expand, none.
6. **Learn.** Compare winning and losing pages on the features in the register
   (answer first, original data, sourced facts, length, schema, links in and
   out). State what repeats. With fewer than about 10 pages this is a note, not
   a rule.
7. **Write the report.** Fill `templates/monthly-report.md`. Top five lines:
   what moved most, what shipped, what did not work, what changes next month,
   what you need from the user.

## Each quarter

Refresh the plan: add AI panel questions, rerun keyword research, review pages
that are `flat` or `losing`, update the calendar. Keep the old panel results so
the history stays comparable, and note the date the panel changed.

## Failed-read checks before you report

- Did the scan or manual run complete on every engine? A missing engine is
  "not measured", not zero.
- Is M (the number of answers) large enough? Under about 10 answers per engine
  is a rough read, label it so.
- Did traffic drop? Run the drop checklist in `knowledge/measurement.md` before
  blaming content.
