# Provenance receipts

Every paid result ships an `attestation` — an **EIP-191 signed provenance receipt** over
`sha256(text) + url + status + time`. It proves the bytes you received are genuine and untampered, and
it's verifiable **offline, by anyone**, forever — the signer key is pinned at
[`/.well-known/mercury-attestation`](https://mercury-x402-jed.fly.dev/.well-known/mercury-attestation).

This is the non-commodity edge: a free scraper gives you bytes, but no proof of *what / where / when*.
For RAG, trading, and agent-to-agent commerce, that proof is the difference between data and evidence.

Verify a receipt: `POST /x402/verify` with the result + its attestation, or ecrecover the EIP-191
message yourself (the receipt embeds the exact signed `message` + a one-line `howTo`).
