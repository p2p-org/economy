---
title: "Polkadot overview for newcomers"
description: "Brief overview of Polkadot for newcomers"
date: 2020-08-18
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://i.imgur.com/jf8tYVI.png'
layout: Post
category:
  - polkadot
authors:
  - GlebPalienko
company:
 - p2p

---

# Polkadot overview for newcomers

*August 18th, 2020* - Polkadot almost became a fully-operational network by reaching the 4th of five milestones - opening transfers between accounts. The network is expected to finish the rollout plan this autumn by enabling parachain auctions and cross-chain interaction protocol, but, which might be important for newcomers, now you can legally buy and sell DOT tokens. If you are someone who missed the original 2017 and small 2020 sale but still are interested - this article is for you.

## Which wallets to use?
We recommend starting exploring Polkadot with official [Polkadot.js browser wallet](https://polkadot.js.org/apps/#/accounts) (you would also need to install [polkadot.js browser plugin](https://github.com/polkadot-js/extension)). This is the official wallet supported by Web3 Foundation that provides all possible opportunities for DOT users. If you are not a fan of desktop wallets, you can just walk through all tabs and get a good overview of Polkadot. The full list of supported wallets can be found [here](https://wiki.polkadot.network/docs/en/build-wallets). 


You will notice that a lot of them are in the development stage, but the following ones are fully functional:

- [Parity Signer](https://www.parity.io/signer/)
- [Lunie](https://lunie.io/)
- [Polkawallet](https://polkawallet.io/)
- [ImToken](https://token.im/)
- [Math wallet](https://www.mathwallet.org/polkadot-wallet/en/)

Please note that the wallets may not provide full functionality (e.g., Democracy, Council voting, Extrinsic, etc.) - but all of them support transfers and staking.

## Where to buy DOT?
Generally, we don’t give advice on the exchange as your experience may differ based on the country of your residence or KYC/AML procedures. As you’re reading this page, we believe you are already a crypto person and you don’t need common advice like picking a trusted exchange. But there’s one thing you may not be familiar with:

**On August 21st, Polkadot will go through the redenomination process. It means the “old” DOT will be equal to 100 “new” DOTs. This was the choice of community - you can read more in the [official post](https://polkadot.network/the-results-are-in/). This change will not be done by changing any core code - from 21st 1 DOT will be equal to 10^10 Plancks (the smallest fraction of DOT), while now it’s 10^12 Plancks. If you buy your DOT now, you will just see 100x more DOT on your balance after 21st.** 

## How to create an account?
Please use [our guide](https://economy.p2p.org/create-account-in-polkadot-network). The whole process will take several minutes.

## How to nominate?
We have a general [guide on nominating](https://economy.p2p.org/polkadot-nomination-guide). Here are some additional tips that you might find helpful:
- You can nominate from 1 to 16 validators from one account. The validator election mechanism will distribute your stake to validators in an optimal way (generally, for one validator). We recommend to nominate trusted validators as the right selection will provide better yield and protect you from [slashing](#what-is-slashing-and-how-does-it-work). 
- Your nomination status will update every day (around 1PM CET - when the validator election happens). The meaning of each status:
	* Active - your nomination is working, and one of the validators you’ve chosen is in the active validator set. Everything is OK.
	* Inactive - it is OK to have some inactive nomination while you have at least one active - it means that your nomination is working, but some of the validators you’ve chosen are not in the active set. 
	* Waiting - you will see this status if you’ve made a nomination but the elections haven’t happened yet. Don’t worry, just wait for the validator elections to be held.
	* Renomination needed - this signals you that you need an update of your nomination.
- Bonding and unbonding
	* Bonding means you’re locking your funds to work in staking. While funds are locked, you can make nominations, update them, vote, etc. To make your funds liquid you should go through unbonding.
	* Unbonding might be performed when you want to stop nominating and move or sell your DOTs. Please be careful - the unbonding period for Polkadot is 28 days, so basically you won’t be able to transfer or stake your DOTs for almost a month!
- Controller account is a special account that might be linked with your primary account (stash in terms of Polkadot) to perform some actions (e.g., staking). It is good practice to have a controller account connected to your stash and don’t touch the last one without a significant reason. What is more important, you can basically share your controller account with 3rd parties to perform staking while keeping your stash keys with you and your funds will be safe!

For those of you who have more than 500 DOT we have a [special offer](https://economy.p2p.org/polkadot-nomination-strategies/#p2p-validator-special-offer)! 

## How do rewards work?
At the moment, Polkadot provides around 14-15% APR on your stake. The following things might influence your profit:
- Validator fee. The average validator fee is around 3%.
- Luck. The profit for each validator is proportional to the number of blocks produced during the era. These numbers will be equal in the long run, but for some days you may notice a bit more or a bit less profit than predicted - so basically you should not worry about this.
- Total stake on the node. Polkadot provides staking rewards that are almost equal for every validator. After that, the validator automatically distributes the profit for the nominators after taking a validator fee. So, nominating to the validator that has 20k DOT in nominations will bring you twice as much as nominating the one with 40k DOT in nominations.
- Overall validator performance. In the real world, different validators have different hardware resources, connectivity, etc. - all of these factors may affect nominators’ profitability.
- Slashing penalties. [Please take a note on slashing and how it works in Polkadot](#what-is-slashing-and-how-does-it-work).

**Please use our [article with nomination strategies](https://economy.p2p.org/polkadot-nomination-strategies) that are based on the stake you hold** 

Other important points on the rewards:
- Rewards are distributed each era (24 hours for Polkadot).
- By default, the rewards are not claimed automatically. This can be done either by you or by your nominated validator. P2P Validator is periodically claiming rewards for our nominators, so you should not worry about this if you nominate us.

## What is slashing and how does it work?
Slashing is a penalty mechanism that provides economic incentives for validators to play fair and nominators to choose the right validators. Slashing is triggered when a validator makes a double sign or more than 10% of the network goes offline. This can also happen because of a software bug. In such cases, the slashes are applied after 28 days and can be canceled by democracy voting.

As the slashing is applied to both validator and its nominators, you may lose some portion of your stake. To minimize risks to be slashed:
- Select 16 validators in your nomination.
- Select only the validators you know and trust.
- Don’t try to make maximum profits - staking is a marathon, not a sprint. The risk of losing a portion of your stake might outweigh the better profitability of an unknown validator.

## What resources to use or follow?
For all newcomers to Polkadot ecosystem, we recommend the following resources: 
- Our [blog articles about Polkadot](https://economy.p2p.org/category/polkadot/)
- Join the [official Polkadot group on telegram](https://t.me/PolkadotOfficial)
- Join the [community group in Element](https://matrix.to/#/!FdCojkeGzZLSEoiecf:web3.foundation?via=matrix.parity.io&via=matrix.org&via=web3.foundation)
- Use the official [wiki of the project](https://wiki.polkadot.network/docs/en/getting-started)
- Get familiar with Polkadot in action using [Polkadot.js](https://polkadot.js.org/apps/#/accounts)
- Use [Polkascan](https://polkascan.io/polkadot) or [Subscan](https://www.subscan.io/) to dive deeper in addresses and transactions
- Give [Kusama](https://kusama.network/) network, a wild cousin of Polkadot, a try 


## About P2P Validator
[P2P Validator](https://p2p.org/?utm_source=blog&utm_campaign=polkadot_for_newcomers) is a world-leading non-custodial staking provider with the best industry practices and proven expertise. We provide comprehensive due-diligence of digital assets and offer only top-notch staking opportunities securing more than 100 million of USD value. At the time of publishing, P2P Validator is trusted by over 2000 delegators across 15+ networks.

------

*Do not hesitate to ask questions in our [Telegram chat](https://t.me/P2Pstaking) or contact Alex via am@p2p.org or Gleb via gleb.p@p2p.org. We are always ready to help and open for communication.*

------

**Web:**[ https://p2p.org](https://p2p.org/?utm_source=blog&utm_campaign=polkadot_for_newcomers)

**Stake DOT with us:** [https://p2p.org/polkadot](https://p2p.org/polkadot?utm_source=blog&utm_medium=economy&utm_campaign=strategy)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:** [https://t.me/P2Pstaking](https://t.me/P2Pstaking)