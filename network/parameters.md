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

# Parameters

Cascadia has a well-defined set of parameters that outline rules for validators, ensuring a fair and efficient system for block production and decision-making.

{% hint style="info" %}
Parameters are also listed on Cascadia's [validator explorer](https://validator.cascadia.foundation/parameters).
{% endhint %}



**Staking**

<table data-header-hidden><thead><tr><th width="223">Rules</th><th width="103.33333333333331">Value</th><th>Description</th></tr></thead><tbody><tr><td>Denomination</td><td>UTCC</td><td>The denomination of staked tokens in Cascadia is UTCC, the native token of the network.</td></tr><tr><td>Unstaking Time</td><td>21 Days</td><td>When a user decides to unstake their tokens, there is a set waiting period before they can be made liquid again. </td></tr><tr><td>Max Entries</td><td>7</td><td>Delegators are limited to a maximum number of entries to ensure that the network remains decentralized. </td></tr><tr><td>Historical Entries</td><td>10,000</td><td>Cascadia stores a certain number of historical entries, which include information about past validator entries and other relevant data. </td></tr><tr><td>Max Active Validators</td><td>100</td><td>Cascadia sets a maximum limit on the number of active validators in the network to ensure decentralization and prevent concentration of power.</td></tr></tbody></table>



**Slashing**

<table data-header-hidden><thead><tr><th width="181.33333333333331">Validator Rules</th><th width="122">Value</th><th>Descripton</th><th data-hidden>Parameter</th></tr></thead><tbody><tr><td>Downtime Jail Duration</td><td>600 Seconds</td><td>Validators who fail to sign blocks during their designated slot will be penalized by being placed in jail for a set period of time.</td><td></td></tr><tr><td>Minimum Signed Blocks (per window)</td><td>50%</td><td>Validators are required to sign a minimum percentage of blocks during a signing window to maintain their active status.</td><td>Per Window</td></tr><tr><td>Signing Window</td><td>100</td><td>The signing window is the number of blocks considered when calculating a validator's minimum signed blocks.</td><td></td></tr><tr><td>Slash Fraction Double Sign</td><td>5/100</td><td>Validators who attempt to double-sign a block will be penalized by having a fraction of their stake slashed.</td><td></td></tr><tr><td>Slash Fraction Downtime</td><td>100/10,000</td><td>Validators who miss their signing slot and fail to sign a block will be penalized by having a fraction of their stake slashed.</td><td></td></tr></tbody></table>



**Distribution**

<table data-header-hidden><thead><tr><th width="181">Parameters</th><th width="102.33333333333331">Value</th><th>Description</th></tr></thead><tbody><tr><td>Base Proposer Reward</td><td>1%</td><td>Block proposers in Cascadia receive a base reward of 1% for their contributions to the network. </td></tr><tr><td>Bonus Proposer Reward</td><td>4%</td><td>In addition to the base reward, block proposers can receive an additional reward of 4% as a bonus for their efforts in maintaining the network's operation. </td></tr><tr><td>Community Tax</td><td>2%</td><td>A portion of the rewards collected in Cascadia, currently set at 2%, is allocated toward community development.</td></tr><tr><td>Withdrawal Address Enabled</td><td>True</td><td>Cascadia allows for the use of a separate withdrawal address to facilitate the withdrawal of rewards.</td></tr></tbody></table>



**Governance**

<table data-header-hidden><thead><tr><th width="168.33333333333331">Parameters</th><th width="107">Value</th><th>Description</th></tr></thead><tbody><tr><td>Min. Deposit</td><td>6102</td><td>For a proposal to be submitted, a user needs a minimum of 6102 bCC balance.</td></tr><tr><td>Voting Period</td><td>2 days</td><td>The duration of the voting period for a governance proposal in Cascadia is set at 2 days.</td></tr><tr><td>Quorum</td><td>33%</td><td>The minimum percentage of votes required for a proposal to be considered valid. </td></tr><tr><td>Threshold</td><td>50%</td><td>The threshold is the minimum percentage of "yes" votes needed for a proposal to pass, assuming that the quorum has been met.</td></tr></tbody></table>
