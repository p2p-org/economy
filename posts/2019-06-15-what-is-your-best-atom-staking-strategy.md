---
title: "What is your best atom staking strategy?"
description: "This post about various staking models for cosmos hub delegators"
date: 2019-06-15
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/C4J62dg.jpg'
layout: Post
category:
  - economy
  - cosmos
authors:
  - AlexBond
company:
 - p2p
---

Previously [we discussed](https://economy.p2p.org/5-reasons-to-stake-your-atoms) why staking is important for the ecosystem and how people interested in the network potential can benefit increasing their overall share without suffering from inflation implications. In this short blog post I want to cover some strategies which participants could utilize with their outcomes and possible risks.

There are three key options for stakers in existing conditions:
* Stake and forget
* Stake and use the power of compounding in order to increase a total share of the network
* Stake and save the current network share while withdrawing gains diluted by inflation from other participants who do not stake.

In fact each of these options could be supplemented with the idea of diversification amongst various validators to decrease [slashing risk](https://economy.p2p.org/slashing-overview-in-cosmos-network).

For simplicity let’s assume that we have two delegators, the first is staking the second one is not. Initial total supply is `100 atoms` inflation is `7%`, staking ratio is equal to the target value of `67%` and considered period of observation is `5 years`. 

# 1) Stake and forget

This strategy may look convenient at a first glance but such behavior has many disadvantages. Inactive delegator can miss the moment when a node of a validator he bonded to goes offline for a long period resulting in slashing of a stake. Community may decide to change initial network parameters via governance. It may influence overall staking performance and an inactive delegator can miss that. In this case, accumulated rewards do not secure the cosmos hub.

![stake&forget](https://imgur.com/0uR6CYS.jpg)

Network share growth is slowing down as rewards become diluted by inflation and in following years it will become negative. Slashing will affect the whole holdings including rewards. 

# 2) Stake and compound

This strategy is especially effective when inflation is rising and there exists a strong belief in future ability of atom to capture transaction fees flow from validating on different chains, issuing assets and so on. In this case, additional gains from people who do not stake are re-delegated on an annual basis.

![stake&compound](https://imgur.com/cJxdAUG.jpg)

Staking ratio stays constant so return on staking (RoS) is not changing and network share growth is stable in this example. Obviously rewards of this delegator outperformed the previous one. This strategy also has trade-offs. If a big fish bonded to a single validator or validator itself has a big stake or delegated amount, implementing this approach may lead to high network centralization and power concentration. This will not benefit network participants and would undermine security of the cosmos hub. 

This scenario is also subject to slashing risk the most. To increase safety of the funds it is highly recommended to diversify stake amongst various validators even if slashing sounds like something unrealistic.

# 3) Stake and maintain the same share slightly releasing profit exceeding standard inflation

If `100%` of total atom supply is locked in staking every holder will have equal provisions. In fact, there would be no difference in their network ownership and no one would be diluted. In this case we cannot gain extra atoms and total yield would be zero. Inflation should be considered as a **feature that protects ownership of the network from dilution and as a punishment for every holder who does not contribute to the cosmos hub security**. Profit from inflation accrues only from those who do not stake. Their network share is redistributed among others and there is always an option to withdraw this addition without ownership reduction.

![maintain the network ownership](https://imgur.com/tz2eLNj.jpg)

This approach is also good as a hedge against slashing in the long run. The more frequently you withdraw and sell rewards the less atoms will be affected. This way of staking is especially effective if inflation and annual RoS are falling and network ownership growth is slowing down. Selling portions of atom provisions may be considered as a hedge against price fluctuations. If atom price is expected to decrease in a particular period released profits could be used to buy back with a better price. If price is expected to rise and future dynamic is uncertain then it could be a great cure against greed and a good way to release profit without taking away the ability to generate revenue in future from assets and losing network ownership.

# Comparison in dynamics

Let’s take `15 year` period and look at the performance of these strategies in dynamics. Initial atom supply in this example is `100 atoms`. Four delegators have `10 atoms` each:
* D1 stake & forget
* D2 stake and compound
* D3 stake and maintain the network ownership selling the rest
* D4 just hold not staking at all
Inflation is `7%` staking ratio constantly rises from `57%` to `77%` with a five year stop at `67%`

![Big table](https://imgur.com/1ABULcA.jpg)

For that period of time D1 ended with `34,82 atoms` accumulating `24,82 atoms` pending withdrawal, D2 ended with `98,88 atoms`, D3 earned `65,07 atoms` selling `17,32` of them during that time maintaining stake of `47,75 atoms` and D4 left with `10 atoms` like in the beginning. Overall holdings could be visualized in the following graph.

![Holdings growth graph](https://imgur.com/L3Zd6kL.jpg)

On that graph we do not count sold atoms of D3, even so, after some time a delegator who was selling the surplus of atoms would have more holding than one who had just passively staked. If we look at a network ownership dynamics we notice that at the finish D3 maintains higher share even without increasing it. If at the end of the experiment total holdings of each delegator are affected by double-sign slashing (except D4) we see that D2 will lose twice as many as D3. 

![Network share dynamics](https://imgur.com/BGoQQ3g.jpg)

In the first half of the period D1 had more atoms than D3 but It is possible to be higher on the graph for this period if D3 will release less profit and re-delegate more atoms in order to slightly increase his share but not as much as D2. For the first year you can re-delegate all provisions and slightly decrease re-delegation percentage for the following years but not breaking the initial ownership. In fact you can mix the option of compounding and partial selling in any variation that suits your expectations.

Network share changes differently for delegators. At the end of a period when inflation is decreasing because staking ratio is `>67%`, D2 experiences the highest decrease in the network share growth while others experience a decrease in their network ownership losses. 

![Network share change](https://imgur.com/T1rcLZE.jpg)

Simply speaking, it becomes more reasonable to implement the strategy of D3 when annual RoS is decreasing. If RoS is rising, network share growth rate is also rising boosting total holdings.

# Conclusion

We discussed various options of managing staking balance mostly for educational purposes and deeper understanding of staking process economic variables. Inflation mechanism may drastically change in the near future as it would not be necessary to hold such a high rate of dilution if there were enough economic incentives to stake for participants, and revenues from transaction fees and other options would exceed inflationary rewards providing a stable source of income for validators to maintain their infrastructure and fund operational costs.

---

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake ATOMs with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)
