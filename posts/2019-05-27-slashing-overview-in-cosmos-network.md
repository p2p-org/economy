---
title: "Slashing overview in cosmos network"
description: "This post is about the role of slashing mechanism in cosmos ecosystem"
date: 2019-05-27
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://i.imgur.com/aqETFSr.jpg'
layout: Post
category:
  - economy
  - cosmos
authors:
  - AlexBond
company:
 - p2p
---
We can define a cosmos network as a *social galaxy* with various entities and different types of participants who are fully self-responsible for decisions they make. To make such system as healthy as possible, minimize cheating and other fraudulent behavior that cause loss of confidence, it should contain a set of rules, instruments and other incentives which will determine the right direction together with moral ethics.

Slashing is an event, which results in a loss of stake percentage, depending on the type of network violation and jeopardizing the safety of other participants. It represents not only a financial incentive to act properly but also is a measure to prevent nothing at stake problem. 

Cosmos is a complex ecosystem where atom act not only as an economic incentive but also represent a governance unit playing a crucial role in ecosystem security. In that way, slashing becomes a tool that influences voting power distribution. 

Besides, it affects the authority of caught fraudlent participant, motivates validators to improve their infrastructure and in case of delegators, to provide a deeper due-diligence and diversification amongst validators. Slashing also act as a decentralization mechanism motivating re-delegate atoms to more reliable or even smaller validators with equal level of security and infrastructure set up. 

For now this motivation can be not so obvious but after enabling Inter Blockchain Communication (IBC) and feature of shared security when validators will be slashable on multiple validated chains slashing risk will be different for all validators depending on conditions and number of  chains they operate.

# Slashing events

There are two types of events when stake liquidation happens:

* **Downtime** occurs when validator is offline and do not participate in block commitment signing less than `5%` of the blocks in a row of `10 000`. This situation leads to loss of `0,01%` stake not only for validator but for bonded to him delegators as well. In addition, validator drops out of the consensus and do not earn block rewards for at least `10 minutes`. After fixing the issues validator can re-join validators set by sending un-jail transaction.

