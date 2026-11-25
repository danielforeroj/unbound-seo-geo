# Tracker: calendar and register

Copy these two tables into a spreadsheet or keep them as a file. Ids stay
stable for the life of a page.

## Calendar

| id | month | type | need | keywords | AI questions | business supplies | owner | due | status | doc | route |
|---|---|---|---|---|---|---|---|---|---|---|---|

Status: `brief`, `draft`, `human`, `fact-check`, `approval`, `publishing`,
`live`. Route: `cms`, `pull-request`, `ticket`, `listing`, `kit-only`.

## Register (one row per live page)

| id | url | published | answer first | original data | sourced facts | words | schema | links in | links out |
|---|---|---|---|---|---|---|---|---|---|

| id | d30 clicks | d30 impr | d30 AI named (N of M) | d60 clicks | d60 impr | d60 AI named | d90 clicks | d90 impr | d90 AI named | cited itself? | verdict | action |
|---|---|---|---|---|---|---|---|---|---|---|---|---|

Verdict: `winning`, `flat`, `losing`, set at 90 days. Action: refresh, merge,
expand, none. "Cited itself?" is yes if the page URL appears among cited
sources in your scan or manual check.
