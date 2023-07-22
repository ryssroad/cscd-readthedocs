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

# Gas Fees

Cascadia’s native token (CC) is used to pay for transactions and emitted as block rewards to validators.  CC can be locked into a vote-escrow contract in return for veCC.  On the Cascadia blockchain, gas rewards are initially split and distributed evenly by 1/3 between 3 parties: nProtocols, Validators, and veCC lockers that hold the vote-escrowed token (Figure 2).

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

For Cascadia to return a share of gas fees, even if an address has not yet created a ve-lock, a new cooldown lock type has been created, `create_cooldown_lock`, an adapted form that allows allows whitelisted addresses (lock\_bot) to create a lock for other addresses, which in turn enables set incentives, as per the specifications below.

<figure><img src="https://lh4.googleusercontent.com/kh0BZlc2RWONNjTjogq3192Riz7dHuOkibLb0SRT6h_pXM9BFjDoXIaoIOjobf-H6XLuNUUSp6WnSTXoBcFueJjCKXtJbSny1fozT2N3_vODvWS2K_-NPDzy60QDkcvWbvPSgAZ0ABYge38nG_H9d_0" alt=""><figcaption></figcaption></figure>
