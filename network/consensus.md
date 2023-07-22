---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Consensus

Although there are several consensus algorithms that could result in the same ordering of transactions, DPoS has been demonstrated to be trustworthy, safe, and efficient over the course of years of operation on various blockchains.  Cascadia is built on the foundations of Cosmos SDK architecture, thus inheriting the same traits as its predecessor.

The goal of DPoS is to reduce communication costs between nodes by indirectly participating in the consensus process.  In the DPoS consensus mechanism, the number of validators is fixed to lower the cost of communication among the validators.  An administrator chooses an algorithm that determines how to complete blocks with a limited number of validators when using the DPoS consensus mechanism.&#x20;

The flow of information is vitally important to blockchains, and even more so to Cascadia’s cybernetic systems.  Blockchain networks operate in an asynchronous environment and unanticipated communication failures may result in consensus discrepancy.  As a result, Cascadia employs the practical  Byzantine Fault Tolerance (pBFT) algorithm, a consensus algorithm that ensures the consistency of the consensus results among validators in the asynchronous communication environment.  Client (non-validator) nodes request transaction processing to replica (validator) nodes and receive a reply.  To verify the requested transaction, the replica nodes perform consensus between requests from a client and replies to a client.  The consensus process consists of three phases: 1. Pre-prepare, 2. Prepare, and 3. Commit

In contrast to PoW and PoS systems, Cascadia validators are not in direct competition with one another.  Instead, they are collaborating to create and verify fresh blocks.  The DPoS consensus enables Cascadia to confirm transactions with a \~99.9% confidence rate on average in just 1.5 seconds while degrading in a detectable manner that is nominal to recover from.  It is intended to optimize efficiency under the notional assumption of 100% honest nodes participating and having reliable network connections.



**Phases**

The two phases of the DPoS algorithm are scheduling production and selecting a group of block producers.  The election process ensures that stakeholders hold the reins of power because they stand to lose the most if the network is not functioning properly.  On a minute-by-minute level, elections have no bearing on how consensus is reached.



**Regular Operation**

Block makers typically alternate manufacturing a block every few seconds.  This will result in the longest chain conceivable.  A block producer cannot generate a block during a different time period than the one they are scheduled for.

\
**Minority Fork**

A minority fork can be produced by up to 1⁄3 of the nodes acting maliciously or malfunctioning.  The majority fork will produce 2 blocks every X seconds, whereas the minority fork will only produce 1 block every X seconds.  The minority will never last longer than the honest 2⁄3 majority.



**Double Production by Disconnected Minority**

The minority can try to create an infinite number of forks, but each of them will have a shorter length than the chain of the majority because the minority can only build the chain more slowly than the majority.



**Network Dispersion**

The network could split, in which case no fork would have a majority of the block producers.  The greatest minority in this situation will end up with the longest chain.  Smaller minorities will inevitably gravitate toward the longest chain when network connectivity is restored, and clear consensus will be reinstated.

It is possible for there to be 3 forks where the two longest forks are the same length.  When they rejoin the network, the producers from the third (smaller fork) will decide who wins the tie.  Since there are an odd number of producers, a tie cannot be sustained for very long. \


**Minority Production**

Minority B produced two or more substitute blocks during their time slot in this scenario.  Any of the alternatives developed by B may be used as a foundation by the producer (C), who is slated to come after B.  All nodes who chose B will switch forks at this point, making the chain the longest.  They will never be a part of the longest chain for more than one round, regardless of how many different blocks a small percentage of bad producers try to spread.



**Final Revocable Block**

It is feasible for several forks to continue to grow for a considerable amount of time in the case of network fragmentation.  The longest chain will ultimately prevail, but watchers need to be assured that a block is unquestionably a part of the chain that is expanding the fastest.  If 2⁄3 of the producers are being truthful, block B has been confirmed by C and A, which indicates 2/3 + 1 confirmation, and we can thus conclude that no other chains could possibly be longer.



**Producer Rotation under Determinism**

The above examples contemplate a round-robin scheduling of block producers.  For every N blocks, where N is the number of producers, the set of block producers is actually shuffled.  Because of the randomization, ties could eventually break whenever there are numerous forks with identical producer counts, and block producer B does not always disregard block producer A.



**Corruption of the Majority of Producers**

If the majority of producers turn corrupt, they will be able to create an infinite number of forks, each of which will seem to be moving forward with a 2⁄3  majority.  In this situation, the longest chain algorithm replaces the last irreversible block method.  The longest chain will be chosen by the majority of the remaining honest nodes, who will determine which chain to approve.  Because the stakeholders would eventually vote to replace these producers, this kind of behavior would not persist long.

\
**Delegation**

The validation of the blocks is delegated to several delegates by stakeholders in Cascadia’s DPoS consensus.  These delegates, also known as witnesses, protect Cascadia on behalf of the stakeholders and are in charge of fostering network consensus when new blocks are being validated.  The delegates that will submit a specific proposal to the stakeholders in order to secure their votes are chosen by the stakeholders via a democratic voting system.  The amount of Cascadia tokens that network users have locked up in their wallets determines the voting power, but the rewards for a successful block validation are split between agents who participate in the network, as described below.

As stakeholders vote based on a candidate’s reputation, DPoS enables improved block validator screening.  Stakeholders have the right to dismiss or substitute alternative witnesses at any moment for unruly or ineffective delegates.
