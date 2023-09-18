# CW1 Subkeys Contract

CW1 is a protocol for proxy contracts within the Cascadia ecosystem. It enables one central contract to secure assets or privileges, further disbursing rights to secondary contracts.

A typical scenario involves multiple addresses collaboratively leveraging an account. A primary address might deposit assets, subsequently assigning allowances to sub-accounts. These sub-accounts can:

* Execute transfers
* Initiate withdrawals
* Delegate and undelegate
* Execute redelegations

While sub-accounts operate within these allowances, an administrative entity maintains overarching control. This includes:

* Modifying allowance thresholds,
* Dictating permissible actions for addresses,
* Managing admin rights (only feasible if the contract is mutable).

{% hint style="info" %}
CW1 contract has the ability to facilitate transactions of non-transferrable tokens, such as staked or voting.
{% endhint %}
