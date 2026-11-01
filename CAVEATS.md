# Namecheap API caveats and workarounds

The API is old and crude: XML only, one full-zone write call for DNS, no transactions, undocumented rate-limit behavior, and several fields that don't mean what they say. Everything below was collected 2026-10-31/11-01 from these sources:
- the official API docs, fetched live on 2026-11-01 (this repo's [`markdown/api/`](markdown/api/INDEX.md); the authority);
- older Internet Archive snapshots of the same pages (2025-07 to 2026-08);
- Namecheap knowledge-base/FAQ articles;
- Namecheap's own SDK and Terraform provider (code, README, issues);
- long-lived third-party clients.

It was checked against the official pages on 2026-11-01. **Nothing was tested against the live API.** Each item names its evidence (links in [Sources](#sources) at the end). Page references like `[official setHosts]` mean the matching file in [`markdown/api/`](markdown/api/INDEX.md), e.g. `methods__domains-dns__set-hosts.md`.

Legend:
- **[official]** = the API doc pages in [`markdown/api/`](markdown/api/INDEX.md).
- **[KB]** = Namecheap knowledge-base/FAQ articles ([`markdown/kb/`](markdown/kb/INDEX.md)).
- **[NC-SDK]** / **[NC-TF]** = Namecheap's own go-namecheap-sdk / terraform-provider-namecheap (README, code, issues; many are live-API observations).
- **[3P]** = third-party clients (DNSControl, acme.sh, ncheap, lego).
- **[ours]** = the compilers' interpretation or advice.

---

## 1. Transport, auth, and responses

| # | Caveat | Workaround |
|---|---|---|
| 1.1 | **HTTP 200 on errors.** Failures come back as `<ApiResponse Status="ERROR">` with `<Errors><Error Number="...">` [official intro]. A response can carry several errors. HTTP 200 on errors: [NC-SDK][3P] | Parse XML, require `Status="OK"`. Treat a missing/empty `Status` as a parse failure, not success. |
| 1.2 | **Rate limiting = HTTP 405**, not 429, with no documented body. [NC-SDK][NC-TF #362][3P DNSControl] Some clients also report HTTP 429 or in-band error `500000` [3P ncheap]. | Treat 405/429/`500000` as "rate limited". Wait **≥60 s** (a full window) before retrying; short exponential backoff just burns more quota. [ours] |
| 1.3 | **The limits disagree, and the API pages give none.** The KB/FAQ says 50/min, 700/hour, 8,000/day per key [KB]. Namecheap support told DNSControl 20/min (2017), and Namecheap's own SDK/provider use 20/min; the provider observed the 21st call in a minute failing in sandbox (2026-10) [NC-TF #362]. | Budget **≤10–15 calls/min**, space calls ~3–5 s apart, and pause between batches [ours]. The quota is per account/key, shared by every script and machine. |
| 1.4 | **IPv4 whitelist only.** At least one IP must be whitelisted, in the web UI [official intro]. `ClientIp` must match the whitelisted address. The whitelist can't be managed via the API: there's no command for it. | Whitelist your server's public IPv4 in the web UI. On a dynamic IP, expect auth failures (`1011150`) after it changes. |
| 1.5 | **API key is account-wide.** No scopes, no read-only keys, no per-domain keys. It can buy domains and wipe zones. [3P ncheap] (no KB page states it) | Keep it out of version control (e.g. an untracked `.env`, mode 0600). Use client-side guards (read-only allowlist, explicit `--yes`, spend caps). |
| 1.6 | **Docs say GET; secrets in URLs leak.** Official examples use GET query strings, but the docs **recommend** POST for `setHosts` with >10 hosts and for `domains.create` [official]. Every serious client sends **POST form bodies** [NC-SDK][3P]. | Always POST `application/x-www-form-urlencoded` over HTTPS. Never log the request. |
| 1.7 | **Dates have no single format** and no timezone: `MM/DD/YYYY` in lists, non-padded `M/D/YYYY` in ssl.getInfo, `12/14/2034 1:01:07 PM` (with U+202F before PM, sometimes 2-digit year) from `domains.renew`, `0001-01-01T00:00:00` meaning "never". [NC-SDK docs + #177/#203] | Parse leniently, per field. Don't sort the raw strings. |
| 1.8 | **API access eligibility**: ≥20 domains, or ≥$50 balance, or ≥$50 spent in 2 years [KB]. The API pages only say production access requires meeting "our requirements" [official intro]. | If access gets disabled, check eligibility first. |
| 1.9 | **Sandbox ≠ production.** It needs its own account, key and whitelist [official intro]. Its data differs: production-registered domains show as available, sandbox registrations can't be deleted, there are no coupons, [KB]; pricing and behavior aren't guaranteed to match [3P]. | Use sandbox for shape-testing only; still be careful in production. |
| 1.10 | **The official docs are stale and incomplete.** The change log stops at 28-Feb-2018, yet pages were edited in 2025–26 with no new entries [official]. Not documented: rate-limit responses, `EmailType` values `NONE`/`GMAIL`, SRV commands, `getHosts` returning `EmailType`, `getInfo` `DnsDetails` fields beyond `ProviderType`, and date formats. `IsLocked` is documented as "domain changes are not allowed", but it isn't the transfer lock (4.1). Examples disagree with real responses: `<Host>` in the docs vs `<host>` that clients parse; several examples have no XML namespace, and the setHosts example uses `https://` where the others use `http://`. [official][NC-SDK][3P] | Treat the docs as a parameter list, not a behavior spec. Parse XML case-insensitively and namespace-agnostically. Trust the caveats here over the docs where they conflict. |
| 1.11 | **The docs site sits behind a Cloudflare bot challenge.** It blocks curl, WebFetch, and headless Chromium and Firefox (403 "Just a moment..."). Plain headless WebKit works. The site has quirks: many pages link to unresolved `~/support/api/...` paths (404s), and old `.aspx` URLs redirect to clean ones (WhoisGuard → `/methods/domainprivacy/`). [observed 2026-11-01 while building this copy] | Read this repo instead of scraping the site. If you must refresh, use a plain headless WebKit (Playwright) or the Internet Archive (`web.archive.org/web/<timestamp>id_/<url>`). No bot-evasion tooling. |
| 1.12 | **ToS:** drop-catching via API is banned [KB]; suspension for high-volume/abusive automation [3P ncheap]. | Keep automation low-volume. |
| 1.13 | **Resetting or disabling the API key breaks every app that uses it immediately.** [official intro] | Update every stored copy of the key straight after a reset; expect auth errors until then. |
| 1.14 | **Methods only work for domains registered with Namecheap and present in your account** (not domains merely using Namecheap DNS). [official methods.md] | |
| 1.15 | **`users.resetPassword` must omit `UserName`**; every other call needs it. Official examples mix the case of parameter names (`apiuser`, `mailbox1`). [official] | |

## 2. DNS host records (`domains.dns.getHosts` / `setHosts`)

| # | Caveat | Workaround |
|---|---|---|
| 2.1 | **`setHosts` replaces the whole zone.** It's the only DNS write call; any record you don't send is deleted. [official][NC-SDK #49] | Always read → modify → write the full set. Back up the `getHosts` XML first. Refuse writes that would empty the zone. |
| 2.2 | **Not transactional, no compare-and-swap.** A concurrent change between your read and write is silently lost (last writer wins). [NC-SDK] | One editor per domain at a time (lock). Re-read after writing and diff against what you intended. |
| 2.3 | **A successful write can look failed.** Under rate limiting, the verification `getHosts` after a good `setHosts` is the call that gets the 405, so tools report failure although the change is live. [NC-SDK #193] | On error after a write, **re-read before retrying**; never blindly resend. |
| 2.4 | **`EmailType` is zone-level and rides on `setHosts`**, where it's marked required [official]. Leaving it out (or sending the wrong one) silently changes or switches off mail routing. Documented values: `MXE`, `MX`, `FWD`, `OX` [official]. Clients also use `NONE` and `GMAIL` (undocumented) [NC-SDK][NC-TF #361][3P ncheap]. | Read the current EmailType (from the `getHosts` result or `domains.getInfo` → `DnsDetails@EmailType`; neither is in the docs [NC-SDK]) and resend it unchanged on every `setHosts`, unless you're deliberately changing mail. |
| 2.5 | **MX ↔ EmailType coupling is undocumented and murky.** MX records generally need `EmailType=MX`; adding the first MX or removing the last needs an EmailType change in the same write. `OX` (Private Email) and `GMAIL` zones keep provider MX records while the type stays OX/GMAIL. Namecheap's SDK can't round-trip those zones, and its error wrongly suggests switching to `MX`, which **disconnects the hosted mailbox**. [NC-SDK README + #162][NC-TF #361] | On OX/GMAIL zones: raw `getHosts`/`setHosts` with the existing EmailType, change only non-mail records, and check mail afterwards. Never "fix" by switching to `MX`. |
| 2.6 | **Changing an MX preference is ignored.** Namecheap keeps the stored `MXPref` for an existing host+mailserver; sending the same server twice at different prefs keeps only one. [NC-TF #382][3P DNSControl #4637] | Two writes: remove the MX record, then add it back with the new pref. Expect a brief gap; avoid doing it to your only MX. |
| 2.7 | **TXT values:** no double quotes, not empty, no leading/trailing spaces [3P DNSControl audit rules]. Values >255 bytes must be sent **joined and unquoted**; Namecheap splits them itself. Sending pre-split `"a" "b"` corrupts the record (adds a space) [3P DNSControl #5036]. XML entities in returned values (e.g. `&quot;`) need decoding before you resend [3P acme.sh]. | Send the raw TXT string. Decode XML entities from `getHosts`. |
| 2.8 | **CAA is documented two ways.** The parameter table lists separate global `Flag` (0–255, "use 0") and `Tag` (issue/issuewild/iodef) parameters, which aren't numbered per record. But the official POST example and every client put the full rdata in `Address` (`0 issue "letsencrypt.org"`). [official][3P DNSControl] Changing the flag (0 → 128) doesn't work [3P DNSControl #4635]. | Put the full rdata in `AddressN` with flag 0. Remove and re-add if a CAA change doesn't stick. |
| 2.9 | **SRV records aren't in `setHosts`.** They use separate, **undocumented** commands `namecheap.domains.dns.getsrvrecords` / `setsrvrecords` (`SrvCount`, `ServiceN`, `ProtocolN`, `PriorityN`, `WeightN`, `PortN`, `TargetN`). SRV records have no TTL. [3P DNSControl / willpower232/go-namecheap] | Use a client that supports them (DNSControl) or add SRV in the web UI. Not in the official reference: unverified. |
| 2.10 | **Apex NS records can't be set on BasicDNS** (only Namecheap's own). A single NS on a subdomain also misbehaves; pairs work. [3P DNSControl] | Use `setCustom` for delegation of the whole domain; use ≥2 NS for subdomain delegation. |
| 2.11 | **TTL:** the official range is **60–60000, default 1800** [official setHosts page]. Namecheap's SDK mirror wrongly says 300–60000. "Automatic" (from the web UI) reads back as **1799**. [official][NC-SDK][NC-TF] | Always send an explicit TTL. Treat 1799 as "automatic" when diffing. |
| 2.12 | **Parking records appear on empty zones.** A new/emptied zone gets `www CNAME parkingpage.namecheap.com.` + `@ URL http://www.<domain>/`. [3P DNSControl][NC-TF changelog #262] | Treat exactly that pair as "empty zone". Remove them deliberately if not wanted. |
| 2.13 | **Use lowercase** for hostnames, addresses and nameservers; mixed case can cause undefined behavior and spurious diffs. [NC-TF docs] | Lowercase before sending and when comparing. |
| 2.14 | **`URL`, `URL301`, `FRAME` are Namecheap redirect pseudo-records**, not DNS. They're listed as record types [official], and URL forwarding doesn't work on custom nameservers [official setCustom]. `MXE` takes an IP, and Namecheap synthesizes MX+A from it [3P Perl]; the docs only say "custom MXE record". | Don't expect them to survive moving DNS to Cloudflare. |
| 2.15 | **Only Namecheap BasicDNS zones are editable.** PremiumDNS/FreeDNS can't be managed via the API [KB]. But `getList` `IsOurDNS` is **true for BasicDNS or PremiumDNS** [official], so it isn't proof that a zone is editable. Domains on Namecheap web-hosting DNS show `IsOurDNS=false` and are refused with `2030288` "not using proper DNS servers" [3P acme.sh]. If the domain uses custom nameservers (Cloudflare), Namecheap host records are irrelevant. | Check `IsUsingOurDNS` (getHosts/dns.getList: "Namecheap's default name servers") rather than `IsOurDNS`. For zones on another provider (e.g. Cloudflare), manage records there. |
| 2.16 | **Only the registered root domain works** as SLD/TLD, not subdomains [NC-TF]. Multi-label TLDs (`co.uk`) need Public-Suffix-aware splitting [3P ncheap]. IDNs must be Punycode (stated for `domains.create`, with `IdnCode`) [official], for searches too [KB]. | Split with the PSL; convert IDNs to Punycode. |
| 2.17 | **No BIND zone import/export.** [KB] | Script `getHosts` → zone file yourself, or use DNSControl (`get-zones`). |
| 2.18 | **The official setHosts "POST example" is an internal JSON shape** (`authDetails`, `RequestValues`, `AllowWhenDomainLocked`...), not the form body the API takes. `MXPrefN` is marked required for every record. [official] | Build a normal form body. Send `MXPrefN` (e.g. 10) on every record. [ours] |

## 3. Nameservers and email forwarding

| # | Caveat | Workaround |
|---|---|---|
| 3.1 | **`setCustom` turns off Namecheap extras**: URL forwarding, email forwarding and Dynamic DNS stop working. [official] | Expected when moving to Cloudflare; recreate redirects there. |
| 3.2 | **Nameserver list limits**: comma-separated, no spaces, max 12 [3P]; the `Nameservers` parameter allows 1200 chars [official]. | |
| 3.3 | **`setEmailForwarding` replaces all forwards;** sending none deletes all [3P][NC-TF #361]; the official page doesn't say so. Forwarding needs `EmailType=FWD` on Namecheap DNS ("MX records for our Free Email Forwarding service") [official setHosts]. The email-forwarding calls take `DomainName`, not `SLD`/`TLD` [official]. | Read → modify → write, like `setHosts`. |

## 4. Domain and account data

| # | Caveat | Workaround |
|---|---|---|
| 4.1 | **`getList` `IsLocked` is not the transfer lock.** The docs define it as "domain changes are not allowed" [official]. It reads `false` on domains whose registrar lock is on, so it's likely a registry/dispute hold [NC-TF #377][3P ncheap]. | Use `domains.getRegistrarLock` for transfer-lock status. |
| 4.2 | **No API to toggle auto-renew.** `AutoRenew` is read-only in `getList`. [NC-SDK #141] | Web UI only. |
| 4.3 | **No DNSSEC / DS record management.** Confirmed by Namecheap staff (2024) and still absent. [NC-SDK #140] | Web UI only (Advanced DNS). |
| 4.4 | **`getInfo` is incomplete**: `LockDetails` comes back empty and there's no auto-renew field [NC-SDK docs]. The official example also leaves `LockDetails` empty and shows only `DnsDetails@ProviderType` [official]. | Combine `getList` + `getRegistrarLock` + `getInfo`. |
| 4.5 | **Paging defaults to 20 items** (`PageSize` 10–100) [official]. Clients that don't page silently miss domains [3P DNSControl #4330]. Other lists differ: `transfer.getList` defaults to 10 (10–100); `whoisguard.getList` PageSize runs 2–100 [official]. | Always page until `TotalItems` is reached, PageSize=100. |
| 4.6 | **`domains.check` takes ≤50 domains** (`2011169`). [official] | Chunk. |
| 4.7 | **`users.login` only works for API-created sub-accounts**, not normal namecheap.com accounts. [official] | Don't use it to validate credentials; use `users.getBalances`. |
| 4.8 | **`domains.renew` result**: `NumYears` is frequently 0. [NC-SDK docs] | Use `ExpiredDate`. |
| 4.9 | **Whoisguard naming**: the product is now "WithheldforPrivacy", but commands remain `namecheap.whoisguard.*` and some parameters still say Whoisguard [official]. `allot`/`unallot`/`discard` have no method pages but do appear in the official error-code list [official error-codes]. Their parameters come from SDKs [NC-SDK]. `discard` is destructive. | |
| 4.10 | **`setRegistrarLock` without `LockAction` locks the domain** (default `LOCK`). [official] | Always send `LockAction` explicitly. |
| 4.11 | **`setContacts` needs all four contact sets** (Registrant/Tech/Admin/AuxBilling); missing ones fail with `2010324`–`2010327`. It's effectively a full replace. [official] | Read with `getContacts`, modify, send all four. |
| 4.12 | **Cache `getTldList` and `users.getPricing`**: the docs "strongly recommend" it. [official] | Cache locally (e.g. daily); saves rate-limit budget. |
| 4.13 | **The API can't add privacy to an existing domain** (no new privacy subscription for an existing domain name). [official domainprivacy page, added 2025–26] | Web UI, or set `AddFreeWhoisguard`/`WGEnabled` at `domains.create`. |
| 4.14 | **`ssl.getInfo` has `ReturnSubscriptionInfo=true`**, which adds `Years`, `SubscriptionStartDate`, `SubscriptionEndDate` and `SubscriptionDuration`. [official, added 2025–26] | Use it to track subscription vs. certificate expiry. |
| 4.15 | **`users.getBalances` `FundsRequiredForAutoRenew`** = funds needed for auto-renewals expiring within 90 days. [official] | Check it so auto-renew doesn't fail on low balance. |

## 5. Money-spending calls

| # | Caveat | Workaround |
|---|---|---|
| 5.1 | **Charge-bearing calls aren't idempotent**: `domains.create/renew/reactivate`, `domains.transfer.create`, `ssl.create/renew/purchasemoresans` and `whoisguard.renew`. A network error after sending may still have charged [NC-SDK][3P ncheap]. `users.createaddfundsrequest` only returns a credit-card redirect URL; no charge happens until the card form is submitted [official]. | **Never auto-retry.** After an ambiguous failure, check `getList`/`getInfo`/`users.getBalances` before doing anything. |
| 5.2 | Paid from **account balance only** [KB][3P ncheap]. The actual charge can exceed the listed price: `check` returns `IcannFee`, and results give `ChargedAmount` [official]. Premium domains need `IsPremiumDomain`/`PremiumPrice` (and `EapFee`) [official]. **Premium registration during EAP isn't supported via the API** [official]. | Check `users.getPricing` and `domains.check` first; set a max price. Require a human's approval before any call that spends money. |
| 5.3 | **`transfer.create`** takes `Years=1` only and a limited TLD list. The two official lists disagree: methods.md adds `.co.uk`/`.me.uk`/`.org.uk`, but the transfer.create page omits them. EPP codes with special characters go as `EPPCode=base64:<encoded>`. `AddFreeWhoisguard` defaults to **Yes**. [official] | Check `getTldList` `IsApiTransferable` first. |
| 5.4 | **`domains.create` `Years` defaults to 2.** [official] `BillingTaxNumber` is an optional parameter (added 2025–26) [official]. | Always send `Years` explicitly. |
| 5.5 | **Premium renew/reactivate**: needs `IsPremiumDomain=true` + the exact `PremiumPrice`, 1 year only, and no promo codes. A wrong or missing price fails (`2515610`, `2515623`, `2015610`). `renew` on an expired domain fails with `2020166`; use `reactivate`. `whoisguard.renew` takes ≤9 years and isn't allowed until 30 days before expiry (`2029331`). [official] | Get the price from `domains.check` first; never guess. |
| 5.6 | **SSL product names changed on 2026-07-11** to SSL.com names (`Standard SSL SSLcom`, `EV SSL SSLcom`, ...). Old names (PositiveSSL, EssentialSSL, ...) are deprecated but **auto-substituted**: the request doesn't fail, and an equivalent SSL.com product is issued and returned. The `ssl.renew` page mixes `SSLType`/`Type`/`CertificateType`. [official, added 2025–26; not in change log] | Send the new names; check the returned type and price before relying on an old-name request. |

## Error codes worth knowing

| Code | Meaning | Source |
|---|---|---|
| 1010101 / 1010102 / 1011102 | ApiUser missing / ApiKey missing (both 1010102 and 1011102 are documented as "APIKey is missing") | official |
| 1011150 | RequestIP invalid (not whitelisted) | official |
| 1017105 | ClientIP disabled or locked | official |
| 1050900 | Unknown error validating ApiUser | official |
| 1017101 / 1017103 / 1017150 | ApiUser / UserName / RequestIP disabled or locked | official |
| 1017411 / 1017410 | Too many login attempts / declined payments | official |
| 3013288 / 4013288 | Too many records (3013288: setHosts, setDefault, setEmailForwarding; 4013288: setHosts only) | official |
| 4022288 | Unable to get nameserver list (setEmailForwarding page prints `4022228`, likely a typo) | official |
| 2011169 | More than 50 domains in `check` | official |
| 2016166 | Domain not associated with your account | official |
| 2019166 | Domain not found | official |
| 2030166 | Edit permission not supported / domain invalid | official |
| 2030288 | Not using proper DNS servers (getHosts/email forwarding on non-Namecheap DNS) | official |
| 2033409 | Order chargeable for Username not found | official |
| 2011170 | PromotionCode validation error | official |
| 2015278 | Invalid `LockAction` | official |
| 2010324–2010327 | Registrant / Tech / Admin / AuxBilling contacts missing (setContacts) | official |
| 2020166 | Domain expired, reactivate instead (renew) | official |
| 2515610 / 2515623 | Premium price wrong / premium-vs-regular mismatch | official |
| 2029331 | Privacy renewal too early (>30 days before expiry) | official |
| 3031510 / 3050900 | Error / unknown error from Enom (Namecheap's upstream registrar platform) | official |
| 5050900 / 5050169 / 5019169 | Unhandled/unknown exceptions (getList is `5050169` on its page, `5019169` in error-codes). Treating them as transient and retrying reads only is our advice | official; advice [ours] |
| 500000 | Rate limited (reported) | 3P ncheap |
| HTTP 405 | Rate limited | NC-SDK, 3P |

## Sources

Reviewed 2026-10-31/11-01. No API calls were made.

- **[official]** Namecheap API docs, `https://www.namecheap.com/support/api/`: the copy in [`markdown/api/`](markdown/api/INDEX.md) (raw HTML in `html/api/`). Older Internet Archive snapshots (2025-07 to 2026-08) were compared to spot pages changed since.
- **[KB]** Namecheap knowledge base: [`markdown/kb/`](markdown/kb/INDEX.md), especially the [API FAQ](https://www.namecheap.com/support/knowledgebase/article.aspx/9739/63/api-faq/) (eligibility, limits, whitelist, sandbox, PremiumDNS/FreeDNS, Punycode, BIND import).
- **[NC-SDK]** [namecheap/go-namecheap-sdk](https://github.com/namecheap/go-namecheap-sdk): README (record helpers, EmailType rules, rate limits 20/min with HTTP 405, non-idempotent charges), `docs/namecheap-api-v2.md` (method reference mirror, 2026-05-28, with date-format notes), CHANGELOG, issues [#49](https://github.com/namecheap/go-namecheap-sdk/issues/49), [#140](https://github.com/namecheap/go-namecheap-sdk/issues/140) (no DNSSEC), [#141](https://github.com/namecheap/go-namecheap-sdk/issues/141) (no auto-renew), [#162](https://github.com/namecheap/go-namecheap-sdk/issues/162) (OX/GMAIL MX rules), [#177](https://github.com/namecheap/go-namecheap-sdk/issues/177)/[#203](https://github.com/namecheap/go-namecheap-sdk/issues/203) (dates), [#193](https://github.com/namecheap/go-namecheap-sdk/issues/193) (write reported as failed).
- **[NC-TF]** [namecheap/terraform-provider-namecheap](https://github.com/namecheap/terraform-provider-namecheap): `docs/resources/domain_records.md` (modes, TTL, email types incl. NONE/GMAIL, lowercase), issues [#355](https://github.com/namecheap/terraform-provider-namecheap/issues/355) (MERGE import deletes), [#361](https://github.com/namecheap/terraform-provider-namecheap/issues/361) (EmailType side effects), [#362](https://github.com/namecheap/terraform-provider-namecheap/issues/362) (rate limit/405), [#377](https://github.com/namecheap/terraform-provider-namecheap/issues/377) (`IsLocked` ≠ transfer lock), [#382](https://github.com/namecheap/terraform-provider-namecheap/issues/382) (MX pref ignored); changelog #262 (parking records).
- **[3P]** Third-party clients:
  - [DNSControl](https://github.com/DNSControl/dnscontrol) Namecheap provider (`providers/namecheap/`, `documentation/provider/namecheap.md`); issues/PRs #2081 (405 detection), #4330 (paging), #4635 (MX pref, CAA flag, single apex NS, TXT rules), #4637, #4645, #5036 (long TXT); a 2017 Namecheap support quote of 20/min, 700/hour, 8,000/day.
  - [willpower232/go-namecheap](https://github.com/willpower232/go-namecheap) `srv.go`: undocumented `domains.dns.getsrvrecords` / `setsrvrecords`.
  - [acme.sh `dns_namecheap.sh`](https://github.com/acmesh-official/acme.sh/blob/master/dnsapi/dns_namecheap.sh): full-zone rewrite, `2030288`, XML entities, no EmailType.
  - [jkindrix/ncheap](https://github.com/jkindrix/ncheap) README: safety model, rate-limit shapes (405/429/500000), `IsLocked`, key scope.
  - [WWW::Namecheap::DNS](https://metacpan.org/pod/WWW::Namecheap::DNS) (Perl): MXE behavior.

### Still unverified (needs a live or sandbox call)

- whether SRV commands work (only in third-party code; DNSControl uses them in production);
- whether the `NONE`/`GMAIL` EmailType values are accepted (listed by Namecheap's own Terraform provider);
- the real per-minute limit (FAQ says 50/min; Namecheap support and Namecheap's own tools say 20/min, and the 21st call has been seen failing).

Corrections welcome: open an issue with the evidence.
