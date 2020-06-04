---
title: "Cosmos' Game of Zones Phase 3: a Deceptive Rootchain that will trap your tokens"
description: "For Game of Zones Phase 3 we made a special deceptive zone to demonstrate IBC threat models"
date: 2020-06-04
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/AWFWheI.jpg'
layout: Post
category:
  - cosmos
authors:
  - vshvsh
company:
 - p2p

---

*For Phase 3 we prepared a specific deceptive zone whose purpose is to trap your transfers and let the zone ‘root’ users to claim them on the counterparty chains.* 


# Evil Rootchain

For Phase 3 we prepared a specific deceptive zone whose purpose is to trap your transfers and let the zone ‘root’ users to claim them on the counterparty chains.

That zone does not expose a vulnerability in IBC, neither it is something unexpected by people who made ICS: it’s merely an illustration of IBC threat model and how it can be used to steal user funds.

We modified `createOutgoingPacket()` function to work like that:
- user who has at least some root denom tokens (i.e. 1000root on balance) can create any outgoing transfers they want, even if they don’t have the required funds;
- user who has no root tokens cannot transfer any tokens back to a source chain.

Here’s the [gist](https://gist.github.com/vshvsh/88964912dbd389332c53bc239fb59168) of how it’s done, and the [full project](https://github.com/p2p-org/gaia-rootchain).  

So if someone was to transfer, say, doubloons to our deceptive chain, they couldn’t take it back - but any root user can redeem fake tokens for real tokens on an origin chain.

That means that a regular user who sends funds to a deceptive chain can’t cash them out on an origin chain - they’ve basically lost they funds. But it’s not apparent, because internal transfers on the zone work fine, and until a user tries to redeem the transferred token they won’t see any problems.

Moreover, malicious root token holder can redeem those tokens instead of an original sender or transferred token holders, and that wouldn’t be apparent too without aggregate analysis of all transfers across all channels.

We deployed it on responsible-3 zone (heads up: responsible was an approved sockpuppet account of p2p all along; it didn’t compete in earlier phases where scarcity and/or account throughput were an issue).

# Demonstration

An unsuspecting user makes a transfer of 100 very valuable ptp tokens to responsible-3:
```
>rly tx transfer p2p-org-3 responsible-3 100ptp true cosmos16zx4s8nculu94vhm07fd3qlg8g7grtj0xk49dg
I[2020-06-03|18:21:59.489] ✔ [p2p-org-3]@{50776} - msg(0:transfer) hash(962733C0568867D6F4EA70417EB1E747FCC136396E3E020D5351DAD011ACBE6D) 
I[2020-06-03|18:22:09.218] ✔ [responsible-3]@{50793} - msg(0:update_client,1:ics04/opaque) hash(87D2802713DB702334AB843CAD488841E5A3E1A7C95DCB0DA0344E5039A77674)
```

They now have transferred tokens in the wallet, but can they transfer them back?
```
>rly q bal responsible-3 
100transfer/fmqnwnlqii/ptp
```

```
>rly tx transfer responsible-3 p2p-org-3 100ptp false cosmos16zx4s8nculu94vhm07fd3qlg8g7grtj0xk49dg
I[2020-06-03|18:56:09.666] ✘ [responsible-3]@{51200} - msg(0:transfer) err(sdk:4:failed to execute message; message index: 0: need to be root user to send ibc source=false transfers: unauthorized) 
Error: failed to send first transaction
```

No, they can’t. Here comes a root user:
```
>rly q bal responsible-3                                                                           
100000000000root,975000rsp
```

They don’t have any `100transfer/fmqnwnlqii/ptp` tokens, but they can redeem 100ptp on p2p-org-3 anyway:

```
>rly tx transfer responsible-3 p2p-org-3 100ptp false cosmos1hazzkmrvxcrxvxv98daslkw0a7uax5djqgn20d
I[2020-06-03|18:58:41.425] ✔ [responsible-3]@{51230} - msg(0:transfer) hash(24456218B05964F3B7B57EFD1F25E2CEEDA9BAAEBC957D0A6E315D801929E093) 
I[2020-06-03|18:58:49.540] ✔ [p2p-org-3]@{51217} - msg(0:update_client,1:ics04/opaque) hash(769158A9735DF93496F08F631E5D1AB04CCF081DFC132700E25C970D33DF74DB) 
```

```
>rly q bal p2p-org-3                                                                               
100ptp
```

## Conclusion

The prolonged existence of actively malicious “rootchains” is not realistic - people wouldn’t use it for anything - but we expect people might deploy temporary ones for fishing or scamming purpose when IBC connections are permissionless and IBC-enabled wallets allow arbitrary chains to be added. 

More than that, any sufficiently complicated IBC-enabled blockchain can become a “rootchain” due to vulnerability, especially if we’re talking about complex smart contract chains and dynamic IBC like on Agoric or CosmWASM chains. Both trapping the funds on receiving chain forever or dishonest redeeming on source chain can be a result of an exploit on undertested code.

We think that the community should build tools for total supply observability across chains and means to swiftly stop IBC transfers with malicious or vulnerable zones or applications via governance to prevent user fund loss.


-----
*The best way to support our contribution is to [stake ATOM with P2P Validador](https://p2p.org/cosmos).*

---

[P2P Validator]() is a world-leading non-custodial staking provider securing more than $40 million by over 1000 delegators/nominators across 15+ top-notch networks. We've been validating in Cosmos Hub since the first day of mainnet. P2P Validator provides comprehensive due-diligence and invested its own funds in ATOM in 2017 intending to support Cosmos network in the long term.

**Web:**[ https://p2p.org](https://p2p.org/)
**Stake ATOM with us:** [p2p.org/cosmos](https://p2p.org/cosmos)
**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)
**Telegram:** [https://t.me/P2Pstaking](https://t.me/P2Pstaking)

