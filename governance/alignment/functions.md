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

# Functions

{% hint style="info" %}
Cascadia's bCC contract is written in Vyper 0.2.7, which is unaffected by malfunctioning reentrancy locks.  Be aware that Vyper versions 0.2.15, 0.2.16, and 0.3.0 are susceptible to malfunctioning reentrancy locks. For more information, refer to [this tweet](https://twitter.com/vyperlang/status/1685692973051498497) from Vyper.
{% endhint %}



**Structs**

The contract code begins by defining two structs: `Point` and `LockedBalance`. In the context of a smart contract, a struct is a composite data type that encapsulates a set of related variables under a single reference, allowing for more organized data management.

* [x] **Struct:** `Point`
  * Used to represent a point in time where the state of the contract changes in terms of total supply and balance.
* [x] **Struct:** `LockedBalance`
  * Represents the amount of tokens locked for a user along with the timestamp when these tokens can be unlocked.



**Interfaces**

The contract includes an interface for `SmartWalletChecker`. An interface in Ethereum smart contracts describes the functions of another contract, allowing interaction with external contracts that exist on the Ethereum blockchain.

* [x] **Interface:** `SmartWalletChecker`
  * Contains a `check()` function, which is used to verify whether an address belongs to a whitelisted smart wallet.\


\
**Constants and Variables**

The contract declares a number of constants and public variables. Constants define fixed values used throughout the contract, while public variables are accessible both within and outside the contract.



**Events**

Events in smart contracts are mechanisms that allow the execution of code to trigger logging operations on the blockchain. These logged events are stored with the contract's address in the transaction log, a special data structure on the blockchain.



**Functions**

The contract defines several functions, which can be categorized as external (callable from other contracts), internal (only callable from within the contract), and view functions (do not modify the state but return values).

<table data-header-hidden><thead><tr><th width="318">Function Name</th><th>Description</th></tr></thead><tbody><tr><td><code>__init__()</code></td><td>This constructor function initializes the contract.</td></tr><tr><td><code>set_lock_bot()</code></td><td>Allows for setting a lock bot that can create locks on behalf of other users.</td></tr><tr><td><code>change_min_time()</code></td><td>Modifies the minimum required lock time.</td></tr><tr><td><code>change_max_time_div()</code></td><td>Modifies the maximum time divisor.</td></tr><tr><td><code>commit_transfer_ownership()</code></td><td>Starts the process of transferring the ownership of the contract.</td></tr><tr><td><code>apply_transfer_ownership()</code></td><td>Completes the process of transferring the ownership of the contract.</td></tr><tr><td><code>_checkpoint()</code></td><td>Records global and user-specific data to checkpoints.</td></tr><tr><td><code>_deposit_for()</code></td><td>Handles deposits and token locks for a specified user.</td></tr><tr><td><code>checkpoint()</code></td><td>Records global state data to a checkpoint.</td></tr><tr><td><code>deposit_for()</code></td><td>Allows anyone to deposit tokens on behalf of a specified user.</td></tr><tr><td><code>create_cooldown_lock()</code></td><td>Creates a token lock with a cooldown period.</td></tr><tr><td><code>create_cooldown_lock_for()</code></td><td>Creates a token lock with a cooldown period for a specified user.</td></tr><tr><td><code>start_cooldown()</code></td><td>Initiates the cooldown period for the sender's tokens.</td></tr><tr><td><code>renew_cooldown()</code></td><td>Allows the sender to extend the cooldown period for their tokens.</td></tr><tr><td><code>increase_amount()</code></td><td>Allows the sender to deposit more tokens without changing the unlock time.</td></tr><tr><td><code>withdraw()</code></td><td>Allows the sender to withdraw their tokens if the lock period has expired.</td></tr><tr><td><code>find_block_epoch()</code></td><td>Estimates the timestamp for a given block number using binary search.</td></tr><tr><td><code>balanceOf()</code></td><td>Returns the current voting power of a specified address at a given epoch.</td></tr></tbody></table>



**Modifiers**

Function modifiers, represented as `@external`, `@view`, and `@internal` decorators in the code, influence how functions ca be called. `@external` functions can be invoked from other contracts, `@view` functions can't modify the contract state, and `@internal` functions can only be called within this contract.



**Assertions**

The `assert` keyword is used for debugging. It throws an exception if a condition is not met, assisting in verifying the correctness of the code.

