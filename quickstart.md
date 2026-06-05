# Quickstart

## Pay a service in ~5 lines (Node)

```js
import { wrapFetchWithPayment } from "x402-fetch";
import { privateKeyToAccount } from "viem/accounts";

const pay = wrapFetchWithPayment(fetch, privateKeyToAccount(process.env.WALLET_KEY));
const r = await pay("https://mercury-x402-jed.fly.dev/buy/fetch?url=https://example.com");
console.log(await r.json()); // clean text + title + status + a signed provenance receipt
```

`WALLET_KEY` is **your** Base-mainnet wallet, funded with a little USDC. There is no Mercury API key.

## Or drop the MCP server into any agent

```json
{ "mcpServers": { "mercury": { "command": "npx", "args": ["-y", "mercury-x402-mcp"],
  "env": { "MERCURY_PRIVATE_KEY": "0xYOUR_BASE_WALLET" } } } }
```

Your agent now has 17 web-data tools it pays for itself. See [MCP server](mcp.md).

## Look before you pay (free)

`GET /catalog` lists every service, price, and the exact 402 flow — no wallet required.
