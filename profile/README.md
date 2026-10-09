# StellarYard

Local development tooling for the Stellar and Soroban ecosystem.

StellarYard is an open-source project, independent of and not affiliated with the Stellar Development Foundation. It provides a visual, click-instead-of-CLI environment manager for developers building on Stellar — spin up a local Horizon and Soroban RPC network, fund test accounts, deploy and invoke Soroban smart contracts, and inspect ledger state, without memorizing CLI flags or juggling multiple terminal windows.

## Why

Testing a Soroban contract locally today means coordinating several separate tools — Docker, Horizon, the Soroban RPC, and the Stellar CLI — before you can run a single `invoke`. StellarYard collapses that into one backend with a real API, and clients (web dashboard, terminal CLI) built on top of it, so the friction of local setup stops being the first thing a new Soroban developer has to fight through.

## Repositories

| Repo | What it is |
|---|---|
| [`stellaryard-core`](https://github.com/stellaryard/stellaryard-core) | The orchestration engine and API server — controls local Horizon/Soroban RPC containers, accounts, contract deployment. No UI; the foundation the other two consume. |
| [`stellaryard-dashboard`](https://github.com/stellaryard/stellaryard-dashboard) | Web dashboard for StellarYard — visual container control, account management, ledger viewer, contract deploy/invoke UI. |
| [`stellaryard-cli`](https://github.com/stellaryard/stellaryard-cli) | Scriptable terminal client for StellarYard — same capabilities as the dashboard, built for CI and terminal-first workflows. |

All three share one API contract, defined in `stellaryard-core`. See each repo's `PRD.md` and `ARCHITECTURE.md` for what it does and how it's built.

## Status

Early-stage. Local/testnet-only in this phase — no support for mainnet accounts or real-value transactions yet. Architecture is designed with that as a future direction, not an afterthought, but it isn't here yet. Don't point this at funds you care about.

## Contributing

Issues are labeled by scope in each repo. To contribute, check the issue tracker in the relevant repo — `stellaryard-core` for backend/API work, `stellaryard-dashboard` for frontend, `stellaryard-cli` for CLI commands. Each repo's `ARCHITECTURE_ESSENTIALS.md` is meant to be a fast reference before you start, not the full doc.

Licensed under Apache 2.0.
