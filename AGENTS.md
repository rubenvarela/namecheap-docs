# AGENTS.md

You're reading an offline copy of Namecheap's developer documentation. It's here so you don't have to scrape namecheap.com, which blocks automated clients behind a Cloudflare challenge (see [README.md](README.md#why-this-exists)).

## 1. Read [CAVEATS.md](CAVEATS.md) first

Before you write or run anything that calls the Namecheap API, read **[CAVEATS.md](CAVEATS.md)**. The official docs leave out behavior that breaks things, and CAVEATS.md has the research already done, with sources. Don't redo it; add to it. The most damaging ones:

- `domains.dns.setHosts` **replaces the whole zone** and silently resets mail routing (`EmailType`) if you leave it out (2.1, 2.4).
- Errors come back as **HTTP 200** with `Status="ERROR"`; rate limiting is **HTTP 405** (1.1, 1.2).
- The API key is **account-wide** and can spend money; charge-bearing calls are **not idempotent**, so never auto-retry them (1.5, 5.1).

Where CAVEATS.md and the official pages disagree, CAVEATS.md explains why. Most items are from docs and other clients' observations, not tests; the unverified ones are listed at the end.

## 2. Find the page

| Need | Start at |
|---|---|
| API methods, parameters, error codes | [`markdown/api/INDEX.md`](markdown/api/INDEX.md) |
| FAQ, limits, sandbox, Dynamic DNS, WHMCS, resellers | [`markdown/kb/INDEX.md`](markdown/kb/INDEX.md) |
| Phishing Reports API terms | [`markdown/other/INDEX.md`](markdown/other/INDEX.md) |

File names are the URL path with `/` replaced by `__`, e.g. `https://www.namecheap.com/support/api/methods/domains-dns/set-hosts/` → [`markdown/api/methods__domains-dns__set-hosts.md`](markdown/api/methods__domains-dns__set-hosts.md). Grepping works well: `grep -ril emailtype markdown/`.

`html/` has the raw pages as the server sent them, with fetch metadata in `html/*/_status.tsv`. Use it only to check the markdown.

## 3. Rules

- **Don't fetch namecheap.com to read the docs.** Use this copy. It's refreshed about weekly, and the first line of each page says when it was fetched. If you really need the live page, a human with a browser is the reliable way; don't try to get around the challenge.
- **Don't edit `markdown/` or `html/`.** They're regenerated on each refresh; report problems as an issue.
- Cite pages by their source URL (in the `<!-- source: ... -->` line) when you quote them to a human.
- Namecheap's own change log isn't maintained. To see what changed, use this repo's history: `git log -p -- markdown/api/<page>.md`.
