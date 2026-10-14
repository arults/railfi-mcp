# RailFi MCP

Non-custodial, free MCP server for agent-safe stablecoin payout plans.

- Endpoint (streamable HTTP, JSON-RPC, protocol 2025-06-18): https://railfi.xyz/api/mcp
- A2A card: https://railfi.xyz/.well-known/agent-card.json
- Web app: https://railfi.xyz/plans

## Tools
- `create_payout_plan` – validate recipients, budget and time window; returns an approve-once pack the owner approves in their own wallet.
- `validate_payout_plan` – check a plan without creating an export.
- `reconcile_payouts` – mark lines paid (tx hash) / skipped and report progress.

RailFi never holds funds or keys and does not execute payments. A2A message/send is not implemented. Rate limit: 60 req/min/IP.
