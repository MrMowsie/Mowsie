#Mowsie

A Monetary Fabric for Stateless Bitcoin Velocity
Money Without Memory

“…and through the eyelet lay an absurdly small black hole, no larger than a mouse.”

Overview

Mowsie is a stateless, zero-knowledge monetary fabric for Bitcoin.
It enables instant, private BTC-denominated transfers without operating a blockchain, ledger, token, or independent consensus system.

Users:

Deposit native BTC into a vault on Bitcoin.

Generate zero-knowledge commitments.

Move value inside a minimal, proof-verified fabric (on Solana) where no transaction history is ever stored.

Value objects are created and destroyed in microseconds via an infinite-mint / instant-burn engine. They exist only long enough to complete a state transition. The system retains one evolving state root, never a transaction graph.

📄 Whitepapers

Stateless Monetary Fabric Whitepaper – MonetaryFabricWhitePaper.pdf

Metabolic Epochs Whitepaper – MetabolicEpocsWhitePaper.pdf

What “Stateless” Actually Means

“Stateless” does not refer to nationality or sovereign statehood.
It means the protocol maintains:

no balances

no addresses

no transaction history

no lineage of value objects

Every value object exists for one transition and is burned immediately afterward.

Stateful Systems (Bitcoin, Ethereum, Solana)

Retain every transaction forever

Accumulate history

Maintain balances

Grow in size indefinitely

Mowsie

No transaction log

No account balances

No address graph

Only one state root

Pure velocity, zero persistence

This is the first monetary system designed where money has a lifespan measured in microseconds—existing only at the moment of transfer.

Design Goals

Radical statelessness
Only the current state root exists; nothing else is stored.

Bitcoin as the store of value
Mowsie is a velocity layer, not a competing chain or asset.

Minimal attack surface
A fixed circuit and no scripting VM drastically reduce complexity.

No token, no governance, no speculation
The protocol has no native asset and cannot inflate.

Self-funded via crumbs
A single satoshi (“crumb”) fuels internal computation and wallet activation.
Orphaned crumbs accumulate to sustain infrastructure — the Feast of Crumbs.

High-Level Architecture
Bitcoin — Settlement Layer

Native BTC held in a consolidated UTXO vault

No wrapped tokens

Bitcoin provides long-term security and immutability

Solana — Verification Layer

Verifies zero-knowledge proofs

Maintains the evolving state root

Holds no funds and executes no arbitrary logic

Mowsie — Monetary Fabric

Stateless ZK value domain

Users hold secrets locally

Infinite-mint / instant-burn lifecycle ensures:

strict conservation of value

no stored history

no persistent commitments

Key Concepts
Infinite-Mint / Instant-Burn Engine

Inside the fabric, every value object is:

Minted

Used

Burned

It exists only long enough to move value forward.
This prevents inflation while producing a form of “momentary money” that cannot persist or accumulate.

Stateless Root Evolution

Instead of storing old data, Mowsie updates a single state root:

Root
𝑡
+
1
=
Update
(
Root
𝑡
,
𝜋
)
Root
t+1
	​

=Update(Root
t
	​

,π)

No history exists between transitions — only a proof that the new state is valid.

Economic Model: Crumbs & Blink Credits

No token

No circulating supply

No governance

Internal actions require burning crumbs (single sats)

Crumbs convert into blink credits, which represent internal computation

Expired wallets’ crumbs feed into the Feast of Crumbs, sustaining the protocol

Repository Contents

MonetaryFabricWhitePaper.pdf
Formal definition of the stateless monetary fabric and the infinite-mint / instant-burn engine.

MetabolicEpocsWhitePaper.pdf
The metabolic, living-wallet epoch system that powers the blink economy and adaptive difficulty.

MowsieWhitePaper.pdf
Original combined whitepaper draft.

LICENSE — MIT License

README.md — This document

Future additions will include:

Reference circuits

Vault implementation

Verifier contract

Developer SDKs

Testnet clients

Project Status

Mowsie is in the active R&D phase.

Next Steps

Formalizing proving circuits

Building a reference client

Implementing vault + verifier logic

Launching a testnet

Third-party audits

Public circuit verification

Contributing

Contributions are welcome.

You can:

Open issues for discussion or analysis

Submit PRs for documentation, formalization, or implementation

Propose improvements to the stateless fabric model or metabolic epoch system

Share independent research, security analyses, or simulations

Please keep contributions focused and technical.

License

Mowsie is released under the MIT License.
See LICENSE
 for details.
