---
title: "Introduction to CyberWay"
description: "CyberWay - blockchain for applications"
date: 2019-08-15
thumbnail: 'https://i.ibb.co/hCPS7Ps/1240x698.png'
heroImage: 'https://i.ibb.co/hCPS7Ps/1240x698.png'
layout: Post
category:
  - cyberway
authors:
  - MarinaGureva
company:
 - cyberway
---

Introduction
============

Since the development of the first blockchain database named “Bitcoin”, 
complex transaction behaviour was a “Holy Grail” for people
wondering how they could pay, bet, play, and even order pizza with such
assets.

The first complex transaction logic implementation was made available
right in “Bitcoin” with a stack virtual machine providing a limited set
of operations for the end-user to make some fun with it. Fine example is
an Omni-layer built on top of the operations set, which end-user
intention is to provide a creation and usage of the custom user-defined assets. 
Such a system successfully fulfilled contemporary requirements for liquid asset 
transfer. Unfortunately, such an application logic usage rapidly overflowed the
throughput available, so no mass adoption happened.

Another attempt to provide the customizable complex transaction
behaviour was made with creation of “Ethereum”, which provided some 
created from scratch programming language called “Solidity” for creation of 
even more complex application logic, hoping it would not overflow the database 
throughput. Obviously this lead to another failure. Primal language and naive 
database architecture understanding did not survive the reality check - in 2017 
the protocol was literally down with CryptoKitties hype.

The scalability troubles got up again, so another popular solution was
rapidly proposed. It’s name was EOS. The solution was to split the
computable transaction complex behaviour and to process it with the set
of cluster nodes, which were called “Block producers”. This lead to the
entrustment of an enourmous responsibility to these “Block producers”.
They were now not only about data storage providers, but also
computation providers. Now these guys not only store and process your
data, but they even define the way your transaction behaves itself,
define if they allow such a transaction to be written or not.
Futhermore, such an “improvement” lead to the unacceptable database node
hardware requirements, which made the support truly awful. Moreover such
a split was not enough for building production-ready applications - who
would like to find out if the upvote transaction, which was even payed
for, was at first queued and then rejected?

You have something to propose?
------------------------------

