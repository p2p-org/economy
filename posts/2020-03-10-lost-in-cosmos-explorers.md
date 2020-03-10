---
title: "Lost in Cosmos explorers.."
description: "Triggers for reward withdrawal that are not displayed by most explorers"
date: 2020-03-10
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/oKWGTp8.jpg'
layout: Post
category:
  - staking, cosmos, kava, regen, terra, economy, iris
authors:
  - AlexBond
company:
 - p2p
---

Every transaction that is recorded in non-private blockchain can easily be retrieved for analytical or other purposes providing clarity for end users. With such transparency everyone can get a trusted record of any event since the start of the network. But is it really an easy task for someone without deep knowledge in code and various API endpoints to get all the data they need?

### Transparency limit

You may argue that there are multiple explorers built for this purpose but each of them focuses on various goals and doesn’t give a complete picture of all events happening in a particular network. For an ordinary user like me, explorers act as a window in this magic world of blockchains and **our understanding is limited by the events various tools decide to display**.

Blockchains are still new and complex to understand. The increasing number of projects with a different logic and various triggers is aggravating. Transparency matters especially for financial transfers and events that can be used for accounting purposes. For example, in Proof-Of-Stake blockchains it can be a withdrawal of accumulated rewards.

A diversity of high-quality explorers is significant for building user commitment to the network and facilitating trust although more tools do not always result in better visibility. Some explorers focus more on usability, which is also very important but it still is not conductive to increasing transparency for users of the network.

### Unobvious events in Tendermint blockchains

Let's take a look at the reward withdrawal process in Cosmos Hub. Surplus accumulates in a validator pool and can be withdrawn to the corresponding staking address manually. Basically, a delegator withdraws rewards at any point of time to receive them on address. Explorers show this operation with names like GetReward or Withdraw Reward. In fact that's not the only action that triggers reward withdrawal.

#### **Example**

Let's take a random account and check the information about its balance on[ Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8) block explorer.

![img](https://lh3.googleusercontent.com/pbOzSOzQL9RN3I6K4tQvoDc8H9zZLT-ZJOY9uc9mvgjKy7FJQiwFIU6pwDJqulcdAhbNnSKQzmD8HvVnDNI-YpSiARkWIqCIEPtCQ298Lk3LVBPScGENEowCnADgfk56XZIHhhaJ)

![img](https://lh5.googleusercontent.com/y3ff9Aa9VysjtS0XPxBf8cYKm454NpsyTDuTP10YvrNhVpyTulyMTyiPYA6Tp6PLVNG4JKHhoOfGT_9GpBw8_A11-uQjoziRD3r4Zu9yGB8PZq2D64NpHyphCuhtKOfpRcC-ubk_)

If we calculate total balances using this transaction data we should get:

- Received: *484,7076 ATOM*
- Delegated: *474 ATOM*
- *Tx Fees: 0,015 ATOM*
- Available: ***10,692625 ATOM***

And here are values from[ Mintscan](https://www.mintscan.io/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8):

![img](https://lh4.googleusercontent.com/8ceoFL9qNY5ilkmOy7LlVAYH2nwXXNDpP5dp3pjipl7W-sgHm5HB7fM5_lIeAlDjwk0qg-fg09P_FBTMYUW0VultsCX6PHOoxH2yonQ92cA5r6KdMB0_x-rbMhNVWzFFvPMOhkr_)

The same is true for the same address on [Forbole](https://cosmos.bigdipper.live/account/cosmos1d5lu67hu3lhqtw6zyv7uy4gkfpdtfnzxw0wga8):

![img](https://lh4.googleusercontent.com/MsN4x__zDhUQxXEUhLzbxBasPI8pkM_kiOgrQQ9JPnOuvv4EfFp9S11jqx9VrFPLMB1Fnbp7AsfH2GXYwh5zDU1jDvWvd2UpVGiQH57GT4fIfNQgfHEY6qJEsnwlw8HlYp-IIVNT)

We see an additional 0,971002 ATOM, but where did they come from if there was no withdraw transaction made by this address? Of course you may say it's even less than 1 ATOM who cares? But systems based on a code should not allow any mistake. So, is the displayed balance correct or wrong? Let's look into it.

In fact there are hidden events that trigger reward withdrawal but are not displayed on most explorers simply because they serve another purpose and these minimal changes do not correspond much to the observation of what is happening in general.

There are five core types of actions delegators usually perform:

- Delegate to a validator
- Redelegate to another validator
- Undelegate from a validator
- Withdraw accumulated rewards
- Send available tokens to another address

The first four of them initiate reward withdrawal, and this event for the first three of them usually is not displayed by most explorers.

In some cases, to apply updates of the network, validators stop producing blocks and upgrade node software. This process requires a transition to a new chain with a new genesis file that stores the actual state at the moment of chain halt. When the new chain becomes active what happens with accumulated rewards?

These rewards also become available, the transition to the new chain triggers withdrawal but the event is also hidden and not obvious to delegators.

### Final thoughts

Every public network needs a variety of analytical tools to allow people without advanced technical skills to get information about what is going from different angles. In Proof-Of-Stake blockchains a clear reward history and accessibility of historical data are especially important.

Having more explorers doesn't guarantee high diversity of data but still contributes to increasing user confidence and shows different aspects of a particular network. A higher number of explorers can increase transparency. Every message or event can be important if it clarifies some valuable logics of the system.

**What if you need to prove received reward referring to a particular event that simply does not displayed by any explorer?** Thinking of that, we decided to conduct technical research to make all rewards together with corresponding messages accessible and transparent across all versions of Cosmos Hub as a starting point.

------

*Want to stake with us? Alexey will be happy to help. Contact* *am@p2p.org* *to get personal assistance.*

------

**P2P Validator** provides secure non-custodial staking. Subscribe to our channels and stay tuned for updates and new blog posts.

**Stake ATOM with us:**[ https://p2p.org/cosmos](https://p2p.org/cosmos)

**Web:**[ https://p2p.org](https://p2p.org)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/p2pvalidator](https://t.me/p2pvalidator)