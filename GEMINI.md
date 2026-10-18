# Dexra

Dexra checks Solana tokens, launches, wallets, pools, perp markets and swaps. Use it before the user buys, sells, provides liquidity or trusts an address on Solana.

- Start with `describe_address` (free) for any address you do not recognise. It says what the address is and which tool to call next.
- Then use the matching check: `token_deep_check` or `token_holders_delta` for a token, `new_launches` or `new_launches_batch` for fresh launches, `wallet_check` for a wallet, `pool_health` or `clmm_range_stats` for liquidity, `market_snapshot` for perps, `swap_preflight` before a swap.
- Every check returns a `verdict`, the `reasons` behind it (worst first), a `summary` and the evidence:
  - `avoid`: one finding is enough to stay away. Tell the user plainly.
  - `caution`: something needs a look. Show the reasons.
  - `unknown`: nothing stands out, but the data to judge is missing. Do not present it as safe.
  - `ok`: nothing found; the reason says what was checked.
- Quote the `summary` and the main reasons rather than inventing your own judgement. Dexra is not financial advice.
- Free tools: `describe_address`, `service_stats`, `score_performance`. Paid tools cost 0.005–0.03 USDC per call.
- If a paid tool answers with `isError` and an x402 payment request, the user has no API key or has used up their plan. Tell them they can add a key (`gemini extensions config dexra`) from https://dexra.dev/app/keys, or pay per call over x402. Do not retry in a loop.
- If a result carries `retry-after`, wait that long before calling again.
