# Technical: the floor everything stands on

Conclusion: being indexable, crawlable and snippet-eligible is the whole
technical requirement for Google's AI features. Check access at every layer,
make sure core content is in the HTML, treat schema as hygiene.
Grades: A official, B study, C practitioners or own data, D one creator.

## The minimum (A)

- Googlebot is not blocked, pages return 200, content is indexable, no spam
  violation. That is the full requirement for AI Overviews and AI Mode.
- Google's AI optimization guide says a site must be included in the "Search
  generative AI" setting in Search Console to be eligible. Open Search Console
  settings and check whether that option appears for your property. If it does
  not, note "not found" rather than guessing.
- Crawl access open at every layer: robots.txt, and the CDN, hosting provider
  and firewall. CDN-level blocking is the one audits miss. Ask whoever manages
  hosting whether any bot rule or "block AI bots" toggle is on.

## OpenAI bots, one by one (A, OpenAI bot docs)

| bot | job | what to do |
|---|---|---|
| `OAI-SearchBot` | decides whether your site can appear in ChatGPT search answers | allow it in robots.txt and allow its published IP ranges at the firewall |
| `GPTBot` | training data | block or allow as a business choice, it does not affect ChatGPT search inclusion |
| `ChatGPT-User` | fetches pages a user asks about | OpenAI says robots.txt rules may not apply to it |
| `OAI-AdsBot` | visits pages submitted as ChatGPT ads | ignore unless you run ads there |

Changes to robots.txt can take about 24 hours to be picked up. To allow the
search bot, make sure robots.txt contains no `Disallow` for it and add:

```
User-agent: OAI-SearchBot
Allow: /
```

Get the current IP list from the OpenAI bots documentation and give it to
whoever manages the firewall.

`Google-Extended` controls training and grounding in some other Google
systems, not Search. Blocking it does not remove a site from AI Overviews.
`nosnippet`, `data-nosnippet`, `max-snippet` and `noindex` do limit AI display,
at the cost of visibility (A).

Default for a business: allow Googlebot, Bingbot and OAI-SearchBot. Blocking
training bots is a business choice to explain, not a default.

## Client-side rendering is the most common failure on new sites (C)

Sites built with AI site builders or client-side React often ship an empty HTML
shell. Google renders it with a delay. AI fetchers often do not run JavaScript.
Test: view page source, or fetch with JavaScript disabled. If the main content
is not in the HTML, it is a finding. Fix: server-side rendering or static
generation (Next.js, Astro, or your platform's equivalent). Core content as
text, links as `<a href>` with descriptive anchors (A).

## Structure

- Important pages in the main menu and internally linked. A page with no
  internal links is invisible in practice (C). Within about 3 clicks of the
  home page is a common rule of thumb (D).
- Descriptive words in URLs. Group large sites in directories (A).
- Redirect instead of duplicating. Canonical when you cannot redirect (A).
  Duplicate content is not a penalty, it wastes crawl and splits signals.
- Keep the brand's content on one domain (D, one case).
- Pages with 60 or more navigation links may give agents little real content on
  first read (B vendor, no sample size, a hypothesis to check).

## Schema is hygiene, not a GEO lever

- Not required for AI features, and there is no special schema for AI (A).
- Use it for rich results: it must match visible content. Validate with Google's
  Rich Results Test and the Schema Markup Validator (A).
- Types that matter for shopping and booking features: Product,
  MerchantListing, LocalBusiness, Event, JobPosting (A).
- Organization and author schema: cheap, no evidence of citation effect (C).
- Ahrefs (6 million URLs): cited pages had more JSON-LD, but 1,885 pages that
  added schema saw AI citations barely move (B). Correlation, not cause.

## `llms.txt`

Google says Search does not use it, and creating one is fine but unnecessary
(A). OpenAI's crawler documentation mentions only robots.txt and IP ranges (A,
by omission). Do not build or sell it. Leave an existing one.

## Speed and crawl errors

Fix pages that are really slow. Chasing a perfect score does not move rankings
(D). Google says page experience matters as a whole (A). Fix redirect chains,
404s that have inbound links, missing titles and non-indexable money pages by
impact. "Crawled, currently not indexed" lists are mostly noise: sort them by
page importance before reacting (D).

## Sitemaps

Optional but useful for large or deep sites (A). Submit in Search Console
(Sitemaps, paste the URL) and Bing Webmaster Tools. Bing matters because
practitioners report ChatGPT search leans on it, which OpenAI has not confirmed
(D).
