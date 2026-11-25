# Measurement

Conclusion: there is no position inside an AI answer. Count how often you are
named across many runs, per engine, and write the count. Judge the program on
conversions, not AI clicks.
Grades: A official, B study, C practitioners or own data, D one creator.

## Writing rules for numbers

- Always "named in N of M answers". A percentage may follow, never stand alone.
- In prose say "how often you are named" or "mention rate". Do not say "share
  of voice".
- Never report a rank or order inside an AI answer.
- A figure from a study is quoted with its sample and date. A figure from the
  user's own checks is quoted with N and M. A number with neither is not used.
- Every number comes from a saved result or the user's own check. If missing,
  write "not measured".
- Never promise a ranking, a citation or a date by which one appears.

## Why counts

In SparkToro's 2,961-run study, the same prompt gave the same brand list in
fewer than 1 in 100 repeats and the same order in about 1 in 1,000, with list
length from 2 to 10 or more (B). The brands that appear are fairly stable over
many runs. SparkToro recommends 60 to 100 runs per prompt for stable figures
(B), which is more than most manual checks reach. So a small run is a rough
read and should say so.

People also phrase the same intent very differently (average prompt similarity
0.081, B), so use a panel of phrasings, not one "ideal" prompt.

## What a report shows, per engine and intent

- Named in N of M answers for the brand and each top competitor.
- Recommended versus only mentioned.
- Sources quoted, and which of them the user owns.
- What each engine says about the brand, and what is wrong.
- Trend over months, not week to week noise.

Three useful metrics (C, Growth Memo): presence (the share of tracked prompts
where you appear in any engine, written as a count of prompts), portability
(how many cited URLs appear in all engines, usually very few) and
concentration (how much of your citations come from one engine).

## Search Console

- **Generative AI report.** Google's guide says impressions from AI features on
  Search can appear in a dedicated report where available (A). Otherwise AI
  Overviews and AI Mode traffic is counted inside the normal Performance report,
  Web search type, with no breakdown (A).
- **Query rows are incomplete, totals are not.** Comparing the aggregate and
  query-level data on 10 US B2B SaaS sites, Growth Memo found about 75% of
  impressions and 38% of clicks were filtered out of query rows (C, small
  sample). Read query reports as a sample.
- **Striking distance:** queries at average position about 3 to 20.
- **Low click rate:** high impressions, click rate under about 1%.
- **Page gaps:** a top page's query export plus the article into an LLM, ask for
  uncovered clusters.
- **Commercial queries:** regex `(best|top|vs|review|comparison|alternative)`.
- **Cannibalization:** export query plus page, find queries where two pages
  compete, then merge, canonicalize or differentiate.
- **Long queries** (7 or more words) hint at conversational searches. They do
  not prove AI origin.

## Analytics

- Build a filter on source or medium with regex
  `chatgpt|openai|perplexity|gemini|copilot|claude`. AI referrals undercount by
  design: people see a brand in an answer and search or type the name later,
  and unlinked mentions send nothing. A tracking parameter change can make
  referrals vanish with no real change (D), so check non-AI traffic before
  reacting to an AI drop.
- Measure conversions and revenue per visit by channel, not clicks alone.

## If traffic dropped, check in this order (A)

1. Technical: crawl stats, indexing, robots.txt or firewall changes, a
   migration, a broken template.
2. Seasonality: compare with the same month last year and Google Trends.
3. Algorithm updates: check the Google Search Status Dashboard dates against
   the drop, and the size of the position shift.
4. Security issues or manual actions in Search Console.
5. Which pages and queries dropped, before rewriting anything.

Changes can show in hours or take months. Wait a few weeks before judging (A).

## Tools named by practitioners (none tested here for accuracy)

Crawl: Screaming Frog, Sitebulb. Google's own: Search Console, URL Inspection,
Rich Results Test, Schema Markup Validator, PageSpeed Insights, Trends, GA4.
Keywords and links: Ahrefs, Semrush. AI visibility tracking: Peec, Profound,
Ahrefs Brand Radar, Unbound GEO. Questions: AlsoAsked, AnswerThePublic,
SparkToro. LLMs are good at audit grunt work (redirect chains, crawl export
triage, query clustering) and weak at strategy and voice (D).
