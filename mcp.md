# MCP server

`mercury-x402-mcp` exposes Mercury's services as tools in any MCP host (Claude Desktop, Cursor, Cline,
or your own agent). Each paid tool pays its SKU over x402 with your wallet and returns the result plus
a signed receipt. Built live from `/catalog`, so the tool list is always current.

## Install

```json
{ "mcpServers": { "mercury": { "command": "npx", "args": ["-y", "mercury-x402-mcp"],
  "env": { "MERCURY_PRIVATE_KEY": "0xYOUR_BASE_MAINNET_WALLET" } } } }
```

`MERCURY_PRIVATE_KEY` is your Base-mainnet wallet (funded with a little USDC). The `mercury_catalog`
and `mercury_verify` tools work **without** a wallet (free).

* npm: [`mercury-x402-mcp`](https://www.npmjs.com/package/mercury-x402-mcp)
* source: [github.com/0xjed/mercury-x402-mcp](https://github.com/0xjed/mercury-x402-mcp)
