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

# Checkpointing

To ensure the accuracy of ve-balances, Cascadia implements checkpointing, which calculates slope and bias via locked tokens and lock duration. To this end, a custom integration for new cooldown lock types has been created where the balance remains the same until the cooldown is triggered, as per the specifications below:

<figure><img src="https://lh5.googleusercontent.com/1-ZXf6FJlw1-oMcDqXrC3UCgmW6v_IdDah6PDFZbUFEzC-Dqbrvduu1dqW8w-Afo1sSA8tea3KLjubhLLVgKyMivihwA1hjOKyIc1f5PW3bulBSszD1Wg7q7VxIwji-3T-lBd54pFqpMr--XCPoAtqU" alt=""><figcaption></figcaption></figure>
