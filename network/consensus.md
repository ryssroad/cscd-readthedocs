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

Cascadia introduces a novel consensus algorithm based on Byzantine Fault Tolerant Delegated Proof of Stake (BFT DPoS) to achieve decentralization, efficiency, and security.  This section explores the underlying mechanisms of BFT DPoS consensus, its advantages over traditional consensus mechanisms, and its application on the Cascadia blockchain.



**Introduction**

In recent years, blockchain technology has emerged as a promising solution for a wide range of applications, from financial services to supply chain management. However, the consensus mechanisms that underpin these systems have significant limitations, such as high energy consumption, slow transaction processing, and limited scalability.  To address these challenges, Cascadia adopts the BFT DPoS consensus algorithm, which combines the strengths of both Byzantine Fault Tolerance (BFT) and Delegated Proof of Stake (DPoS).

DPoS has been demonstrated to be trustworthy, safe, and efficient over the course of years of operation on various blockchains.  Cascadia is built on the foundations of Cosmos SDK architecture, thus inheriting the same traits as its predecessor.

The goal of DPoS is to reduce communication costs between nodes by indirectly participating in the consensus process.  In the DPoS consensus mechanism, the number of validators is fixed to lower the cost of communication among the validators.  An administrator chooses an algorithm that determines how to complete blocks with a limited number of validators when using the DPoS consensus mechanism.&#x20;

The flow of information is vitally important to blockchains, and even more so to Cascadia’s cybernetic systems.  Blockchain networks operate in an asynchronous environment and unanticipated communication failures may result in consensus discrepancy.  As a result, Cascadia employs the practical  Byzantine Fault Tolerance (pBFT) algorithm, a consensus algorithm that ensures the consistency of the consensus results among validators in the asynchronous communication environment.  Client (non-validator) nodes request transaction processing to replica (validator) nodes and receive a reply.  To verify the requested transaction, the replica nodes perform consensus between requests from a client and replies to a client.  The consensus process consists of three phases: 1. Pre-prepare, 2. Prepare, and 3. Commit

In contrast to PoW and PoS systems, Cascadia validators are not in direct competition with one another.  Instead, they are collaborating to create and verify fresh blocks.  The DPoS consensus enables Cascadia to confirm transactions with a \~99.9% confidence rate on average in just 1.5 seconds while degrading in a detectable manner that is nominal to recover from.  It is intended to optimize efficiency under the notional assumption of 100% honest nodes participating and having reliable network connections.



**Delegation and Validator Selection**

Token holders delegate their voting rights to a set of validators, who are responsible for validating transactions and maintaining the integrity of the blockchain.  The delegation process allows for a more decentralized network, while still ensuring efficient and secure consensus.  Validators are chosen based on the stake they hold or have delegated to them, with the top-ranked validators selected to participate in the consensus process.  This selection mechanism ensures that validators have the incentive to act honestly and maintain the security of the network.

Let n be the total number of validators in the network, and let `s_i` be the stake of validator `i`, where `i = 1, 2,..., n`.  Validators are ranked based on their stake, and the top m validators are selected to participate in the consensus process, where `m < n`.  The probability of being selected as a validator, `P(i)`, is proportional to the stake of validator i, such that:

`P(i) = s_i / Σ (s_j), for j = 1, 2,..., n`

The maximum number of active validators in the network is 100. This parameter ensures a balance between decentralization and efficiency in the consensus process.



**Byzantine Fault Tolerance**

The network can tolerate up to 1/3 of the participating validators being faulty or malicious.  As long as less than 1/3 of the validators are Byzantine, the network can reach consensus and maintain its security.  This property ensures the resilience of the blockchain against potential attacks or network failures.

Given the selected m validators, the network can tolerate f Byzantine validators, where f = floor(m/3).  Therefore, the network can withstand f malicious validators while still reaching consensus.



**Block Proposal and Voting**

Block proposal and voting involves a designated proposer creating a new block and broadcasting it to the other validators.  Validators then vote on the proposed block in two rounds: the pre-vote and the pre-commit phase.  In the pre-vote phase, validators indicate their support for the proposed block, while in the pre-commit phase, they confirm their final decision.  If a block receives at least 2/3 of the votes in both phases, it is committed to the Cascadia blockchain.

Let `V_pre-vote` and `V_pre-commit` represent the sets of validators that vote for a block in the pre-vote and pre-commit phases, respectively.  A block is committed to the blockchain if and only if the following conditions are met:

`|V_pre-vote| ≥ 2 * m / 3 and |V_pre-commit| ≥ 2 * m / 3`

This two-phase voting process ensures that validators reach a consensus on the validity of a block before adding it to the blockchain, enhancing the security and stability of the network.



**Distribution**&#x20;

The base proposer reward is set at 1%, with an additional bonus proposer reward of 4%.  This encourages validators to actively participate in the block proposal process.



**Incentives and Penalties**

The BFT DPoS consensus incorporates incentives and penalties to encourage honest behavior and discourage malicious actions.  Validators and their delegators are rewarded for participating in the consensus process through block rewards and transaction fees.  However, if a validator is found to be maliciously or negligently acting, their stake (and the stake of their delegators) can be slashed, resulting in a loss of tokens.  This penalty system provides a strong deterrent against malicious actions and ensures the long-term security and stability of the blockchain.

Let `R` be the total rewards distributed per block, and let `r_i` be the reward received by validator `i`, where `i = 1, 2,..., m`.  The reward for each validator is proportional to their stake, such that:

`r_i = R * (s_i / Σ (s_j)), for j = 1, 2,..., m`

In the event of malicious behavior, a slashing function can be applied to the stake of the malicious validator and their delegators.  Let `P_slash` be the slashing penalty percentage, and let `L_i` be the loss incurred by validator i due to slashing, where `i = 1, 2,..., m`.  The loss due to slashing is calculated as:

`L_i = P_slash * s_i`

This approach addresses the limitations of traditional consensus mechanisms, such as high energy consumption, slow transaction processing, and limited scalability, while maintaining decentralization, efficiency, and security.



**Staking**

At Cascadia, staking is denominated in the native token.  The unstaking time is 21 days, allowing delegators to reclaim their tokens after this period.  Delegators can have a maximum of 7 validator entries, and the system stores up to 10,000 historical entries.

\
**Slashing**

Validators are subject to slashing penalties for downtime and double-signing.  The downtime jail duration is 600 seconds, with a minimum signed-per-window requirement of 50% within a 100-block signing window.  The slash fraction for double-signing is 5/100, while the slash fraction for downtime is 100/10,000.
