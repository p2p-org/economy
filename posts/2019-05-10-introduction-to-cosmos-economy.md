---
title: "Introduction to Cosmos economy"
description: "This post is about cosmos network economics and roles of key participants!"
date: 2019-04-20
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/lbNkZzZ'
layout: Post
categories:
  - economy
  - cosmos
authors:
  - AlexBond
company:
 - p2p
---

To understand economical structure of Cosmos we should look closely at the key principles of the ecosystem, basic incentives for all different participants and possible influence of these principles on their behavior. Overall network purpose (mission) is *satisfying the needs of ecosystem users by giving them an opportunity to provide their services in a decentralized manner with the ability to interoperate without centralized entities.*   

   Cosmos network consists of application-specific blockchains (Zones) which can be designed differently depending on the utility purpose. All blockchains are interoperable within a single ecosystem connected through intermediary blockchains (hubs) that in fact replace centralized organizations by set of validators. As a separate blockchain each zone can have its own token to govern the private or public network and have its own set of validators but governance can decide that validators of the Cosmos hub will be required to validate additional zones.  
   
   Cosmos ecosystem utilizes Tendermint - practical byzantine fault tolerance (PBFT) consensus mechanism. It means that finalizing blocks depends on 2/3 plus one quorum of all validators agreed on the current state of the network in order to reach the consensus. There are three key groups of participants in Cosmos ecosystem. Each group has its own incentives and impact on the state of ecosystem.
### Validators 

