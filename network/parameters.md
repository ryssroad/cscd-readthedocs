# Parameters

Cascadia has a well-defined set of parameters that outline rules for validators, ensuring a fair and efficient system for block production and decision-making.



**Staking**

| Denomination          | UTCC    | The denomination of staked tokens in Cascadia is UTCC, the native token of the network.                                                        |
| --------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Unstaking Time        | 21 Days | When a user decides to unstake their tokens, there is a set waiting period before they can be made liquid again.                               |
| Max Entries           | 7       | Delegators are limited to a maximum number of entries to ensure that the network remains decentralized.                                        |
| Historical Entries    | 10,000  | Cascadia stores a certain number of historical entries, which include information about past validator entries and other relevant data.        |
| Max Active Validators | 100     | Cascadia sets a maximum limit on the number of active validators in the network to ensure decentralization and prevent concentration of power. |



**Slashing**

<table data-header-hidden><thead><tr><th>Validator Rules</th><th>Value</th><th>Descripton</th><th data-hidden>Parameter</th></tr></thead><tbody><tr><td>Downtime Jail Duration</td><td>600 Seconds</td><td>Validators who fail to sign blocks during their designated slot will be penalized by being placed in jail for a set period of time.</td><td></td></tr><tr><td>Minimum Signed Blocks (per window)</td><td>50%</td><td>Validators are required to sign a minimum percentage of blocks during a signing window to maintain their active status.</td><td>Per Window</td></tr><tr><td>Signing Window</td><td>100</td><td>The signing window is the number of blocks considered when calculating a validator's minimum signed blocks.</td><td></td></tr><tr><td>Slash Fraction Double Sign</td><td>5/100</td><td>Validators who attempt to double-sign a block will be penalized by having a fraction of their stake slashed.</td><td></td></tr><tr><td>Slash Fraction Downtime</td><td>100/10,000</td><td>Validators who miss their signing slot and fail to sign a block will be penalized by having a fraction of their stake slashed.</td><td></td></tr></tbody></table>



**Distribution**

| Base Proposer Reward       | 1%   | Block proposers in Cascadia receive a base reward of 1% for their contributions to the network.                                                              |
| -------------------------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Bonus Proposer Reward      | 4%   | In addition to the base reward, block proposers can receive an additional reward of 4% as a bonus for their efforts in maintaining the network's operation.  |
| Community Tax              | 2%   | A portion of the rewards collected in Cascadia, currently set at 2%, is allocated toward community development.                                              |
| Withdrawal Address Enabled | True | Cascadia allows for the use of a separate withdrawal address to facilitate the withdrawal of rewards.                                                        |



**Governance**

| Quorum         | 33%    | For a vote to be considered valid in Cascadia's governance model, a minimum percentage of voting power is required to participate. |
| -------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| Threshold      | 50%    | To pass a proposal in Cascadia's governance model, a minimum percentage of favorable votes is required.                            |
| Veto Threshold | 33%    | In Cascadia's governance model, a proposal can be vetoed if a minimum percentage of "no" votes is reached.                         |
| Voting Period  | 2 Days | The duration of the voting period for a governance proposal in Cascadia is set at 2 days.                                          |



{% hint style="info" %}
These parameters can be found [here](https://validator.cascadia.foundation/parameters).
{% endhint %}
