# Manual AI visibility check (no tools needed)

Use this when the MCP is not connected, or to cross-check it. It takes about
an hour for a first pass. It is a small sample, so label it as one.

## Why several runs

The same question rarely returns the same list of brands twice. In a study of
2,961 runs, identical lists came back in fewer than 1 in 100 repeats, though
which brands appear is fairly stable across many runs
(`knowledge/measurement.md`). So one run proves nothing. Counting across runs
does.

## Setup

1. Write 10 buyer questions, spread across intents:
   - Shortlist: "best [category] for [buyer]"
   - Comparison: "[you] vs [competitor]", "alternatives to [competitor]"
   - Problem: "who can help me with [problem]" (phrase it so the answer names
     providers, not criteria)
   - Self-description: "what is [brand]", "is [brand] good", "what do people
     say about [brand]"
   - Local, if you serve places: "best [service] in [city]"
2. Write each the way a buyer would, in the buyer's language. Add 2 or 3
   rephrasings of your most important questions, since people phrase the same
   need very differently.
3. Pick engines: ChatGPT (with search on), Perplexity, Gemini, and Google AI
   Overviews or AI Mode where they appear. Use a logged-out or fresh chat each
   time, and the same country settings you want to measure.
4. Our working rule, not from a study: ask each question 3 times per engine
   (30 answers per engine for 10 questions). More is better. Under 10 answers
   per engine is a rough read.

## Record

One row per answer, in `data/manual-YYYY-MM.md`:

| date | engine | question | run | brands named (in order) | you named? | recommended or mentioned | pages cited |
|---|---|---|---|---|---|---|---|

Copy the cited URLs exactly. Do not paraphrase names.

## Read the results

Per engine, write:

- **Named in N of M answers** for you and each competitor. Example: "named in 7
  of 30 answers on Perplexity; Competitor A named in 19 of 30".
- Whether you were recommended or only mentioned in those N.
- The pages and sites cited most often, and which of those you own.
- Wrong, stale or missing facts about your brand. Quote the sentence and note
  the engine.

Then answer two questions:

1. Where you are absent but a competitor is named, what page does the engine
   cite? That page type is what to build or earn a place on.
2. Is the gap on your site (no page answers the question) or off it (engines
   quote other sites, lists, reviews or videos)?

## See what the engine searches for

ChatGPT rewrites a question into its own searches, often several. In Chrome,
open DevTools, Network tab, send the question, and look in the conversation
response for the search queries (search the response for "queries"). These
field names are undocumented and can change. Perplexity shows its searches
under "Steps". Use the wording as input for headings, not as a reason to build
a page per variant.

## Free paste test

Paste all answers for one intent into a Claude or ChatGPT chat and ask: "Where
is [brand] missing, who appears instead, and is the gap on the brand's site or
in third-party mentions?" Treat the reply as a hypothesis, and verify each
claim against the saved answers.

## Do not

- Change the panel mid-month.
- Compare counts across different M without saying so.
- Report a position ("we were third") inside an answer.
- Use an answer you did not record.
