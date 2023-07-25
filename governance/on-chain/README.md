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

# On-Chain

This guide provides an overview of Cascadia's on-chain governance system, focusing on vote-escrowed CC as the determining factor for each account's voting power. This section covers various aspects of the governance system, such as proposal submission, voting periods, quorum requirements, pass thresholds, and veto thresholds. Additionally, it clarifies the voting options available and the criteria for determining the outcome of a governance proposal.

**Participation Requirements**&#x20;

To engage in Cascadia's on-chain governance, an account must hold bCC, a unique ERC20 implementation that defines an account's voting power.  It is non-transferable and can only be acquired by locking CC.

{% hint style="info" %}
In Cascadia, "locking" is more aptly referred to as "alignment".  This terminology better reflects the nature of the locking process within the Cascadia ecosystem.
{% endhint %}

**Governance Features**&#x20;

bCC holders can vote on proposals on a 1 token, 1 vote basis. The current module supports these features:

1. Proposal submission: Users with a specific bCC balance can submit proposals, initiating the voting period.&#x20;
2. Vote: During the voting period, participants can vote on proposals.

**Governance Parameters**&#x20;

The voting period spans 14 days, and a quorum is achieved when at least 40% of the voting power participates. The pass threshold is 50% of participating voting power. Participants can choose from Yes, No, or Abstain voting options during the voting period, and may change their vote before the period ends.

**Criteria for Approving Governance Proposals**&#x20;

Four factors determine the outcome of a governance proposal.

1. A quorum requires at least 40% of the network's total voting power (based on bCC balances) to participate;
2. Over 50% of participating voting power must support a Yes vote by the end of the 14-day voting period; and
3. The same criteria apply to submit and determine the outcome of all proposal types.

**Establishing Quorum**&#x20;

Voting power, whether supporting Yes, No, or Abstain, contributes to the quorum.  A quorum is necessary for a governance proposal to be approved.

**Who Can Submit a Proposal**

Every holder of the bCC token can submit proposals.

**How to Submit a Proposal**

Submitting a proposal requires at least 1 bCC token. The proposal should mention the voting period and outline the proposed change's purpose, potential impacts, and any other relevant details.

**Considerations for Proposal Submission**

Before submitting a proposal, participants should consider the potential impacts on the network, both immediate and long-term. Contributors should encourage thorough discussion and deliberation before formal proposal submission. Proposers should also note that they may need to hold a certain number of bCC during the proposal process, as a demonstration of their commitment to the initiative.

**Voting Period**

The voting period for each proposal spans 14 days, giving everyone ample time to review the details, deliberate, and cast their votes. During this period, bCC holders may cast their vote with the aforementioned options. Voters can change their decision any time before the voting period concludes.

**Voting Power and Tallying**

The voting power of each account is proportional to the amount of bCC it holds. More specifically 1 bCC = 1 vote. The total voting power for a proposal equals the sum of bCC participating in the vote. When the voting period ends, the votes are tallied. The decision, whether it is approved or rejected, depends on the majority vote, keeping in mind the necessary quorum and veto thresholds.

**Effect of Proposal Outcome**

The outcome of the vote can result in the implementation of the proposed changes or maintaining the status quo, depending on the decision. A successful proposal leads to the execution of changes as detailed in the proposal, while a failed proposal retains the current conditions.

{% hint style="info" %}
Cascadia's on-chain governance is designed to evolve over time. The parameters above are initial settings and may be updated as part of our evolving governance process.
{% endhint %}
