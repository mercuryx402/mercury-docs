# Developer portal & API keys

Mercury has **two payment rails** — pick whichever fits how your agent is built. Both hit the *same*
`/buy/*` endpoints and return the *same* signed provenance receipts.

| You bring | Rail | Best for |
|---|---|---|
| a **Base wallet + USDC** | keyless **x402** | crypto-native agents that already hold a wallet |
| a **Mercury API key** | the **API-key rail** | everyone else — no wallet, no crypto |

## Get a free key (no wallet)

→ **[mercury-x402-jed.fly.dev/developers](https://mercury-x402-jed.fly.dev/developers)** — one click, no signup.

You get a `mk_test_…` sandbox key with a free quota to evaluate the whole API. Use it as a bearer token:

```bash
curl -H "Authorization: Bearer mk_test_YOUR_KEY" \
  "https://mercury-x402-jed.fly.dev/buy/fetch?url=https://example.com"
```

Production keys (`mk_live_…`) bill against prepaid credits — card top-up is rolling out.

## Or pay keyless with a wallet

No key needed — your agent signs an x402 payment per call. See [Paying over x402](x402.md).
