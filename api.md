# API reference

Base URL: `https://mercury-x402-jed.fly.dev`

## Free (no wallet)
| Route | Returns |
|---|---|
| `GET /catalog` | every SKU, price, network, and the 402 flow as JSON |
| `GET /llms.txt` | the agent-facing guide (llmstxt.org) |
| `GET /openapi.json` | OpenAPI 3.1 description |
| `GET /.well-known/x402` | the x402 discovery record |
| `GET /.well-known/mercury-attestation` | the provenance signer key |
| `GET /vs` | machine-readable competitor teardown |
| `POST /x402/verify` | verify a signed receipt offline |

## Paid (x402)
`GET /buy/<sku>?url=<target>` — see [Service catalog](catalog.md). Returns `402` until paid, then the
result + `attestation`. Optional params per SKU (e.g. `?format=markdown`, `?links=1`, `?extract=title,price`).
