# Validators

Cascadia utilizes [Tendermint](https://github.com/tendermint/tendermint/tree/master/docs/introduction), which is dependent on a group of validators that add new blocks to the blockchain.  Validators play a role in the consensus mechanism by disseminating encrypted and authenticated votes using the unique key of each validator. Validators and their delegators receive tokens from transaction fees and CC as block rewards.&#x20;

Validators also collect fees collected from the deployed ve-contract using functions in the bank module of Cosmos SDK to receive a portion of these fees.  An additional share of validator rewards and gas fees go to CC lockers and nProtocols, which will be adjustable via governance.

Nodes are computers running the Cascadia software that contribute to the network by relaying information.  Each node needs to stake at least 1 CC to become a Validator.

| [System Requirements](https://cascadia.gitbook.io/gitbook/validators/system-requirements) | These are the minimum requirements to run a validator in the Cascadia network. |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Cloud Platforms](cloud-platforms/)                                                       | This guide shows you how to install a VM using Google Cloud & AWS.             |
| [Install your Node](https://cascadia.gitbook.io/gitbook/validators/install-your-node)     | The first steps on how to install a Cascadia node.                             |
| [Run your Validator](https://cascadia.gitbook.io/gitbook/validators/run-your-validator)   | This guide shows you how to set up and run your validator.                     |
