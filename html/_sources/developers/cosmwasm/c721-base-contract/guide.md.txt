# Guide

Creating a CW721 contract, representing either an NFT collection or a standalone NFT. The primary detail you need is the Minter Address (the sole authority to mint new tokens within the CW721 contract).



**Query**

Fetching data about a CW721 token happens directly from the blockchain. The Cascadia dashboard allows easy querying of any CW721 token. Each query typically needs the CW721 contract address. However, certain queries, like `Number of Tokens`, `Contract Info`, `All Tokens`, and `Minter`, don't need additional parameters. The parameters for other queries include:

<table data-header-hidden><thead><tr><th width="154.33333333333331">Query</th><th width="371">Description</th><th>Required Input</th></tr></thead><tbody><tr><td>Owner Of</td><td>Identifies the token's owner inside the contract.</td><td>Token ID</td></tr><tr><td>Approval</td><td>Permissions an address holds over a token.</td><td>Owner Address, Token ID</td></tr><tr><td>Approvals</td><td>All approvals are given by the token's owner.</td><td>Token ID</td></tr><tr><td>All Operators</td><td>Addresses with full control over an owner's NFTs.</td><td>Owner Address</td></tr><tr><td>NFT Info</td><td>Token URI and extension details.</td><td>Token ID</td></tr><tr><td>All NFT Info</td><td>Comprehensive NFT details, including owner &#x26; approvals.</td><td>Token ID</td></tr><tr><td>Tokens</td><td>All tokens owned by an address.</td><td>Owner Address</td></tr></tbody></table>



**Execute**

CW721 Contracts house methods for token interactions. Cascadia Tools simplifies these executions:

<table data-header-hidden><thead><tr><th width="159.33333333333331">Method</th><th>Description</th><th>Parameters</th></tr></thead><tbody><tr><td>Transfer NFT</td><td>Move an NFT to a different address.</td><td>Recipient Address, Token ID</td></tr><tr><td>Send NFT</td><td>Transfer NFT &#x26; execute a message post-transfer.</td><td>Recipient Address, Token ID, Message</td></tr><tr><td>Approve</td><td>Permit another address to transfer or send a token.</td><td>Recipient Address, Token ID</td></tr><tr><td>Revoke</td><td>Nullify transfer or send permissions over a token.</td><td>Recipient Address, Token ID</td></tr><tr><td>Approve All</td><td>Allow an address full control over all owner's tokens.</td><td>Recipient Address</td></tr><tr><td>Revoke All</td><td>Remove permissions over all tokens.</td><td>Recipient Address</td></tr><tr><td>Mint</td><td>Create a new token for an address.</td><td>Recipient Address, Token ID</td></tr><tr><td>Burn</td><td>Destroy a token you can access.</td><td>Token ID</td></tr></tbody></table>
