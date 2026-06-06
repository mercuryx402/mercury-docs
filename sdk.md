# SDK & CLI

`mercury-x402-sdk` wraps the whole network — **dual-rail** (wallet *or* API key) — with a `mercury` CLI.

```bash
npm i mercury-x402-sdk
```

```js
import { Mercury } from "mercury-x402-sdk";

const m = new Mercury({ apiKey: "mk_test_…" });   // or { privateKey: "0x…" } for the wallet rail
const r = await m.fetch("https://example.com");    // { text, title, status, attestation }
await m.verify(r);                                 // verify the signed receipt — offline, free

await m.markdown("https://example.com");
await m.extract("https://example.com", { title: "string", price: "number" });
await m.buy("sitemap", { url: "https://example.com" });
await m.catalog();                                 // every service + price (free, no rail)
```

## CLI

```bash
npx mercury catalog
export MERCURY_API_KEY=mk_test_…     # or MERCURY_PRIVATE_KEY=0x…
npx mercury fetch https://example.com
```

npm: `mercury-x402-sdk` · source: [github.com/mercuryx402/mercury-x402-sdk](https://github.com/mercuryx402/mercury-x402-sdk)
