# Validators

Cascadia is built on [Tendermint](https://github.com/tendermint/tendermint/tree/master/docs/introduction), which is dependent on a group of validators that add new blocks to the blockchain.  Validators play a role in the consensus mechanism by disseminating encrypted and authenticated votes using the unique key of each validator. Validators and their delegators receive tokens from transaction fees and CC as block rewards.&#x20;

Validators also collect fees collected from the deployed ve-contract using functions in the bank module of Cosmos SDK to receive a portion of these fees.  An additional share of validator rewards and gas fees go to CC lockers and nProtocols, which will be adjustable via governance.

Nodes are computers running the Cascadia software that contribute to the network by relaying information.  Each node needs to stake at least 1 CC to become a Validator.