![Downtime](https://imgur.com/vpHkrTG.jpg)  
* **Double-sign** can lead to more harmful consequences than the previous one. It can cause double-spend or chain fork. The wrong setup of the validator’s infrastructure or key compromise are the most common occasions that cause this type of slashing. In this case, stake penalizes by `5%` and validator loses the right to propose blocks and earn rewards without an ability to un-jail. All delegators of this validator enter the unbonding period, which lasts `21 days`.

![DoubleS](https://imgur.com/SEv8vKf.jpg)  

**Slashing also affect atoms, which were in unbonding phase** at the moment when one of these events happened. If a validator have low self-bonded ratio (low self-delegated amount) and large amount bonded then, in theory, it could have economic incentive to double-sign. This behaviour will lead to a loss of confidence in this validator and as a consequence inability to earn transaction fees and atom provisions in future missing opportunity of the long term ecosystem adoption and development. 

Validators with low self-delegated amount should be able or will have to find the way to maintain resilent infrastructure with low costs in order to increase self-delegation and/or commision rate while bonded atoms to them are increasing.

If self-bonded ratio is decreasing or low in some cases (for instance, validator bonded to other validators in order to diversify holdings or increase network decentralization), if validator charges fair commission long term incentives should overcome short term gains. Commission rate should be reasonable and cover existing expences. If a validator with high stake is not earning to maintain infrastructure and operations (by self-bonded amount that generate rewards and/or commission rate) it is at least concerning. 


# How slashing works in theory

Assume that we have three validators:  
* `V1` with a commission of `5%`
* `V2` with a commission of `8%`
* `V3` with a commission of `9%`

If delegator bond to `V1` with an annual return on staking (RoS) around `10,2%` for **5 years** and *without taking advantage of compounding*, then his cumulative interest for five years nominated in atoms will be `48,5%`. Let’s have a look at how *monthly compounding* with slashing will affect this number. To simplify calculation we assume that:
 **In the case of downtime**, it happened *three times* and delegators stake passively without re-delegating after the first event:

1. End of the 2<sup>nd</sup> month and `2 days` passed before un-jail  
2. End of the 7<sup>th</sup> month and `1 day` passed before un-jail  
3. End of the 11<sup>th</sup> month and `1 day` passed before un-jail

**In the case of double-sign**, slashing and unbonding period occurred once at the end of the 12<sup>th</sup> month. After `21 day` of unbonding delegator bonded to another validator with the same commission rate. I will use the same conditions for other comparisons in this article. Overall result for delegator will look like:

![Results](https://imgur.com/XQo0lyR.jpg)

We can notice that:

* Delegator who took advantage of monthly compounding even with a double-sign event outperformed another one who just delegated once and forgot. The magic of this feature I will cover in the next article.

* Downtime has not much influence on the result for delegator even if it happens quite often and validator re-join validator set much later than current jail time for downtime (10 minutes). It has a bigger influence on the validator in the long term. His delegators will lose confidence and will immediately re-delegate their holdings to others. Until validator un-jail, the staked ratio will be lowered by the number of atoms delegated to him. This will increase voting power of other validators resulting in higher probability of proposing a block and may lead to higher transaction fee gais in comparison with validators who often go offline.

* Double-sign has the most harmful event on RoS and the difference is about `9%` in comparison with delegator who have chosen an honest and secure validator

If we will compare the performance of delegators who bonded to different validators with a various commission rate, we will see that RoS for `V3` is higher than RoS for `V1` and `V2` if double-sign occurred. For a taken period of 5 years this will be correct even if the commission of `V3` will be `16%` that is more than three times higher than the `5%` commission of `V1`.

![Slashing example](https://imgur.com/9QnrSOH.jpg)

You can notice that in the longer term (in our example >5 years)  current double-sign slashing do not cause huge effect on the performance and there still exist high incentive for delegators to choose validators basing predominantly on the commission rate. In theory, this may cause weaker decentralization level of the network. 

Downtime slashing has even less voting and economic influence. Current slashing conditions should be considered as a starting point for further discussion on that topic and may be changed in future via governance mechanism. 

For example, every repeating downtime event over the period of `X` could cause atom slashing equivalent to `prev_slashing_percentage * 2`.  If a validator constantly goes offline this will cost more for him and his delegators thus increasing incentive to properly maintain the state of own infrastructure and for delegators to re-delegate to others. One of concerns about changing initial parameters is a lack of empirical data so as the network evolve we will see more experiments in this field.

# Smart ideas for delegators to protect from slashing consequences

No one can predict the future and **one of the best ways for delegators to protect themselves from misbehavior is diversification**. Suppose that delegator bonded all his atoms to `V1` with the lowest commission possible, `5%` in our case. Another delegator diversified amongst all three validators equally - `33%` for each. If `V1` will be caught on double-sign, the second delegator will get `2,5%` higher RoS than the first one who put all atoms in one basket even if `V2` & `V3` went offline for some reason.

Another idea is responsible behavior. Bonding to a validator is not a blind step and simple way to earn passive income. To be up to date delegators should continue to monitor validator uptime. Frequent downtimes may indicate unreliable infrastructure. 

* What actions validator take in order to prevent slashing conditions? 
* Does valiadator disclose an infrastructure setup? 
* Is it secure? 
* What upgrades and improvements are in the roadmap? 
* Is the commission rate sufficient to support validator activities and maintain reliable infrastructure? 
* What is the responsibility level of a validator and how valuable is it's contribution to the ecosystem development? 

Answers to these questions can help delegators to diversify amongst the most remarkable validators.


The most prominent validators who set up well-protected infrastructure and have a high level of confidence can offer refunds for their delegators in case of slashing event. In this case reserve funds or the idea of developing slashing insurance for delegators make sense. For some delegators who have no ability to follow up with the state of their atom performance this could be a reasonable solution. 

> The first rule – do not lose your money, the second rule – remember of the first one.  
> <right>"Warren Buffet"</right>

In the cosmos ecosystem, your atoms are your assets, which can generate additional income for you. Take care of your holdings and be responsible for the decisions you make.

---

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake ATOMs with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)
