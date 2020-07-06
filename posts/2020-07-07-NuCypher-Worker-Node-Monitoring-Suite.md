---
title: "NuCypher Worker Node Monitoring Suite"
description: "Free and open-sourced suite of self-hosted NuCypher node monitoring and alerting services using Prometheus and Grafana."
date: 2020-07-07
thumbnail: 'https://i.imgur.com/XY1wX3H.png' 
heroImage: 'https://i.imgur.com/XY1wX3H.png'
layout: Post
category:
  - NuCypher
authors:
  - PaulP
company:
 - p2p
---

As part of the Technical Contributor Phase of NuCypher’s [Come And Stake It (CASI) Incentivized Testnet](https://blog.nucypher.com/come-and-stake-it-incentivized-testnet/?utm_source=p2peconomy), [P2P Validator](https://p2p.org/?utm_source=blog&utm_medium=economy&utm_campaign=NuCypher-monitoring) has collaborated with [NuCypher](http://www.nucypher.com) to provide an inexpensive and powerful [suite of self-hosted NuCypher node monitoring and alerting services](https://github.com/p2p-org/nucypher-monitoring) using Prometheus and Grafana. This suite is free and open-sourced so that anyone can make use of it to manage their NuCypher node infrastructure.

## The Need

The NuCypher Network is a decentralized network of nodes that uses proxy re-encryption to provide secrets management and dynamic access control services. The network facilitates end-to-end encrypted data sharing between parties without exposing plaintext data or private keys to the nodes.

NuCypher nodes are incentivized to maintain high uptime and availability to readily provide re-encryption services. Persistent downtime will cause nodes to forgo inflation rewards and policy fees. Therefore, identification and resolution of availability issues quickly is a requirement. This solution is aimed at those who independently set up and run the Worker according to the [NuCypher documentation](https://docs.nucypher.com/en/latest/guides/network_node/network_node.html), but who do not have enough experience to implement monitoring and alerting on their own. After successfully running a Worker node, the user should be able to check the state of their node and receive timely alerts about issues that need to be addressed immediately. 

## The Solution

Our goal was to provide a seamless setup, simple configuration and enable the user to obtain up-to-date information about their ongoing node operations and the broader NuCypher network. We implemented a Worker endpoint that provides various node metrics and a Grafana dashboard to allow users to visualize these metrics and assess the state of their node. 

![](https://i.imgur.com/sKbvmsz.png")

![](https://i.imgur.com/22nrHoR.png")


Metrics include:
* CPU / RAM / Disk / Network utilization
* Realtime data on node workload
* Account balances
* Staker information
* WorkLock status

Furthermore, alerts can be provisioned based on these metrics through the dashboard to send timely messages when notable issues arise. Notification mechanisms include Telegram bots, SMS, phone calls, and email notifications. Additional functionality is provided to include images within alert messages and to configure reminders.

![](https://i.imgur.com/rEOUYqG.png")

## Getting Started

To install Prometheus and run your Worker with the metrics endpoint activated, see https://docs.nucypher.com/en/latest/guides/network_node/ursula_configuration_guide.html#prometheus-endpoint.

To set up our monitoring suite, go to https://github.com/p2p-org/nucypher-monitoring, and follow the instructions.

> To file bug reports or feature requests, please create an issue on our Github. If you are feeling adventurous feel free to submit pull requests.

------

*Do not hesitate to ask questions in our [Telegram chat](https://t.me/P2Pstaking) or contact Alex via am@p2p.org. We are always ready to help and open for communication.*

------

# About P2P Validator

[P2P Validator](https://p2p.org/?utm_source=blog&utm_medium=economy&utm_campaign=NuCypher-monitoring) is a world-leading staking provider with the best industry security practices and proven expertise. We provide comprehensive due-diligence of digital assets and offer only top-notch staking opportunities. At the time of publishing, more than 40 million of USD value is staked with P2P Validator by over 1500 delegators across 15+ networks.

**Web:** [p2p.org](https://p2p.org/?utm_source=blog&utm_medium=economy&utm_campaign=nucypher-monitoring)

**Stake NU with us:** [p2p.org/nucypher](https://p2p.org/nucypher?utm_source=blog&utm_medium=economy&utm_campaign=nucypher-monitoring)

**Twitter:** [@p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:** [t.me/P2Pstaking](https://t.me/P2Pstaking)
