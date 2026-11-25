# Unbound GEO MCP

Server: `https://unboundgeo.com/api/mcp`. Add it in Claude Code with
`claude mcp add --transport http unbound-geo https://unboundgeo.com/api/mcp`,
or through your client's connector settings. Sign in when asked.

## Tools this skill uses

| tool | what it gives | use it for |
|---|---|---|
| `list_brands` | the brands in the account | find the brand id for the domain |
| `list_scans` | past scans with dates and status | pick the latest and the previous one |
| `get_scan` | one scan's results per engine | the baseline and the monthly comparison |
| `get_share_of_voice` | how often the brand and rivals appear in answers | the mention counts; report them as counts |
| `list_findings` | issues the scan found | the fix list (read each one first) |
| `list_competitors` | rivals the scan tracks | who is named instead of the user |
| `list_cited_sources` | pages and sites the engines quoted | the authority and source-gap work |
| `list_prompts` | the questions asked in scans | the AI panel, to keep it fixed |
| `get_seo_snapshot` | search data snapshot | the search baseline and rank tracking |
| `list_tracked_keywords` | keywords already tracked | the keyword map and the monthly check |
| `run_scan` | starts a new scan, spends quota | only when the user plainly asks |

Do not assume other tools exist. If a tool name is missing in the client, say
so and use the manual check for that item.

## Calling order

Audit: `list_brands`, `list_scans`, `get_scan`, `list_prompts`,
`list_competitors`, `list_cited_sources`, `list_findings`, `get_seo_snapshot`,
`list_tracked_keywords`.

Monthly: `list_scans`, `get_scan` (latest and previous), `get_share_of_voice`,
`list_cited_sources`, `list_findings`, `get_seo_snapshot`.

## Save every result

After each call, write the result to `seo-geo-work/<domain>/data/<tool>-<date>.md`
(or `.json`). Quote numbers in deliverables only from those files. If the file
is empty or the scan is not complete, treat it as a failed read.

## Read findings before using them

- A finding that names a buying criterion ("price", "support", "ease of use") as
  a competitor is noise. Drop it and say how many you dropped.
- A subdomain you own (docs, blog on another host) may be listed as third-party.
  Mark it as yours.
- A finding is a lead, not a fact about the web. Open the cited page before you
  write a fix based on it.

## Quota

Reads are free to call. `run_scan` uses the user's scan quota. Never run it on
your own, never to "refresh" before a report, never in a loop. Ask once, run
once, save the result.
