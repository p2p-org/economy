---
title: "Confusion with calculation of available staking capacity in Tezos. Who is right?"
description: "The purpose of this post is to shed some light on calculation of baker's free space"
date: 2019-11-12
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/jeNGYqU.jpg'
layout: Post
category:
  - tezos
authors:
  - AlexBond
company:
 - p2p
---

Tezos ecosystem includes solid tools to monitor network performance and staking rewards. Block explorers represent a major part of the ecosystem transparency and health. Delegators and bakers often rely on such tools before making decisions such as, should I add to my self-bond or which baker to stake with. Diversity of these services provide users with unique experience and allow them to choose one that corresponds to a particular need.

Analytical explorers display two types of parameters. The first is derived right from the blockchain data and in most cases they are identical on different analytical tools. Values of these parameters can be slightly different on various explorers because of the network data update frequency. The second type of parameters is calculated using network variables and blockchain data.

It may lead to a confusion when the same variable has different values on multiple resources. It can be because of different approaches taken for calculation or using different timeframes. Currently, *available staking capacity* has different values for the same bakers on various analytical websites. It represents an amount of XTZ that can be staked with a particular baker without making him over-delegated. Delegated tokens above the limit will not contribute to the power of the baker.

### Example

Stats for P2P Validator on various analytical tools for 19.03.2020:

*Tzstats.io*: staking capacity = 14 048 492 XTZ resulting in available staking capacity = **1 971 806 XTZ**.

*MyTezosBaker*: available staking capacity = **802 752 XTZ**| staking capacity = 12 881 681 XTZ.

*Tezos Nodes*: available staking capacity = **2 007 769 XTZ** resulting in staking capacity = 14 079 769 XTZ.

*Baking Bad:* available staking capacity = **1 972 000 XTZ** resulting in staking capacity = 14 044 000 XTZ.

In some cases, the difference between the values above is significant and cannot be explained by fluctuations of baking rights and endorsements. Who is right? 

The purpose of this post is to establish a single approach for available staking capacity calculation and eliminate errors and confusion for end users on various analytical resources. Below I share my understanding of the correct approach to calculate this parameter and invite everyone in Tezos community to join the discussion, express your point of view or suggest other ways of thinking about this parameter.

# Security deposit

In order to create blocks baker should maintain a specific amount of self-bond that is used for security deposit required by the Tezos protocol and subjected to slashing as a measure against misbehavior. Security deposit per created block is equal to 512 XTZ and per endorsement is equal to 64 XTZ. When validator bakes block or endorses, these funds become frozen for a number of preserved cycles defined by the protocol and unfreeze at their end.

If we assume that 100% of total supply participate in staking we can calculate the minimum bond requirement for a baker: `((block_security_depo + endorsement_security_depo * endorsers_per_block) * blocks_per_cycle * (preserved_cycles+1)) / total_supply`

Let's split this formula into parts:

Part 1: `block_security_depo + endorsement_security_depo * endorsers_per_block`

In this part we calculate the total amount of security deposit per block.

Part 2: `blocks_per_cycle * (preserved_cycles+1)`

By multiplying the total security deposit per block by the number of blocks in the cycle and frozen period plus one we get the total amount of XTZ that are frozen for preserved cycles.

Part 3: `Part 1 * Part 2 / total_supply`

Here we finally calculate the security deposit share of the total supply.

Let's crunch some numbers:

`block_security_depo = 512 XTZ`

`endorsement_security_depo = 64 XTZ`

`endorsers_per_block = 32`

`blocks_per_cycle = 4096`

`preserved_cycles = 5`

All these parameters are derived from a Tezos protocol and represent constant values until community decides to propose changes via governance procedure. The only dynamic parameter is `total_supply` which is equal *~ 829,34 million XTZ* (19.03.2020). 

The actual self-bond requirement is floating as baking frequency and endorsement rights are changing but for this case we will not take possible baking deviations into consideration.

The whole calculation of minimum self-bond requirement *if 100% tokens at stake* look like: `((512 + 64 * 32) * 4096 * (5+1)) / 829 340 996 = 7,59%`.

With a decrease of total supply percentage at stake, minimum self-bond requirement will increase as overall share of frozen XTZ in a security deposit related to the participating tokens will be higher.

To calculate the exact self-bond requirement we can simply put the exact number of tokens at stake instead of `total_supply` or divide the result of previous calculation, made for 100% staked tokens, by the actual percentage of staked XTZ. It will result in **~9,64%** of *actual self-bond requirement* for a baker.

The only caveat here is that `total_supply` is growing over time while security deposits remain the same. In the long run it will result in lower self-bond requirement as well as the network security.

# Available staking capacity

After finding the exact self-bond requirement we can answer two questions:

1) Does a particular baker maintain sufficient self-bond?

2) How many XTZ a particular baker can accept before it becomes over-delegated?

To answer the first question we should find a self-bond share in the total staking balance.

`staking_balance = self_bond + delegated_balance`

`self_bond / staking_balance * 100 = X%`.

If `X > actual_self_bond_req` then baker has enough self-bond and won't miss baking or endorsement slots.

The answer to the second question is available staking capacity. To find this value we should substract staking balance from the maximum balance.

`max_balance = self_bond / actual_self_bond_req`

`available_staking_capacity = max_balance - staking_balance`

To make calculation of available capacity even more precise you can adjust `self_bond` by `frozen_fees` + `frozen_rewards` as they do not take part in security deposits and use actual rolls of a baker to get the actual `staking_balance`. 

Using formulas from above we get `available staking capacity of P2P Validator ~ 1 997 663 XTZ`

Seems like [Baking Bad](https://baking-bad.org/), [Tzstats](https://tzstats.com/tz1P2Po7YM526ughEsRbY4oR9zaUPDZjxFrb) and [Tezos Nodes](https://www.tezos-nodes.com/) are quite aligned with the value and use similar approach for calculation of a baker free space.

Now you have all the necessary information to check by yourself if the self-bond is sufficient enough to bake and what is the available staking capacity of a baker. In addition, we have created a [ spreadsheet with prepared calculations](https://docs.google.com/spreadsheets/d/1ZxRBHETPixxeYAG0efJbXsKeiIHPq1nGWJ2ZazND2a8/edit#gid=1765745933) for simplicity. We also improved calculation for self-bond and staking balance of a baker to make available capacity value even more precise.

------

*Special thanks to Baking Bad and StakeNow for paying attention to the article and facilitating valuable discussions.*

------
**P2P Validator** provides secure non-custodial staking. Subscribe to our channels and stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake XTZ with us:** [p2p.org/tezos](p2p.org/tezos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)