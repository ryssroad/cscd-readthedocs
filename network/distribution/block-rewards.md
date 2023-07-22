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

# Block Rewards

Cascadia divides validator incentives (block rewards) among validators, veCC holders, and nProtocols in three equal shares (Figure 1).  This token design choice not only impacts the platform’s users and what they can accomplish within it, but also the underlying functioning of the blockchain itself and the economic incentives that drive the evolution of our ecosystem.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Block Reward Distribution is accomplished by creating a hook, as per the specifications below, which is called whenever a new EVM transaction occurs. `PostTXProcessing` is a wrapper for calling the EVM `PostTxProcessing` hook.

<figure><img src="https://lh3.googleusercontent.com/q3ZffWjqzdW6VQoK-Dn3S9S5pifSE6KNWt1qNn_nv4ogEPeHBmguIG9npYuO4EgFb4iv7-fOBEeUd2PUn1eeQkwx7XakCT4Js3A1HW7OaS3Ia-WNMJ74NWTASHWhAqjJKUAQW7KdqnaP2eZHMyUNzvk" alt=""><figcaption></figcaption></figure>
