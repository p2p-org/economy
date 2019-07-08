---
title: "How Terra prints money without centralized authority"
description: "This post explains basic concepts of Terra protocol"
date: 2019-07-08
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/FRikroH.jpg'
layout: Post
category:
  - economy
  - terra
authors:
  - AlexBond
company:
 - p2p
---

It is not a secret that governments control the money printing press. It is a powerful tool that allows the filling of the economy with liquidity when it is needed. This process usually dilutes share of currency holders and causes an inflation surge, but also may boost spendings and ability of entrepreneurs to borrow cheaper and pay their employees thus resulting in higher employment rates leading to higher tax returns for the government. Wise usage of currency emission allows governments to accumulate rising tax gains and earn interest rate paid on issued money, which are in fact profit from money creation - seigniorage. These gains are used to stimulate fiscal spending and support economic growth.

![Gov scheme](https://imgur.com/jOMAa3b.jpg)

One of the most common uses of money is as a convenient unit of exchange for buying goods and services. To earn some, people can produce goods or provide some useful services, but they do not have an opportunity to earn profit from the emission. This process is monopolized by centralized entities. But, imagine there is an option to participate in a novel currency emission and have rights to get a portion of seigniorage in an algorithmic and decentralized manner?

# Terra brief overview

Terra project implemented the best practices of government fiscal policy and fulfilled them with solid additions that benefit e-commerce platforms (providers) and users as well. The concept combines features of cheap cross-border transactions in stablecoins and the ability for every user to participate in the growing e-commerce economy pretending on portions of transaction fees and seigniorage profit returning capital back to the people.

The core idea of Terra project is to bring on the market a stable family of cryptocurrencies without the necessity to store fiat collateral in the centralized bank and allow parties to transact not worrying about high volatility. This is very important for the crypto community and worldwide adoption. To achieve that goal, Terra developed a complex algorithm of price stabilization, which I will try to explain later.

There are three types of stablecoin implementations:

- *Collateralized* (fiat or crypto or mixed) each coin is backed by a defined currency at some ratio which covers spikes in demand. This type is the most common one and include such prominent projects as Maker (DAI), TrueUSD or Kava (USDX)

- *Algorithmic* (utilizes various mechanisms to follow the peg)

- *Hybrid* (use both features)

Family of Terra stablecoins represent the second type and include various coins maintaining the peg to different currencies, like USD, KRW, and EUR. The less volatile stablecoin in that group is pegged to a basket of currencies [SDR IMF](https://www.imf.org/external/np/fin/data/rms_sdrv.aspx). To provide conversions between currencies, the protocol supports atomic swaps at the fair fiat exchange rate. This allows Terra to offer foreign exchanges efficiently and simplify cross-border payments.

# How Terra achieves price stability and benefit e-commerce providers maintaining stable reward growth for stakeholders

Another important part of Terra project is a staking token Luna. **Luna may be considered as a decentralized collateral, representing a buffer absorbing volatility. It captures the value of the transaction flow and redistributes it among stakeholders** (everyone who stake) creating incentives for them to care about low volatility of stablecoin family. Terra protocol utilizes Tendermint consensus mechanism and another important purpose of staking token is securing the network creating incentives for validators, who play roles of price oracles for inner currency exchanges and broadcast transactions in the network to behave in the interests of the ecosystem and properly provide their services. 

Without fiat collateral and centralized control over the “printing press” it is not easy to provide price stability and control the total supply as well as inner economics in general. To create the market for the own currency, Terra united an *alliance of e-commerce providers in Asia* who are interested in using stablecoins as a payment method offering it to their customers. Terra money is issued in a decentralized manner depending on the demand and total market size. 

For example, if existing supply is not high enough, when transaction volumes grow significantly, demand for stablecoins may also increase. The price of a single unit may rise creating an arbitraging opportunity for the payment network participants who stake Luna. They can exchange one to another with the inner price, and benefit from its deviations out of the peg. In response, to provide the exchange protocol mints requested amount of currency that can be used to release risk-free profit on the open market returning the peg.

![Terra arbitrage](https://imgur.com/kATBcxz.jpg)

When protocol gets tokens in exchange for minting it distribute a part of that provisions to the treasury burning the rest with a `burn rate` which is defined by the protocol and depends on changes in the macroeconomic variables. This module is playing the role of *decentral algorithmic bank* regulating a transaction fee rate and weight of seigniorage that goes to stakers. 

When the economy is in the growth stage, spendings are high. People purchase more goods and services. That results in rising inflation. When inflation surges people cut spendings, slowing them down. It leads to lower profits for companies resulting in the inability to pay their debts or make investments. The economy slows down. To fix it, according to a Keynesian approach, when the economy is rising and families spend a lot, Central Banks should do the opposite to control inflation and be able to step in when the economic cycle is moving closer to a recession. That is exactly the way how the economy is functioning today.

Treasury module is doing exactly the same for Terra economy. In periods of growth and rising transaction volumes it increases accumulation of Luna earned in exchange for minting Terra by decreasing the `burn rate`. When the economy begins to contract in the cycle of lower transaction volumes Terra protocol facilitates spendings using accumulated funds in the treasury, bootstrapping stable demand and economic growth. Another purpose of these provisions is to provide discounts for usage of Terra stablecoin as a payment. If people prefer to pay that way, it obviously creates additional incentives for e-commerce providers to join the Terra network.

The core priority for the success of such a system is to create strong incentives for Luna staking even in periods of instability. This mechanism works like programmatically determined equalizer, managing Luna `burn rate` and `transaction fee rate` which together represent staking rewards. To provide stable staking reward growth, protocol measure and balance these components depending on the economic variables. 

- When the Luna `burn rate` is high it rewards holders as staking power of their assets is rising. To smooth that growth, protocol decreases the `transaction fee rate`.
- When the Luna `burn rate` is low it dilutes holders and staking power is falling. To compensate that, protocol increases the `transaction fee rate`.

# Decentralized resource allocation

Terra may be applied to various sectors with different decentralized applications (dApps) built on top creating multiple token economies managed by the single programmable module. Treasury funds will be filling from various sources. Growth cycles and inflow changes from one sector will cover a decline in another. 

![Pic. 4 - possible dApps and market with flows](https://imgur.com/hPiZFYx.jpg)

Capital allocations for dApps development would be managed by the network participants in a decentralized manner via governance. Every Luna holder may cast a vote taking into consideration actual results of a particular dApp measuring potential benefit. This model creates motivation for dApp providers to investigate new incentive models and offers a unique value proposition competing with others for capital allocation. 

In existing centralized decision making on fiscal spending, a small group of people decide how resources should be allocated. There is a high probability of corruption schemes or lobbying interested parties. In those cases, resources may not be spent efficiently. Future economic outcomes may suffer, undermining the entire ecosystem. 

Terra is aimed to become a convenient medium of exchanging programmable money that enables easy foreign currency swaps and cross-border payments bridging traditional economies with advantages of decentralization. 

An optimal economic resources distribution, a sophisticated stability mechanism, strong network effects and an ability to provide incentives for users is a big step towards mass adoption for digital currency. Now the community can participate in the economy that distributes wealth back to society without the need to trust a limited group of individuals, that may be accumulating lots of money and power, fighting their desire to put some in their own pockets.

------

*I am not an economist or financial adviser, all opinions expressed in this article are my own thoughts on that topic. Special thanks to Do Kwon and Nicholas Platias for their answers and assistance. For deeper dive into the protocol concepts you may visit [Agora, Terra research forum](https://agora.terra.money/).*

------

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake ATOMs with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)

