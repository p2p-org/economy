---
 title: "P2P Validator helps to carry out development of Random Beacon for Cosmos"
description: "Publicly verifiable Random Beacon will become a foundation for gaming applications within Cosmos ecosystem"
date: 2020-04-27
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/gOCed9u.jpg'
layout: Post
category:
  - cosmos
authors:
  - AlexBond
company:
 - p2p
---

P2P Validator’s team successfully carried out the development of BLS-based Random Beacon to provide Cosmos application-specific blockchains with an unbiased source of entropy. The code is[ open-sourced](https://github.com/corestario/tendermint) and available for further exploration by the community. This implementation of Random Beacon opens new possibilities for projects that require truly unpredictable randomness in their decentralized products.

**Our team will continue to develop features that can bring more users and add more value to the Cosmos ecosystem**. If you want to support our initiatives the best way is to[ stake ATOM with us](https://p2p.org/cosmos).

### High level overview

Random Beacon is a cryptographic primitive that periodically outputs random numbers which are publicly available and verifiable by any party. Random Beacon requires several important properties:

- Availability (or liveness) — an adversary cannot prevent a random number generation process.
- Unpredictability — an adversary cannot predict the protocol outcome (a random value).
- Bias-resistance — an adversary cannot influence future values to their advantage.
- Public-Verifiability — anyone can verify the protocol’s outcome.

In a decentralized environment the ability to generate provably random outputs is critical to protect applications from manipulations and get rid of centralized random number sources. It can also be helpful for data protection as random numbers are used in the generation of cryptographic keys, establishing connections, internal sequences and so on. 

*Randomness can be useful for numerous blockchain applications:*

- gaming, gambling and lotteries (e.g. PoolTogether)
- cryptographic sortition in consensus for leader or quorum selection (e.g. DFINITY, Elrond, ThunderCore, Cardano)
- cryptographic sortition for financial applications (e.g. tBTC-like collateralized bridges)
- elections, sociology and statistics
- advanced cryptography, mixnets and other protocols that require randomness to provide privacy or security 

Implementation of Tendermint with BLS-based random beacon - Arcade, provides each block with a random number that can be safely used during block processing without changing original Tendermint security assumptions.

### BLS-based Random Beacon in Tendermint

We wanted our in-built pseudo random number generator (PRNG) to be suitable for applications like games and gambling: that means fast and unbiasable (many random beacons used for consensus are slightly biasable, what's fine for cryptographic sortition but is not suitable for a game like blackjack). Preferably it should be available at every block.

1. Unbiasable
2. Small rounds (a few seconds at most)
3. Publicly verifiable
4. Small receipt (under 10kb)
5. Decentralizible
6. Safety and liveness similar to original Tendermint
7. Sybil resistant
8. Censorship resistant

The most suitable random beacon to satisfy constraints is a BLS Threshold Signature-Based Beacon, proposed by the DFinity team. To build it we expanded a pre-commit step in the Tendermint consensus.

![RBT](https://imgur.com/kkYo5H6.jpg)

The idea works by expanding a pre-commit step of Tendermint consensus: **validators send not only pre-commit but also add partial BLS threshold signatures**. This allows every new block to come out with a freshly generated random number.

The outlined PRNG is available at every block and suitable for building randomness-dependent applications within the Cosmos ecosystem. We also built a Cosmos SDK adaptation that can interact with the random number in the block, and a reseeding module that is capable of bringing external randomness to deterministic BLS-based PRNG.

BLS threshold signatures need a key generation step. We implemented an off-chain distributed key generation based on Pederson distributed key generation (DKG), and an on-chain fallback that provides the ability to both attest and slash in cases when off-chain DKG fails.

### About P2P Validator

[P2P Validator](https://p2p.org) is a world-leading non-custodial staking provider with the best industry practices and proven expertise. We provide comprehensive due-diligence of digital assets and offer only top-notch staking opportunities securing more than 40 million of USD value. At the time of publishing, P2P Validator is trusted by over 1000 delegators across 15+ networks.

------

*Want to stake with us? Alexey will be happy to help. Contact am@p2p.org to get personal assistance.*

---

**P2P Validator** provides secure non-custodial staking. Subscribe to our channels and stay tuned for updates and new blog posts.

**Stake ATOM with us:** [https://p2p.org/cosmos](https://p2p.org/cosmos)

**Web:** [https://p2p.org](https://p2p.org)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram chat:** [https://t.me/P2Pstaking](https://t.me/P2Pstaking)

**Telegram announcement:** [https://t.me/p2porg](https://t.me/p2porg)