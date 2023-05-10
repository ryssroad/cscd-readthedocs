# Modules

A module refers to a set of components that perform specific functions within a network.  These modules work together to ensure the proper functioning and security of the Cascadia blockchain

Here are the production-grade modules that can be used in Cascadia applications:

| claims     | The mainnet release's rewards status and claim procedures.                                                                                                 |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| erc20      | On-chain, trustless bidirectional token translation between the Cosmos and Cascadia EVM runtimes. Per interval, executes custom state transitions (epoch). |
| epochs     | Per interval, executes custom state transitions (epoch).                                                                                                   |
| evm        | Smart Contract deployment and execution.                                                                                                                   |
| feemarket  | Fee market implementation based on the EIP1559 specification.                                                                                              |
| incentives | Incentivize user interaction with governance-approved smart contracts. A share of validator incentives is distributed amongst veCC holders and nProtocols. |
| inflation  | Mints new tokens daily and allocate them to staking rewards, vesting, community pool, and usage incentives.                                                |
| revenue    | Splitting gas fees between block proposers and smart contract deployers.                                                                                   |
| vesting    | Vesting accounts with lockup and clawback capabilities.                                                                                                    |
