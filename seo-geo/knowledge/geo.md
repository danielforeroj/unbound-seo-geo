# GEO: how AI engines pick sources

Conclusion: AI answers sit on top of search retrieval. What moves citation is
plain: be retrievable, match the real question in your headings, answer early,
back claims with sources, and be present on the sites engines already quote.
Grades: A official, B study, C practitioners or own data, D one creator.

## How the engines get their sources

- **Google AI Overviews and AI Mode run on core Search.** They retrieve from the
  Search index and fan a question out into several related searches. To appear,
  a page must be indexed and snippet-eligible. Google lists no other technical
  requirement. (A, Google AI features page and AI optimization guide)
- **Overviews and AI Mode are different surfaces.** Overviews show only when
  Google judges them additive. AI Mode targets exploration and comparison and
  may link differently. (A, Google AI features page)
- **ChatGPT cites what its web search retrieves.** In an Ahrefs study of 1.4
  million prompts, 88% of cited URLs came through the general search channel,
  and ChatGPT cited roughly half of what it retrieved. (B)
- **The prompt is not the query.** ChatGPT rewrites a question into its own
  searches. See them in DevTools (`references/manual-checks.md`). Perplexity
  shows its searches under "Steps". (C)
- **Which index backs ChatGPT or Claude search** is asserted by practitioners and
  not documented by OpenAI or Anthropic in our sources (D). Do not sell on it.

## Engines barely agree

In a Growth Memo analysis of 3.7 million citations, 2.37% of cited URLs
appeared in ChatGPT, Perplexity and AI Overviews for the same prompt, and 91%
appeared in one only. (C, sample skewed to Europe and B2B.) So: test and measure
each engine on its own. Results on one engine do not transfer.

## Answers vary run to run

SparkToro ran 2,961 prompts and found the same brand list returned fewer than 1
time in 100, the same order about 1 in 1,000, with list length from 2 to 10 or
more. Which brands appear is more stable across many runs. (B, not peer
reviewed.) This is why we count across runs (`measurement.md`).

## Ranking helps but no longer guarantees citation

| study | surface | result |
|---|---|---|
| Ahrefs, Jul 2025 | AI Overviews, top 3 citations per overview | 76% of cited pages ranked top 10 |
| Ahrefs, Mar 2026 | AI Overviews, all URLs, 863K keywords, new parsing | 37.9% ranked top 10, 31% outside top 100 |
| seoClarity, Sep 2025 | AI Mode, 1,000 transactional queries | 19% of citations from the top 20 |
| BrightEdge | AI Overviews, 2025 to 2026 | overlap moved between studies with different methods |

The two Ahrefs numbers use different counting rules, so quote the direction
(less direct overlap over time), not a precise drop. (B, all vendors.)
Industry matters: BrightEdge found high overlap for B2B tech and healthcare and
low overlap for e-commerce and restaurants. For the first group, classic SEO
carries most of the weight. For the second, third-party presence and sub-question
coverage matter more. (B)

## What gets a page cited, best evidence first

1. **Retrieval rank, then heading match (B).** In AirOps data analyzed in Growth
   Memo (16,851 queries, Apr 2026), the page's rank in ChatGPT's retrieval
   predicted citation best, and how closely the best heading matched the query
   came second. Covering every subtopic added little over covering none.
   How: put the buyer's question, in their words, in the H1 or an H2.
2. **Title and URL that say the answer (B).** Ahrefs found cited pages had
   closer title-to-prompt similarity and more natural-language slugs. This is
   correlation. How: title, slug, H1 and first sentence state what the page
   answers.
3. **Sourced facts, statistics and quotes in the text (B, lab).** In the 2024
   GEO paper, adding them raised visibility on its main metric, and keyword
   stuffing scored below doing nothing. It was a lab with an older model, so use
   it as direction. How: link each statistic to its source where you state it.
4. **Answer first (C).** A Growth Memo analysis of 18,012 ChatGPT citations found
   44.2% came from the first 30% of the page. Correlation, one engine. How: the
   direct answer in the first 40 to 100 words.
5. **Do not rewrite the body with an AI "GEO optimizer" (B, lab).** A 2026
   simulation across 171,003 documents found body-only rewrites lowered
   visibility, while improving titles, descriptions and headings raised
   retrieval. How: edit structure, leave a good human body alone.
6. **Original information (A, C).** Google says unique, non-commodity content
   influences generative AI presence more than its other suggestions. Original
   data helps most when packaged: a named benchmark answering a "which is best"
   question, the result in the first 30% of the page, visible method, a stable
   URL (C, Search Engine Land analysis of 301 AI-cited pages).
7. **Freshness breaks ties (B).** Relevance does the work within a retrieved
   set. Changing dates without substance does not work (A).
8. **Format by query type.** Comparison, alternatives and "best X for Y" pages
   are where B2B citation competition sits (B/C). Write them honestly
   (`risk.md`).

## Third-party sources carry a lot

A University of Toronto preprint (1,000 consumer ranking prompts, Sep 2025)
found AI search leans on earned media (independent sites) much more than
Google's results do, with differences by engine and vertical (B, direction
only). Peec reports Reddit, YouTube, LinkedIn, Wikipedia and review sites among
the most cited domains (B vendor). Ahrefs finds YouTube a leading cited domain
in AI Overviews (B).

How: take the `list_cited_sources` output or your manual list. Every third-party
page cited for your category is a target. See `authority.md`.

**Reddit.** It is retrieved often and cited less than you would expect, and its
share swings with model changes (B vendor, Ahrefs, Peec, Promptwatch). Join
real threads honestly if it fits your field. Do not use Reddit as a KPI. A
business posting for itself gets banned (C).

**Not English?** Peec found ChatGPT ran many Spanish-prompt sessions with some
English searches (B). If buyers are international, English presence still
matters.

## Tactic verdicts

| tactic | grade | verdict |
|---|---|---|
| One page per real distinct need, answering its sub-questions | A/B | do it |
| Title, slug, H1, first sentence say the answer in users' words | B | do it |
| Sourced statistics, quotes, citations | B (lab) | do it |
| Direct answer first | C | do it |
| First-hand data, ratings, case results | A/C | do it, core of the offer |
| Honest comparison and alternatives pages | C | do it for B2B |
| Placement on third-party lists, reviews, trade press | C | do it |
| YouTube with transcripts for key topics | B | test if you can make video |
| A page per fan-out wording | A against | never |
| `llms.txt` | A, Google ignores it | skip |
| Special schema "for AI" | A, not needed | normal schema only |
| Chunking content into tiny pieces for AI | A, not needed | write for readers |
| Self-ranked "best X" listicle | X | never |
| AI "GEO optimizer" rewrite of a body | B lab | avoid |

## Agents and shopping

Google's guide covers agent features that use Product, MerchantListing,
LocalBusiness and Event data plus Merchant Center (A). Relevant now only for
e-commerce and booking businesses. For B2B services, park it.
