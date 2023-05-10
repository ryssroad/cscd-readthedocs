# Governance

This guide provides an overview of Cascadia's on-chain governance system, focusing on the role of vote-escrowed CC as the determining factor for each account's voting power.  This section covers various aspects of the governance system, such as proposal submission, voting periods, quorum requirements, pass thresholds, and veto thresholds.  Additionally, it clarifies the voting options available and the criteria for determining the outcome of a governance proposal.



**Participation Requirements**&#x20;

To engage in Cascadia's on-chain governance, an account must hold veCC.  veCC is an unique ERC20 implementation that defines an account's voting power.  It is non-transferable and can only be acquired by locking CC.



**Governance System Features**&#x20;

veCC holders can vote on proposals on a 1 token, 1 vote basis.  The current module supports these features:

1. Proposal submission: Users with a specific veCC balance can submit proposals, initiating the voting period.&#x20;
2. Vote: During the voting period, participants can vote on proposals.



**Governance Parameters**&#x20;

The voting period spans 14 days, and a quorum is achieved when at least 40% of the voting power participates. The pass threshold is 50% of participating voting power, while the veto threshold is 33.40% of participating voting power.  Participants can choose from 'Yes,' 'No,' 'Abstain,' or 'NoWithVeto' voting options during the voting period, and may change their vote before the period ends.



**Criteria for Approving Governance Proposals**&#x20;

Four factors determine the outcome of a governance proposal.

1. A quorum requires at least 40% of the network's total voting power (based on veCC balances) to participate;
2. Over 50% of participating voting power must support the 'Yes' vote by the end of the 14-day voting period;
3. Under 33.4% of participating voting power should back 'NoWithVeto' by the end of the 14-day voting period; and
4. The same criteria apply to submit and determine the outcome of all proposal types.



**Establishing Quorum**&#x20;

Voting power, whether supporting 'Yes,' 'Abstain,' 'No,' or 'NoWithVeto,' contributes to the quorum.  A quorum is necessary for a governance proposal to be approved.

{% hint style="info" %}
Due to Cascadia's cybernetic design, on-chain governance is an evolving process.  The above parameters are initial settings, but may be further changed through the governance process.
{% endhint %}
