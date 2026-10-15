# RailFi MCP

Free, non-custodial MCP server for agent-safe stablecoin payout plans.

RailFi helps teams (and agents) turn invoice/payout rows into a **bounded payout-run draft** the owner approves once in their own wallet. Tools validate plans and reconcile transfers; they **never hold funds or keys** and **do not execute payments**.

## Endpoints

| What | URL |
|------|-----|
| MCP (streamable HTTP, JSON-RPC, protocol `2025-06-18`) | https://railfi.xyz/api/mcp |
| A2A agent card | https://railfi.xyz/.well-known/agent-card.json |
| Web app (plans) | https://railfi.xyz/plans?src=site |
| Early-bird beta | https://railfi.xyz/beta?src=site |

## Tools

| Tool | Use when |
|------|----------|
| `create_payout_plan` | You need to validate recipients, amounts, total budget and time window, then export an approve-once pack for the owner's wallet |
| `validate_payout_plan` | You want to check a plan without creating an export |
| `fetch_transfers` | Read-only public USDC/USDT Transfer lookup (Polygon, Base, Ethereum, Arbitrum) |
| `reconcile_payouts` | Transfers landed and you need to mark lines paid (tx hash) or skipped and report progress |

## Install / connect (remote)

```json
{ "mcpServers": { "railfi": { "type": "streamable-http", "url": "https://railfi.xyz/api/mcp" } } }
```

No API key. No OAuth. Rate limit: 60 requests/min/IP.

## Honesty

- Non-custodial: you sign in your own wallet; RailFi never holds private keys or balances.
- A2A `message/send` is **not** implemented.
- Software only — not a money transmitter, bank, or custodian.

## Contact

[info@railfi.xyz](mailto:info@railfi.xyz) · https://railfi.xyz
