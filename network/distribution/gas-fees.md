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

Cascadia’s native token (CC) is used to pay for transactions and emitted as block rewards to validators.  CC can be locked into a vote-escrow contract in return for bCC.  On the Cascadia blockchain, gas rewards are initially split and distributed evenly by 1/3 between 3 parties: nProtocols, Validators, and bCC lockers that hold the vote-escrowed token (Figure 2).

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Cascadia has designed a new cooldown lock type, create cooldown lock, to return a portion of gas fees to select addresses, even if an address has not yet created a ve-lock. This adapted form allows `lock_bot` to establish a lock for other whitelisted addresses, enabling set incentives, per the specifications below:

<figure><img src="https://lh4.googleusercontent.com/kh0BZlc2RWONNjTjogq3192Riz7dHuOkibLb0SRT6h_pXM9BFjDoXIaoIOjobf-H6XLuNUUSp6WnSTXoBcFueJjCKXtJbSny1fozT2N3_vODvWS2K_-NPDzy60QDkcvWbvPSgAZ0ABYge38nG_H9d_0" alt=""><figcaption></figcaption></figure>

In practice, Cascadia can dynamically adjust the initial 1/3 distribution of either block rewards or gas fees based on feedback from stakeholders (nProtocols, Validators, and bCC holders) to align with environmental factors. This is the fundamental value proposition of cybernetics. Initially, this feedback process will be primarily conducted off-chain via standard governance processes, transitioning towards on-chain governance, with autonomous governance as the ultimate goal.