Yeap. The following blog post series is about the CyberWay
(<https://cyberway.io>) - improved and refactored EOS fork.

Proposal
========

So what is CyberWay particularily about?

EOS-compatibility
-----------------

First of all the backward compatibility is held. The code contains most
of the tolerable EOS parts, but excludes the awful ones. So-called
“Smart Contracts” API backward compatiblity is held too, but the insides
have changed. That means every EOS application could easily become the
CyberWay-based one and vice versa. Enough of that. Next.

Bandwidth
---------

EOS’s bandwidth distribution is closely related to the amount of asset
the particular user owns. Furthermore, it requires for the user to hold
the asset to be available for the usage at any time. That means the
asset becomes a highly valuable, but also it becomes the non-available
for the newcomers one. So no newcoming applications are welcomed to be
built with EOS.

Striving to eliminate these inconveniences Cyberway introduces some
changes.

The bandwitdh accounting is split to the couple of categories:

1.  Priority-based bandwidth allows a user to get required computational
    facilities according to the amount of core-asset available.

2.  Shared bandwidth supplies users with the unused computational power
    according to the particular user activity.

State Storage
-------------

EOS’s state storage is extremely unreliable and does not ensures that
data is saved and restored after restart correctly. Futhermore EOS does
not provide any convenient API, but supposes the data structure stored
inside would be complex.

CyberWay solves these troubles. CyberWay uses the external DBMS for the
state storage, which means the particular developer favourite query
language can be used and the external well-designed replication and
clusterisation mechanisms, done by real engineers and scientists, are
also about to reduce the hardware costs and make life easier.

Event Engine
------------

Because of the storage internals being factored out the separate
service, the additional transaction contents-based event engine
implementation is required. It is now impossible to alert the CyberWay
executable from the various database if something happened or not, just
like it was in EOS. Monitoring-purposed event engine, implemented as a
part of updateable application, takes back the ability to track changes
coming with every transaction, even if the data storage is completely
outside.

Virtualization
--------------

Just like EOS, CyberWay requires for the transaction behaviour to be
updated easier, than updating the whole cluster software. That is why
the WebAssembly engine is used for the virtualization purposes and with
C++ as primary language for the application development.

Separation
==========

Why don’t just patch EOS?

Several troubles are about the data itself, and not the code:

1.  EOS’s architecture made the memory quant an expensive one: according
    to the <https://eosrp.io> the cost of such a memory quant fluctuates
    from \$0.2 to \$0.5. That means any transaction-intensive
    application (e.g. some social applications) with even a quite small
    amount of active users (e.g. 2000-3000) would take at least 400MB
    per week, which would cost up to \$200,000.

2.  EOS’s custom transaction behaviour is stored inside the huge
    hash-table allocated over a shared memory and the access is provided
    with an interface, based on quite sofisiticated executable logic,
    which also costs.

    The obvious solution - to make a cache service and process the data
    all inside it - is also quite a task because:

    1.  The so-called “Constitution” of EOS defines the largest time
        interval available for the unused data to be stored with the
        same ownership as 3 years. This is quite unacceptable with some
        kind of applications (e.g. social ones) demanding data
        availability from the very beggining, but the changes are hard
        to make because lots of other application types are perfetcly
        fine with this.

    2.  EOS is made to produce replication packages as fast as it can -
        about half of a second. Such a frequency is fine for marketing
        purposes, but it significally reduces the complexity of custom
        transaction logic. This is also unacceptable.

3.  Reduced amount of validators - only 21, and no significant increase
    is expected because of EOS protocol restrictions.

4.  Censorship availability for validators implemented right in the
    protocol core.

Applications
============

Applications are welcomed to use the following.

Shared Bandwidth
----------------

Shared bandwidth sets a limit for the user activity based on its’ staked
asset amount, but no less than some basic threshold. This is required to
prevent spam to database from the newcomers, and redistribute more
computational resources to the succesful application developers.

Shared bandwidth is accounted separately for the network, RAM and CPU
usage.

Coming to accounting - this is done with particular application
bandwidth balance, which shares the convenient part for the user
performing the transaction. That is why this is called “Shared”
bandwidth. The application is a multisignature account, which requires
at least one additional signature from the particular user, for its’
bandiwidth to be used. 

This type of bandwidth allows CyberWay to provide applications 
with free on-boarding of users at early stages via CyberWay Acceleration Program. 
Later successful application could get CYBER tokens within Acceleration Program
from special fund.

Priority-Based Bandwidth
------------------------

Priority-based bandwidth is required for the user to surely write the
transaction. It is formed with the amount of core asset staked by the
particular user and guarantees the transaction gets written right at
next replication time. The whole amount of staked core asset forms the
bandwidth market.

Each account gets a share from the whole bandwidth market according to
the amount of core asset the account has staked. Considering the case
some user owned and staked the significant part of the whole bandwidth
supply means the reduction of the resources available for other users.
This is definitely not something requiring applications want.

That is why CyberWay introduces the prioritization of the bandwidth. That
means the bandwidth gets split to a couple of categories:

1.  Guaranteed bandwidth, which works exactly as EOS’s one.

2.  Priority bandwidth, which is defined according to the particular
    account priority.

How do account earn the priority?

There are couple of ways:

1.  Perform less transactions using the currently available guaranteed
    bandwidth. The priority lowers as more transactions gets put inside
    with a single user.

2.  Stake more core asset.

The guaranteed/prioritized bandwidth split ratio is set by the cluster
validators.

Memory Rent
-----------

Cluster RAM is something the applications require to work. In contrast to EOS,
CyberWay supposes the RAM to be rented from so-called block
producers, but not to be owned. The rules are the following:

-   Every block producer sets a price for 1Kb memory per month. The
    price begins from the median price value across all block producers.

-   Users place their orders for some particular memory amount rent per
    month.

-   The order is recognized as emplaced for a week, after that it
    gets evaluated in case the cluster-wide demanded memory is lower than
    the amount of proposed one.

-   In case the proposed amount of memory is lower than demanded,
    proposed memory gets auctioned.

In case the memory rent time is up, but there is still some user data
stored inside, the archive operation is introduced. Block producers are
in charge of initiating such an archivation and the restore is available
for the user for the price median-valued among block producers.

DBMS-based State Storage
------------------------

Inspite of existing so-called “blockchain” databases, CyberWay does not
intend to implement the database management software and uses the
external DBMS as a state storage for more reliability. For now, only
MongoDB is available, but in case of requirements, more are coming. Such
a configuration considered to be troublesome for managing, but more
reliable in long term.

Embedded state storage is also available in CyberWay. RocksDB is used
for the in-memory and in-daemon storage management component that is faster than
MongoDB.

Event Engine
------------

As the state storage engine is incapsulated and factored out of
the controller daemon, the event engine is implemented as a helper
application, syncronizing and managing the data in external storages.

The input of such an application is a transaction set, each of which
gets registered as “processed” and only after this the data are
unpacked to state storage.

Such an approach allows to make sure the routine data operations are
processed as required and to split the data managing daemon to
single-responsibility micro-services.

Domain Names
============

Every created account is not identified with a key as other
databases do, but it gets a unique 8 byte identifier encoded in base32.
Also a human-readable 63 byte length unique names are available for the
assignment for every user. In case of the amount of such names is
greater than one, it gets charged and called a “Domain Name”.

Every domain name can be auctioned from base protocol or created by
owner of a lower-level domain name. Domain names are transferable and
reassignable. Therefore, a need for conversion between a domain name and account
identifier gets satisfied with a newly introduced sufficient mechanism
as much as need for domain transactions. Domain transactions are
transactions which get applied to the data only related to the
particular domain-name/application.

Protocol Properties
===================

Protocol properties are also got changed comparing to EOS’s ones.

Block Generation
----------------

First of all, block generation time is increased for achieving more
stable node replication. EOS’s 0.5 second block replication time is fine
for most application in case of all the nodes are located in the same
datacenter. But for truly distributed protocol, this requires to be
increased due to increased network latency. CyberWay supposes the
block replication time to be 3 seconds.

Block Producers
---------------

Block producers are the key members of a protocol. They keep the
database safe and consistent and get rewarded for that.

Inspite of EOS’s 21 default block producers, in CyberWay the number of block producers is to 
be increased up to 101 in the future. This is required for more decentralization to
be achieved.

Consensus Algorithm
-------------------

CyberWay consensus algorithm is heavily inspired by Tezos’ and Cosmos’ one. 
So, active users are rewarded for voting and non-active users are punished for not voting.

Every account is allowed to vote for several validators with staked tokens. 

Block producer’s weigh is determined as follows: 
w = m / sqrt(S), where m is a number of votes for any particular candidate, 
S is a total number of votes for any particular candidate (or number of stakes tokens as 1 vote is 1 token)   

A particular block producer receives a reward from the emission 
and redistributes a share of it among his supporters. 
In case of misbehavior, e.g. a block omission, the block producer as well as his supporters are fined.
The staked tokens are burned. This novelty makes block producers more responsible, 
and voters more careful and thoughtful.

The block producers get a share of emission. The share depends on the total amount of staked tokens. 
The more tokens are staked, the less inflation is. 
Thus, the CyberWay has in-built incentives for users to participate in governance via voting. 
Moreover, the passive users are diluted as they do not get any rewards from validators.  

What if some user considers another user to understand better, which
block producer is the best service provider? This gets covered
by CyberWay with a proxy mechanism which ensures that some user could delegate
his own assets to another user called “Proxy”. The proxy user gets fees for its service.

Censorship
----------

In contrast to EOS, CyberWay completely removes any inequality between the users.
There are no privileged accounts, no so-called “Constitution”,
no blacklists.

Workers
-------

Workers are the mechanism first introducted in BitShares. These are
users, who get their issuance share for making improvements for the
protocol. The improvement can be registered and referenced by any user,
particular improvement to resolve is selected via voting by validators.

Conslusion
==========

CyberWay is one more fork of EOS, specified to handle more complex
applications with more decentralization available. Workers are
considered to be the most powerful tool for decentralized protocol
improvements. The scalability and performance CyberWay introduces is
fine enough for running complex social applications or financial service apllications
or gaming applications. The absence of censorship and priveledged accounts 
makes CyberWay even more decentralized, which is coming in the next blog post.

