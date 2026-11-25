# unbound-seo-geo

The full program for getting a website found in search and named in AI answers. Audit, plan, produce, measure, with a graded knowledge base behind every recommendation. One person can run it.

It's the public edition of the skill the Unbound team runs before touching a site.

```
you   > audit this site: example-dental.com
agent > Reads the site, runs the buyer questions on ChatGPT, Perplexity and Gemini,
        counts who gets named in N of M answers, lists the pages each answer read,
        and writes audit.md, a ranked list of fixes, each with its evidence grade
        and the literal how.
```

## What you get

| step | say | you get |
|---|---|---|
| 1. Audit | "audit this site: example.com" | `audit.md`, where you stand in search and in AI answers, and a ranked list of fixes |
| 2. Plan | "write the plan" | `plan.md`, keywords, pages, mentions, technical fixes and a calendar |
| 3. Produce | "write page P-001" | a paste-ready page with title, meta and schema, checked against the rules |
| 4. Measure | "monthly report" | `reports/YYYY-MM.md`, same questions, same engines, counts side by side |

Work files go in `seo-geo-work/<domain>/`.

## Install

**Claude Code.** Copy the `seo-geo` folder into your skills folder.

```bash
git clone https://github.com/danielforeroj/unbound-seo-geo.git
cp -r unbound-seo-geo/seo-geo ~/.claude/skills/
```

Then say "audit this site: example.com".

**Claude.ai.** Zip the `seo-geo` folder and upload it in Settings, Capabilities, Skills.

**ChatGPT or any other agent.** Paste `seo-geo/SKILL.md` as project instructions. When it asks for a step file, paste it (`references/1-audit.md` and the knowledge file it names).

## Two ways to get data

**By hand, no account needed.** `references/manual-checks.md` is the method. Ask the same buyer question several times per engine in a logged out window, count who gets named, write down the pages cited. Slower, still real evidence.

**With the Unbound GEO MCP.** Connect `https://unboundgeo.com/api/mcp` and the skill reads your scans, cited sources and search snapshots (`references/mcp.md`). It never runs a paid scan unless you ask in plain words.

## Every recommendation carries a grade

| grade | means |
|---|---|
| A | The search engine or AI company says it in its own docs |
| B | A study with a published sample and method |
| C | Practitioners agree, or our own data |
| D | One creator. Never quoted as fact |
| X | Against policy or disproved. On the never list |

The knowledge base is in `seo-geo/knowledge/`, one file per topic (AI answers, local, content, authority, technical, measurement, risk). Sources are listed in [CREDITS.md](CREDITS.md). Engines change every few weeks, so every claim is dated.

## Rules it never breaks

- Every number comes from a saved result or a check you ran. If it wasn't measured, it says "not measured".
- Counts are written "named in N of M answers". No percentage without its count.
- No promised rankings or citations. Nobody controls an AI answer.
- Nothing on the never list in `knowledge/risk.md`. No fake press, no page per query variant, no bought links, no review incentives, no AI rewrite of finished pages.

## Sibling skills

- [unbound-geo-content](https://github.com/danielforeroj/unbound-geo-content), short-form content about AI search with numbers only from the source.
- [unbound-geo-audit](https://github.com/danielforeroj/unbound-geo-audit), audit your brand from Claude or ChatGPT over MCP.

Rather not run it yourself? Unbound GEO does it for you under one of our managed plans.

---

Built by [Unbound GEO](https://unboundgeo.com). Get named. Then PROVE it.

MIT licensed. See [LICENSE](LICENSE).
