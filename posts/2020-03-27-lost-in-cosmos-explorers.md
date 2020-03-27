---
title: "Lost in Cosmos explorers..."
description: "P2P Dashboard now show all reward withdrawals that are not displayed by most explorers"
date: 2020-03-27
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/oKWGTp8.jpg'
layout: Post
category:
  - staking
  - cosmos
  - kava
  - terra
  - regen
authors:
  - AlexBond
company:
 - p2p
---

Existing Cosmos explorers show limited information. In some cases, reward withdrawal happens not only by initiating `withdraw` transaction and there are unobvious events, which cause that action. We have added these hidden events to [P2P Dashboard](https://p2p.org/#dashboard-block), implemented full reward history across all Cosmos Hub versions and opened it for community. Below, I will walk through the topic in detail with examples.

### Transparency limit

Every transaction that is recorded in non-private blockchain can easily be retrieved for analytical or other purposes providing clarity for end users. With such transparency everyone can get a trusted record of any event since the start of the network. But is it really an easy task for someone without deep knowledge in code and various API endpoints to get all the data they need? 

You may argue that there are multiple explorers built for this purpose but each of them focuses on various goals and doesn’t give a complete picture of all events happening in a particular network. For an ordinary user like me, explorers act as a window in this magic world of blockchains and **our understanding is limited by the events various tools decide to display**.

Blockchains are still new and complex to understand. The increasing number of projects with a different logic and various triggers is aggravating. Transparency matters especially for financial transfers and events that can be used for accounting purposes. For example, in Proof-Of-Stake blockchains it can be a withdrawal of accumulated rewards.

A diversity of high-quality explorers is significant for building user commitment to the network and facilitating trust although more tools do not always result in better visibility. Some explorers focus more on usability, which is also very important but it still is not conductive to increasing transparency for users of the network.

### Unobvious events in Tendermint blockchains

Let's take a look at the reward withdrawal process in Cosmos Hub. Surplus accumulates in a validator pool and can be withdrawn to the corresponding staking address manually. Basically, a delegator withdraws rewards at any point of time to receive them on address. Explorers show this operation with names like GetReward or Withdraw Reward. In fact that's not the only action that triggers reward withdrawal.

#### **Example** (27.03.2020)

Let's take a random account and check the information about its balance on[ Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8) block explorer.

![img](https://imgur.com/FXDDdMR.jpg)

![img](https://imgur.com/xgM9HKW.jpg)

If we calculate total balances using this transaction data we should get:

- Received: *484,7076 ATOM*
- Delegated: *474 ATOM*
- *Tx Fees: 0,015 ATOM*
- Available: ***10,692625 ATOM***

And here are values from[ Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8):

![img](https://imgur.com/9AQXf6z.jpg)

It is also true for the same address on [Forbole](https://cosmos.bigdipper.live/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8):

![img](https://imgur.com/s2My69D.jpg)

We see an additional 0,971002 ATOM on the available balance, but where did they come from if there was no withdraw transaction made by this account? Of course you may say it's even less than 1 ATOM who cares? But systems based on a code should not allow any mistake. So, is the displayed balance correct or wrong? Let's look into it.

In fact, the balance is correct. **There are hidden events that trigger reward withdrawal but are not displayed on most explorers**. These tools serve another purpose and these events do not correspond much to the observation of what is happening in general. Nevertheless, these triggers are still crucial for generating full withdrawal history and bringing clarity for delegators.

There are five core types of actions delegators usually perform:

- Delegate to a validator
- Redelegate to another validator
- Undelegate from a validator
- Withdraw accumulated rewards
- Send available tokens to another address

The first four of them initiate reward withdrawal, which is usually not displayed for the first three  actions by most explorers.

On [P2P Dashboard](https://p2p.org/dashboard/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8) you can check reward withdrawals related to the same address.

![img](https://imgur.com/1GVbU5l.jpg)

In some cases, to apply updates of the network, validators stop producing blocks and upgrade node software. This process requires a transition to a new chain with a new genesis file that stores the actual state at the moment of chain halt. When the new chain becomes active what happens with accumulated rewards?

These rewards also become available, the transition to the new chain triggers withdrawal but the event is also hidden and not obvious to delegators.

### P2P Dashboard

Every public network needs a variety of analytical tools to allow people without advanced technical skills to get information about what is going on from different angles. In Proof-Of-Stake blockchains a clear reward history and accessibility of historical data are especially important. **What if you need to prove received reward referring to a particular event that simply does not displayed by any explorer?** 

Thinking of that, we decided to conduct technical research to make all rewards and withdrawals together with corresponding messages accessible and transparent across all versions of Cosmos Hub.

> We have added ability to check all withdrawal events across all versions of Cosmos Hub on [P2P Dashboard](https://p2p.org/#dashboard-block) and made it open for community. In addition, any ATOM delegator can check all withdrawals, get full reward history and download a report in CSV for multiple addresses.
>

To start, go to[ https://p2p.org](https://p2p.org) and click `Get started` button in the top right corner. Connect to the dashboard manually by entering the address or using your Ledger device.

------

*Want to stake with us? Alexey will be happy to help. Contact* *am@p2p.org* *to get personal assistance.*

------

**P2P Validator** provides secure non-custodial staking. Subscribe to our channels and stay tuned for updates and new blog posts.

**Stake ATOM with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Web:**[ https://p2p.org](https://p2p.org)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)