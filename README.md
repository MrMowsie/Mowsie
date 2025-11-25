## Mowsie
**A Monetary Fabric for Stateless Bitcoin Velocity**  
*Money Without Memory*

> “…and through the eyelet lay an absurdly small black hole, no larger than a mouse.”

---

## Overview

Mowsie is a **stateless, zero-knowledge monetary fabric** for Bitcoin.  
It enables instant, private BTC-denominated transfers **without** operating a blockchain, ledger, token, or independent consensus system.

Users:

1. Deposit native BTC into a vault on Bitcoin.  
2. Generate zero-knowledge commitments.  
3. Move value inside a minimal, proof-verified fabric (on Solana) where **no transaction history is ever stored**.

Value objects are created and destroyed in microseconds via an *infinite-mint / instant-burn* engine.  
They exist only long enough to complete a state transition. The system retains **only a single evolving state root**, never a transaction graph.

📄 **Whitepapers**  
- [`MonetaryFabricWhitePaper.pdf`](./MonetaryFabricWhitePaper.pdf)  
- [`MetabolicEpocsWhitePaper.pdf`](./MetabolicEpocsWhitePaper.pdf)  
---

## _What “Stateless” Actually Means (Important Clarification)_

In Mowsie, **“stateless” refers to the absence of persistent ledger state**, not national identity.

Mowsie maintains **no**:

- addresses  
- accounts  
- balances  
- transaction history  
- mempool  
- transaction graph  
- lineage  

Inside the fabric:

- **Every value object exists for exactly one transition**  
- **Every commitment is burned immediately after use**  
- **Only the current state root exists**

### Stateful Systems (Bitcoin, Ethereum, Solana):
- Store full transaction history  
- Grow unbounded over time  
- Maintain balances indefinitely  
- Enable transaction-graph analysis  

### Mowsie:
- No addresses  
- No balances  
- No transaction log  
- No historical artifacts  
- No linkable lineage  
- No mempool  
- Only a single, evolving state root

Statelessness allows **pure velocity**, strong privacy, and a radically minimized attack surface.

---

## Design Goals

- **Statelessness by construction**  
  - Only the current state root is stored on-chain.

- **Bitcoin as the settlement anchor**  
  - BTC in a unified vault represents all long-term value.

- **Minimal, auditable surface**  
  - Fixed proving circuit; no scripting VM.

- **No token, no speculative surface**  
  - No inflation schedule.  
  - No market cap.  
  - No wrapped assets.

- **Self-sustaining through crumbs**  
  - A single-satoshi activation/operation mechanism.  
  - Orphaned crumbs power infrastructure (the “Feast of Crumbs”).

---

## High-Level Architecture

### Settlement Layer – Bitcoin
- Native BTC deposited into a consolidated vault.  
- No wrapped or synthetic assets.

### Verification Layer – Solana
- Verifies proofs and stores the live state root.  
- Holds no user balance; runs no application logic.

### Monetary Fabric – Mowsie
- Stateless ZK value layer.  
- Users hold secrets locally.  
- Commitments exist only for microseconds.

---

## Key Concepts

### Infinite-Mint / Instant-Burn Engine

Each value object follows:

1. **Mint** – fresh commitment  
2. **Use** – internal state transition  
3. **Burn** – destroyed instantly  

This eliminates inflation while achieving maximum privacy.

### Stateless Root Evolution

Only the state root persists:
Root(t+1) = Update(Root(t), π)

No lineage.  
No graph.  
No history.

### Economic Model

- No token  
- No market cap  
- No circulating supply  
- No internal “store of value”  
- Crumbs fund computation  
- Expired wallets return crumbs to the protocol

Mowsie cannot inflate because its internal objects cannot persist.

---

## Repository Contents

- `MonetaryFabricWhitePaper.pdf` – Stateless monetary fabric theory  
- `MetabolicEpocsWhitePaper.pdf` – Metabolic epoch governance model  
- `MowsieWhitePaper.pdf` – Full specification, proofs, and threat model  
- `LICENSE` – MIT license  
- `README.md` – This document  

---

## Project Status

Mowsie is in the **research + specification** phase.

Upcoming milestones:

- Finalization of commitment structure  
- Circuit formalization and testing  
- Reference client implementation  
- Testnet deployment  
- Third-party audits  

---

## Contributing

We welcome:

- Issues  
- Design questions  
- Formal review  
- Implementation PRs  
- Independent security analysis  

Please keep discussion focused on protocol design, safety, and engineering.

---

## License

**MIT License**  
See [`LICENSE`](./LICENSE)

