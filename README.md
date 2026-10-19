# Dexra for Gemini CLI

Adds [Dexra](https://dexra.dev?utm_source=github&utm_medium=referral&utm_campaign=catalog&utm_content=gemini-cli-extension) to Gemini CLI: Solana DeFi checks for AI agents. Before your agent buys, sells or provides liquidity, it can check a token launch, a token's real holders, a wallet, a pool, a perp market or a planned swap. Each check returns a verdict (`ok`, `caution`, `avoid` or `unknown`) with the reasons and the evidence.

## Install

```sh
gemini extensions install https://github.com/dexra-dev/gemini-cli-extension
```

Gemini CLI asks for an optional API key during install. Change it later with:

```sh
gemini extensions config dexra
```

Without a key the free tools (`describe_address`, `service_stats`, `score_performance`) work and paid tools are paid per call in USDC over [x402](https://x402.org). With a key, paid tools are included up to your plan's daily credits: 100 a day on a free account with a confirmed email, more on Pro, Scale and Business. Create a key at [dexra.dev/app/keys](https://dexra.dev/app/keys?utm_source=github&utm_medium=referral&utm_campaign=catalog&utm_content=gemini-cli-extension).

## What it adds

- The remote MCP server `https://api.dexra.dev/mcp` (Streamable HTTP).
- `GEMINI.md`, which tells the model when to call Dexra and how to read its verdicts.

## Tools

| Tool | Price (USDC) |
|---|---|
| `describe_address`, `service_stats`, `score_performance` | free |
| `new_launches`, `swap_preflight` | 0.005 |
| `market_snapshot` | 0.01 |
| `new_launches_batch` | 0.015 |
| `clmm_range_stats` | 0.02 |
| `token_deep_check`, `token_holders_delta`, `wallet_check`, `pool_health` | 0.03 |

Details: [dexra.dev/docs](https://dexra.dev/docs?utm_source=github&utm_medium=referral&utm_campaign=catalog&utm_content=gemini-cli-extension). Configs for other MCP clients: [dexra-dev/mcp](https://github.com/dexra-dev/mcp).

## License

MIT
