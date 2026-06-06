# Quickstart

Pick a rail — a **free API key** or a **wallet** — then call any `/buy/*` route. Same data, same signed receipts.

## A) Free API key (no wallet) — fastest

Grab a key at **[/developers](https://mercury-x402-jed.fly.dev/developers)** (one click), then:

```bash
curl -H "Authorization: Bearer mk_test_YOUR_KEY" \
  "https://mercury-x402-jed.fly.dev/buy/fetch?url=https://example.com"
```

Or with the SDK:

```js
import { Mercury } from "mercury-x402-sdk";
const m = new Mercury({ apiKey: "mk_test_…" });
console.log(await m.fetch("https://example.com")); // clean text + a signed receipt
```

## B) Keyless with a wallet (x402)

```js
import { wrapFetchWithPayment } from "x402-fetch";
import { privateKeyToAccount } from "viem/accounts";
const pay = wrapFetchWithPayment(fetch, privateKeyToAccount(process.env.WALLET_KEY));
const r = await pay("https://mercury-x402-jed.fly.dev/buy/fetch?url=https://example.com");
console.log(await r.json());
```

## C) MCP (Claude Desktop / Cursor / Cline)

```json
{ "mcpServers": { "mercury": { "command": "npx", "args": ["-y", "mercury-x402-mcp"],
  "env": { "MERCURY_PRIVATE_KEY": "0xYOUR_BASE_WALLET" } } } }
```

## Look before you pay (free)

`GET /catalog` — every service, price, and the 402 flow. No wallet, no key.
