# Guide

The following process shows how to create CW20 tokens, detailing steps to create, query, and execute CW20 methods.



**Create a CW20 Token**

**Step 1: Token Details**

* **Name**: Full name of the token.
* **Symbol**: Abbreviation of the token name.
* **Decimals**: Specifies the divisibility. For instance, 6 decimals imply you can have a minimum of 0.000001 of your token.
* **Initial Balance**: The amount of tokens present when created.



**Step 2: Mint**

* **Minter Address**: Address authorized to create new tokens.
* **Cap**: Maximum number of tokens that can exist.



**Step 3: Marketing**

* **Project**: Name displayed for marketing.
* **Description**: Detailed information about the token project.
* **Wallet Address**: Displayed as the official address.
* **Logo URL**: Image URL for marketing and branding.



**Query**

| Balance       | Retrieve the balance of a specific address         | Address in question                   |
| ------------- | -------------------------------------------------- | ------------------------------------- |
| Allowance     | Amount one address allows another to spend or burn | Allower address, Spender address      |
| All Allowance | List of all allowances given by an address         | Allower Address                       |
| All Accounts  | Addresses holding the token                        | None (just the CW20 contract address) |
| Minter        | Address authorized to mint tokens                  | None (just the CW20 contract address) |
| Marketing     | Retrieve the token's promotional details           | None (just the CW20 contract address) |

\
**Interact with the CW20 Token**

<table data-header-hidden><thead><tr><th width="224.33333333333331">Method</th><th>Description</th><th>Additional Information</th></tr></thead><tbody><tr><td>Burn</td><td>Destroy tokens from your balance</td><td>Reduces total token supply</td></tr><tr><td>Burn From</td><td>Destroy tokens from another address</td><td>Uses permissions to burn</td></tr><tr><td>Increase Allowance</td><td>Expand the spending permission of an address</td><td>Based on your balance</td></tr><tr><td>Decrease Allowance</td><td>Reduce the spending permission of an address</td><td>Based on your balance</td></tr><tr><td>Transfer</td><td>Move tokens to another address</td><td>Direct transfer</td></tr><tr><td>Transfer From</td><td>Move tokens using permissions from another address</td><td>Requires prior allowance</td></tr><tr><td>Send</td><td>Transfer tokens with a follow-up message</td><td>Message executed post transfer</td></tr><tr><td>Send From</td><td>Use permissions to transfer and execute a message</td><td>Uses allowance, message post transfer</td></tr><tr><td>Update Marketing</td><td>Modify the promotional details of the token</td><td>Update branding/promo information</td></tr><tr><td>Update Logo</td><td>Change the branding logo of the token</td><td>Logo's URL</td></tr></tbody></table>

\