For Cosmos hub there are `100` possible validators, who are responsible for proposing new blocks and validating transactions. This number will rise by `13%` a year until it reaches three hundred maximum possible validators. For other hubs and zones this number is not mandatory and will depend on the particular use case and required level of security. If there are more validators then the right to participate in consensus will have participants with the higher amount of ATOMs bonded.  
  ![Expected growth of validator’s quantity over 10 years](https://imgur.com/8iHMfV8.jpg)  
  Cosmos hub validators has the highest impact on network security and provide intercommunication between zones. They must actively participate in governance and are required to vote on every proposal otherwise their ATOMs are at the risk of being slashed (currently this feature is not active).
  
  > Tell me who are the validators and I will tell you if the network is safe
  
This group have enough knowledge and resources to maintain infrastructure and are interested in generating maximum long-term gains from ATOM inflation and transaction fees (about this later). That is why validators care about healthy and sustainable ecosystem development. They should act in interests of their delegators if they want to keep them loyal and increase the voting power in the long term.  

### Delegators

This group consists of ATOM token holders who have not enough skills or resources to run and maintain the infrastructure but still want to increase the network security and earn a share of the transaction fees and inflationary reward by bonding tokens to the validators. It boosts the voting power of validator and frequency of being chosen as block proposer. In fact, *by bonding ATOM to validator delegators choose one of the pillars of the ecosystem so their choice is very important and affects the level of decentralization.*  
  Delegators are eligible for  transaction fees and inflation reward as well but they have to pay commission, which vary within existing validators. There is no way for validators to steal bonded tokens but there are still other risks related with choosing the validator, which we will discuss later. Decisions based solely on a low commission rate is not always the best decision for delegators.
### Users

If we compare Cosmos network with the market, users are consumers and service providers. Developers, entrepreneurs and buyers who want to utilize the advantages of Cosmos ecosystem. Many different hubs can co-exist. To go further we can compare the network with a nation where there is a national hub with cities and zones each acting as smaller hubs within it and the possibility to join with the secure hub (Cosmos) if needed. Activity of this group measures the overall value of the network and can have a significant impact on demand for the token, transaction fees, workload and so on.
# Cosmos hub economy and reward distribution  

   Cosmos hub economy relies on the inflationary approach. The target annual inflation rate represents the percentage from total supply that is changing each block. If the total bonded stake is less than `66%` of the total ATOM supply, the inflation rate will slightly increase until it reaches a maximum of `20%` or the total bonded stake climbs higher than `66%`. In this case, the annual inflation will decrease to `7%` depending on ATOMs participating in bonding. New tokens incentivize participants to secure the network. The more tokens locked via staking the higher the threshold for initiating a successful attack.

There are two fundamental streams of revenue for Validators
![Reward distribution](https://imgur.com/yreCCgt.jpg)
*   **Block reward**, which distributing amongst all validators proportionally to their voting power. This reward is paid in ATOMs and depends on the current annual inflation rate, which varies each block with the frequency of average block time. In the future, this reward can be split between ATOMs and Photons that will play the role of a secondary token with the purpose of transaction fee payment only, decreasing the velocity and liquidity of ATOMS and making a 1/3 attack more expensive. Inflation of Photons is expected to be fixed and equivalent to `500` tokens per hour. 
   *Currently Photons are not available but could be activated with specific implementation and distribution method by the community via governance.*
*   **Transaction fees** form in each block and proposer gets `1%` or `5%` depending on the number of precommits included. The frequency of proposing blocks is proportional to the voting power of a validator. Before fees distribution, `2%` goes to a reserve pool. These funds can be spent on network development or other activities by voting.  
   Currently transaction fees are close to zero as the network is still in an early stage of adoption. In the future, it will be possible to receive fees in other whitelisted tokens than ATOMs in Cosmos ecosystem. The amount of fees will depend on gas prices and usage of the network.
*   Validator’s **commission rate** represents a percentage from both streams of revenue that delegators pay to a validator. Delegators reward streams are the same as for validators less the commission percentage.
# Penalties  

   In some circumstances occurs slashing of bonded ATOMs. Penalties should increase the responsibility level of participants who are directly involved in decisions associated with network security. Validators have no control over delegator’s stake but if such an event happens both parties lose a percentage of their tokens. This is in order to prevent misbehavior and negligence from validators and bring incentives to delegators to diversify amongst them, perform proper due diligence and choose wisely.

*   The first reason a stake can be slashed is double-signing a block. This means that a malicious node is broadcasting two blocks with different content for the same height. The penalty for that is currently set at `5%` and the validator who is responsible for that drops out of validators set. All ATOMs enter an unbonding (process of undelegating ATOMs from validator) period that lasts for `21 days` and **within this period the stake will not earn provisions and transaction fees.**  
*   If a validator fails to sign more than `95%` blocks in a row of `10000` due to inactivity, `0.01%` of the bonded ATOMs will be lost and the validator will be *jailed for ten minutes without allowance to participate in consensus and be eligible for rewards.*

If slashing happens, it decreases stake and leads to fewer ATOMs paid as a reward.
### Example

Let’s compare three imaginary validators. Assume that delegator bonded equal amount of ATOM to each. Slashing decreases the amount of stake thus meaning a proportional decrease in ATOM provisions since the event has taken place.

For example, *validator 1* `V1` was caught on a double sign and slashing occurred on the 60<sup>th</sup> day. After unbonding, the rest was staked with the same conditions to another one. *Validator 2* `V2` had three liveness slashes on the 30<sup>th</sup> day with a 2-day recovery period and an inability to fix the issue, on the 60<sup>th </sup> and 180<sup>th</sup> days being offline for one day each. *Validator 3* `V3` had no such events in place. 
![Slashing example](https://imgur.com/3fH5DQZ.jpg)
**Overall results show that validator with a higher commission and honest behavior performed better than validators with stated slashing events.** In this example we have not taken compounding into consideration. Every slashing event may decrease the confidence of delegators and may lead to immediate re-delegation to another validator. That will cause fewer commission rewards in ATOM for validator and can lead to inability to maintain secure infrastructure in future.

# Recommendations for delegators  

   Every delegator is self-responsible for the financial decisions made. To choose the proper validator and understand misbehavior risks it is important to read the full conditions of the delegator agreement and find out the validator’s policy on this topic.

*   **Security audit** that proves the stated level of security that should decrease the probability of a key compromise that may lead to double-sign.
*   Check for an **available roadmap** of future steps to increase the security or transparency of annual expenses on upgrades and improvements.
*   **Skin in the game** proves that the validator puts their own funds at risk as well. The higher the percentage of their stake the more responsible the validator should be and if slashing does occur he will lose his own ATOMs and .
*   **Compensation policy.** Are there any payouts or bonuses from the validator’s side in case of a slashing event?
*   **Diversification amongst 3-7 validators** who operate in different countries and utilize different hardware. It sounds like a good idea, as it decreases amount of stake in case of slashing, increases overall network security and brings voting power diversification as well.

Do not forget to **re-delegate your ATOM rewards** in order to maximize profits and take advantage of the compounding.
---
**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake ATOMs with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:** [https://t.me/p2pvalidator](https://t.me/p2pvalidator)
