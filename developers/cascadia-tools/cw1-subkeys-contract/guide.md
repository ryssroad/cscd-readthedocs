# Guide

**Step 1: Initialization**

You need to determine if you want the contract admin rights to be alterable post-creation.

If you opt for this, remember that should you desire a different admin address later, a fresh contract will be necessary.

{% hint style="info" %}
You can designate multiple admin addresses by using the provided add (+) function.
{% endhint %}



**Step 2: Contract Queries**

From the Cascadia dashboard, it's feasible to obtain data from any CW1 contract. Also, all queries mandate the CW1 contract address as a foundational input.

Queries:

<table data-header-hidden><thead><tr><th width="158.33333333333331">Functionality</th><th width="357">Description</th><th>Required Input</th></tr></thead><tbody><tr><td>Allowance</td><td>The limit set by the admin for another address concerning sending, transferring, or redelegating.</td><td>Spender address</td></tr><tr><td>All Allowances</td><td>Overview of all set limits by the admin.</td><td>-</td></tr><tr><td>Permissions</td><td>A record of rights assigned by the admin to a specific address.</td><td>Address under scrutiny</td></tr><tr><td>All Permissions</td><td>A comprehensive list showcasing all addresses alongside their respective permissions.</td><td>-</td></tr><tr><td>Can Execute</td><td>Verifies an address's capability to run a specific message.</td><td>Refer to Execute segment</td></tr></tbody></table>



**Step 3: Execution Commands**

You can find a list of possible messages below.



**Send:**

```
bank: {
  send: {
    from_address: messages.contractAddress,
    to_address: wallet.address,
    amount: [coin(1000000, 'cascadiatoken')],
  },
}
```



**Delegate**:

```
staking: {
  delegate: {
    validator: 'cascadiavaloperXYZ',
    amount: coin(1000000, 'cascadiatoken'),
  },
}
```



**Undelegate**:

```
staking: {
  undelegate: {
    validator: 'cascadiavaloperXYZ',
    amount: coin(1000000, 'cascadiatoken'),
  },
}
```



**Redelegate**:

```
staking: {
  redelegate: {
    src_validator: 'cascadiavaloperXYZ',
    dst_validator: 'cascadiavaloperABC',
    amount: coin(1000000, 'cascadiatoken'),
  },
}
```



<table data-header-hidden><thead><tr><th width="223.33333333333331">Functionality</th><th width="508">Description</th></tr></thead><tbody><tr><td>Freeze*</td><td>For contracts set as ''Mutable'', admins can lock the contract, halting the addition of fresh admin entities.</td></tr><tr><td>Update Admins</td><td>Introduce a new set of admins, replacing pre-existing ones.</td></tr><tr><td>Increase Allowance</td><td>Boost the spending limit of an address, contingent on the contract's current balance.</td></tr><tr><td>Decrease Allowance</td><td>Scale down an address's allowance according to the contract balance.</td></tr><tr><td>Set Permissions*</td><td>Assign fresh permissions to an address.</td></tr></tbody></table>

{% hint style="info" %}
Actions marked with an asterisk (\*) are strictly admin-exclusive.
{% endhint %}

Following every execution, a transaction hash will be presented for your reference.
