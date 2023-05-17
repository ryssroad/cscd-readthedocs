# ChainID & Address Prefix

ChainID is a number that identifies a specific blockchain. This number is used to ensure that transactions are processed on the correct blockchain, and not confused with transactions on another with a similar format. ChainID also prevents replay attacks, where a transaction is broadcast on multiple blockchains to trick users into accepting the same transaction on different chains.

Address format is used to identify unique users within a blockchain network.



**Cascadia's ChainID**

Cascadia uses several Chain IDs. Choose the correct ChainID when executing Cascadia in your local environment. \
\
The ChainID for Cascadia's devnet is `cascadia_6102-1`.



**Address Prefix**

BIP-0173 introduces a new format for segregated witness output addresses. With regard to the respective network type, Cascadia has many address prefixes, including:

| Testnet | `cascadia` |
| ------- | ---------- |

Cascadia employs the Bech32 address format. Bech32 encoding offers reliable data integrity checks. The human-readable component offers contextual cues, helping UI designers clear error messages.
