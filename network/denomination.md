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

# Denomination

**CC** is our native token, used for all major transactions and interactions in Cascadia. It also plays a crucial role in the blockchain's overall structure and governance.

**bCC** is our governance token, obtained by those who align their CC tokens. Holders of bCC gain the right to vote on key decisions in Cascadia's network.

{% hint style="info" %}
Our bCC contract is written in Vyper v0.2.7, hence, free from the malfunctioning reentrancy locks issue known in Vyper v0.2.15, v0.2.16, and v0.3.0. \
For more details, see [Vyper's tweet](https://twitter.com/vyperlang/status/1685692973051498497).
{% endhint %}

**tCC** is our testnet token, utilized to ensure Cascadia's robustness and reliability through various testing processes prior to mainnet operations.

**aCC** is the smallest denomination of Cascadia's native token used for micro-level transactions.

{% hint style="info" %}
Unlike the _u_ (micro) denotation, Cascadia utilizes _a_ to signify micro-level transactions, promoting increased precision and system adaptability.
{% endhint %}

**Atto** is a unit prefix in the metric system. It denotes a factor of 10^-18, or one quintillionth. This means that 1 CC can be divided into 1 quintillion (1,000,000,000,000,000,000) aCC.

**Why it matters:** The use of 'atto-' allows for a high degree of precision in transactions involving CC. This precision is essential for certain applications that might require operations with minuscule amounts of tokens.
