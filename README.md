# Namecheap developer documentation (offline copy)

**Last updated: 2026-11-01 (fetched from the live site)**

A readable, offline copy of Namecheap's public developer documentation: the full **API reference**, the **developer articles from the knowledge base** (API FAQ, sandbox, Dynamic DNS, WHMCS module, reseller programs) and the **Phishing Reports API terms**. Each page is kept as clean **markdown** and as the **raw HTML** the server sent. It's refreshed automatically about once a week, and a commit only appears when Namecheap actually changed the content, so `git log -p markdown/` shows what Namecheap changed and when.

Using the API? Read **[CAVEATS.md](CAVEATS.md)** first: the gotchas that aren't in the official docs, collected from the docs, Namecheap's own SDK and Terraform provider, and long-lived third-party clients.

## Why this exists

`www.namecheap.com` sits behind a Cloudflare bot challenge. `curl`, `wget`, most HTTP libraries, headless Chrome and Firefox, and AI agents' web-fetch tools all get **HTTP 403 "Just a moment..."** instead of the page. So the docs are hard to reach for anyone who isn't clicking through in a desktop browser: scripts, CI, terminal users and coding agents. On top of that, the site has broken links and an official change log that stopped in 2018 while pages kept changing.

This repo makes the docs plain files in git, so you can read, grep, diff and link to them, and point your agents here instead of having them fight the challenge. It was fetched slowly (one page every ~4 s) with a normal, unmodified headless browser. No bot-evasion tools were used.

## Start here

### Markdown (read this)

| Index | What's in it | Pages |
|---|---|---|
| [**API reference**](markdown/api/INDEX.md) | `namecheap.com/support/api/`: intro and environments, global parameters, error codes, extended attributes, transfer statuses, change log, and every method: `domains`, `domains.dns`, `domains.ns`, `domains.transfer`, `ssl`, `users`, `users.address`, domain privacy (WhoisGuard) | 74 |
| [**Knowledge base: developer articles**](markdown/kb/INDEX.md) | `namecheap.com/support/knowledgebase/`: Namecheap API (FAQ, sandbox, modules), Dynamic DNS (update URL, clients), WHMCS module, SSL and hosting reseller programs | 45 |
| [**Other developer pages**](markdown/other/INDEX.md) | Phishing Reports API terms of use (a separate API for approved security vendors) | 1 |

Each page starts with a `<!-- source: URL | fetched: TIME -->` line. Links between pages point to the local files; other site links point to namecheap.com.

### Raw HTML (the evidence)

[`html/api/`](html/api/), [`html/kb/`](html/kb/), [`html/other/`](html/other/): the server's response exactly as received (before JavaScript), one file per page. Each folder's `_status.tsv` lists URL, HTTP status, final URL after redirects, page title and fetch time. Use these to check the markdown or to convert the pages yourself.

## Things to know about the source

- **The official change log stops at 2018-02-28**, but pages changed since (e.g. SSL products renamed to SSL.com names from 2026-07-11, `ssl.getInfo` `ReturnSubscriptionInfo`, `domains.create` `BillingTaxNumber`). Use this repo's history to see what changed.
- **Site link bugs** (fixed in the markdown, left alone in the HTML): many pages link to `~/support/api/...`, an unresolved path that 404s in a browser; old `.aspx` URLs redirect to the current ones (WhoisGuard pages now live under `methods/domainprivacy/`).
- The docs contradict themselves in places (examples vs. parameter tables, mixed casing, reused error codes). Treat the parameter tables as the best guide, read [CAVEATS.md](CAVEATS.md), and test in the sandbox.

## Coverage

Checked against the site's own sitemaps (`robots.txt` → `sitemap.xml` → `nc-support-sitemap.xml`): every URL in the API section's sitemap, plus every `/support/api/` link found in those pages. From the knowledge base, the developer categories: *API & Resellers* (all of it) and *Dynamic DNS*.

## For agents

See [AGENTS.md](AGENTS.md).

## About

The fetch and conversion scripts live in a separate private repo; this repo receives only the docs. Don't send pull requests that change `markdown/` or `html/`: the next refresh overwrites them. Open an issue instead (wrong conversion, missing page, a caveat that's wrong).

Not affiliated with or endorsed by Namecheap. The documentation content is Namecheap's; this is an unofficial copy for reference.
<!-- publish test 2026-11-01T15:14:17Z -->
