# Mowsie

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

Value objects are created and destroyed in microseconds via an *infinite-mint / instant-burn* engine. They exist only long enough to complete a state transition. The system retains **only a single evolving state root**, never a transaction graph.

📄 **Whitepaper:** [MowsieWhitePaper.pdf](./MowsieWhitePaper.pdf)

---

## **_What “Stateless” Actually Means (Important Clarification)_**

**_In Mowsie, “stateless” does **not** refer to sovereign states or national identity.  
It means the protocol maintains **no persistent ledger state whatsoever**—no balances, no accounts, no transaction history, and no lineage of value objects._**

**_Every value object exists only for a single transition and is burned immediately afterward._**

- **Stateful systems** (Bitcoin, Ethereum, Solana):  
  - Record every transaction forever  
  - Accumulate history  
  - Maintain long-lived account balances  
  - Grow in size over time  

- **Mowsie:**  
  - **No addresses, no balances, no transaction log**  
  - **Only the current state root exists**  
  - **No transaction graph to analyze or attack**  
  - **Value is anchored on Bitcoin; motion happens in a memoryless ZK fabric**

**_Statelessness is the core innovation: money exists only in the present state, enabling pure velocity, strong privacy, and a radically minimized attack surface._**

---

## Design Goals

- **Statelessness by construction**  
  - No addresses, no balances, no transaction log, no lineage.  
  - Only the current state root is stored on-chain.

- **Bitcoin as the store of value**  
  - BTC in a unified vault represents all long-term value.  
  - Mowsie is a *velocity layer*, not a competing asset or chain.

- **Minimal, auditable surface**  
  - Fixed proving circuit; no scripting VM.  
  - Small attack surface that can be formally analyzed.

- **No token, no market cap, no TVL games**  
  - The protocol has **no native token**, no inflation schedule, and no speculative surface.  
  - The only meaningful quantity is BTC in the vault at any given moment.

- **Self-sustaining via crumbs**  
  - A single satoshi fee (“crumb”) on deposits, withdrawals, internal sends, and wallet renewals.  
  - Orphaned crumbs accumulate to fund infrastructure, maintenance, and public goods (the “Feast of Crumbs”).

---

## High-Level Architecture

**Settlement Layer – Bitcoin**

- Native BTC deposited into a consolidated on-chain UTXO pool.  
- Bitcoin provides consensus, immutability, and long-term value storage.  
- No wrapped tokens or synthetic BTC.

**Verification Layer – Solana**

- Verifies zero-knowledge proofs and maintains the live state root.  
- Does **not** hold user funds or execute arbitrary application logic.  
- Functions purely as a high-throughput proof verifier.

**Monetary Fabric – Mowsie**

- Stateless ZK value layer.  
- Users hold secrets locally; the fabric knows only commitments.  
- Infinite-mint / instant-burn engine ensures:
  - Conservation of value (∑B_old = ∑B_new).  
  - No structural link between old and new commitments.  

---

## Key Concepts

### Infinite-Mint / Instant-Burn Engine

Each value object inside the fabric follows a three-step lifecycle:

1. **Mint** – created as a fresh commitment.  
2. **Use** – consumed as input to a state transition.  
3. **Burn** – destroyed immediately as the new commitment is created.

Nothing persists beyond the current step. This eliminates inflation while collapsing money down to its purest form: a **momentary carrier of value** that exists only long enough to move.

### Stateless Root Evolution

Instead of storing a history of objects, Mowsie maintains only a single state root:

\[
\text{Root}_{t+1} = \text{Update}(\text{Root}_t, \pi)
\]

Where:

- *t* is the current state-transition index.  
- *π* is the zero-knowledge proof attesting to the correctness of the transition.

No intermediate commitments persist; only the evolving root is retained.

### Economic Model

- No token, no market cap, no circulating supply.  
- Fees are charged in single-sat “crumbs”.  
- Expired wallets’ crumbs revert to the protocol and are swept into a DAO-controlled Mowsie wallet via the **Feast of Crumbs** mechanism.  
- Inflation is impossible at the fabric level because value cannot be stored there beyond a microsecond.

---

## Repository Contents

- `MowsieWhitePaper.pdf` – Formal specification and threat model.  
- `LICENSE` – MIT license granting broad use, modification, and distribution rights.  
- `README.md` – Project overview (this document).

Implementation code, reference clients, and SDKs will be added in future revisions of the project.

---

## Project Status

Mowsie is currently in the **research and specification** phase.

Planned next steps:

- Formalization of the proving circuits and commitment scheme.  
- Reference implementation of the vault logic and verifier contracts.  
- Testnet deployment and third-party security review.  

---

## Contributing

Feedback, critique, and formal review are highly encouraged.

If you’d like to contribute:

- Open an **Issue** for discussion, security considerations, or design questions.  
- Submit **Pull Requests** for documentation improvements, formalizations, or prototype implementations.  
- Share independent analyses or audits referencing this repository.

Please keep discussion focused on protocol design, security, and real-world deployment considerations.

---

## License

This project is licensed under the **MIT License**.  
See [`LICENSE`](./LICENSE) for details.
