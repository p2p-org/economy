# When will I start receiving my ADA rewards?

Many of our community members have been asking around when they could start receiving rewards from delegated stake. And the short answer might be as follows: **you will begin receiving staking rewards three entire epochs after the epoch during which you delegated your ADA.** But let’s take a closer look at the delegation cycle. 

---

## Delegation Cycle Explanation 
Below you can find a graph showing the delegation cycle on the [Cardano](https://cardano.org/) network. 
![P2P](https://i.imgur.com/ApO8ZLR.png)

First we need to determine a starting point. For example, `P2P` stake pool was registered on 11 August 2020. Thus, if you had delegated during the `210` epoch your stake would have been counted in the snapshot on the `210-211` epochs boundary. 
![P2P](https://i.imgur.com/PtU95mc.png)

Once the snapshot is taken, we have to wait for the current epoch to be finished so that the stake becomes **active.** In our case we are going to wait for the `212` epoch. 

During the `212` epoch the snapshotted stake becomes **active** and participates in the **block minting process** according to the Ouroboros consensus engine logic. 
![P2P](https://i.imgur.com/J5qywX6.png)

In the following `213` epoch, the rewards will be calculated properly according to the stake size of each delegator. 
![P2P](https://i.imgur.com/UqdyuXk.png)

Finally, you will be rewarded for your patience on the first day of the next epoch. In the `P2P` case it will be `214` epoch on August 28. 
![P2P](https://i.imgur.com/n03y6yW.png)


## Takeaways 
1. Cardano is a long term investment so you have to make a decision about delegation/redelegation with caution. 

2. You can terminate the delegation process at any moment by sending your funds from the staking wallet to a new wallet that wasn’t used for delegation. In this case you will not be rewarded for this epoch.

3. Once you make a change, for instance you added new funds to the staking wallet,  the added stake will go through the delegation cycle from the very beginning. 

4. Making change is a simple and safe process as any other normal transaction on the blockchain.



