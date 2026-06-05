# Service catalog

17 keyless, signed services on Base mainnet. Each is a `GET /buy/<sku>?url=<target>` route; the live,
authoritative list (with prices + JSON schemas) is always at
[`/catalog`](https://mercury-x402-jed.fly.dev/catalog).

| SKU | What you get | ~Price |
|---|---|---|
| `fetch` | clean readable page text + title + status | $0.003 |
| `markdown` | LLM-ready markdown (boilerplate/nav/ads stripped) | $0.005 |
| `extract` | structured JSON record (title, price, author, …) from a page's own metadata | $0.006 |
| `metadata` | the page's JSON-LD / OpenGraph / meta as JSON | $0.006 |
| `links` | the outbound-link graph (crawl frontier) | $0.005 |
| `table` | tables extracted as JSON | $0.006 |
| `feed` | RSS/Atom parsed to JSON | $0.005 |
| `sitemap` | the site's sitemap, expanded | $0.01 |
| `robots` | robots.txt parsed | $0.005 |
| `dns` | DNS records for a domain | $0.006 |
| `headers` | HTTP response headers | $0.005 |
| `redirect` | the full redirect chain | $0.005 |
| `readability` | readability-scored main content | $0.005 |
| `availability` | is a URL up + reachable | $0.005 |
| `validate` | validate a URL/response shape | $0.005 |
| `diff` | diff a page against a prior signed snapshot | $0.006 |
| `notarize` | a signed, timestamped notarization of a URL's content | $0.008 |
| `batch` | many URLs in one job | $0.02 |

Every response includes an `attestation` — see [Provenance receipts](provenance.md).
