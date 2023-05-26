# Validators

Cascadia utilizes [Tendermint](https://github.com/tendermint/tendermint/tree/master/docs/introduction), which is dependent on a group of validators that add new blocks to the blockchain.  Validators play a role in the consensus mechanism by disseminating encrypted and authenticated votes using the unique key of each validator. Validators and their delegators receive tokens from transaction fees and CC as block rewards.&#x20;

Validators also collect fees collected from the deployed ve-contract using functions in the bank module of Cosmos SDK to receive a portion of these fees.  An additional share of validator rewards and gas fees go to CC lockers and nProtocols, which will be adjustable via governance.

Nodes are computers running the Cascadia software that contribute to the network by relaying information.  Each node needs to stake at least 1 CC to become a Validator.

<table data-header-hidden><thead><tr><th width="210">Sections</th><th>Descriptions</th></tr></thead><tbody><tr><td><a href="https://cascadia.gitbook.io/gitbook/validators/system-requirements">System Requirements</a></td><td>These are the minimum requirements to run a validator in the Cascadia network.</td></tr><tr><td><a href="cloud-platforms/">Cloud Platforms</a></td><td>This guide shows you how to install a VM using Google Cloud &#x26; AWS.</td></tr><tr><td><a href="https://cascadia.gitbook.io/gitbook/validators/install-your-node">Install your Node</a></td><td>The first steps on how to install a Cascadia node.</td></tr><tr><td><a href="https://cascadia.gitbook.io/gitbook/validators/run-your-validator">Run your Validator</a></td><td>This guide shows you how to set up and run your validator.</td></tr></tbody></table>
