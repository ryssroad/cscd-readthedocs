# Installation (Validator)

Before following the steps below, first set up a node as per the instructions provided [here.](https://cascadia.gitbook.io/gitbook/validators/install-your-node)

{% hint style="info" %}
To resume typing while your node is running, press **ctrl-c**.
{% endhint %}



**Step 1: Verify that your node is fully synced.**

```
cascadiad status
```

If `catching_up` returns `false`, your node is fully synced.

If `catching_up` returns `true`, your node is still catching up.

{% hint style="info" %}
Wait until your node has fully synced (`catching_up` returns `false`) before proceeding.  This may take some time--grab some coffee!
{% endhint %}



**Step 2: Generate and store your validator's address and keys.**

Run the following command to create a new validator key pair:

<pre class="language-javascript"><code class="lang-javascript"><strong>cascadiad keys add &#x3C;key_name>
</strong></code></pre>

Replace `<key_name>` with a name for your validator's key.

\
**For example:**

```
cascadiad keys add yourvalidator
```

This command will prompt you to generate a keyring passphrase and generate a new validator key pair, which consists of a **Cascadia wallet address, a public key, and a mnemonic phrase.** Keep the keyring passphrase and mnemonic phrase secret and securely stored. The public key will be used to identify your validator on the Cascadia network.

{% hint style="info" %}
To access your account, use the `cascadiad keys add <key_name> --recover` command.  Enter your keyring passphrase and mnemonic when prompted, and make sure to override the existing name ''test.''
{% endhint %}



**Step 3: Convert your Cascadia address to an EVM address.**

After creating a public key, run the following command to convert your Cascadia wallet address from Step 2 to an EVM address:

{% code overflow="wrap" %}
```javascript
cascadiad address-converter <your_wallet_address>
```
{% endcode %}

Replace `<your_wallet_address>` with your Cascadia wallet address from Step 2.



**Step 4: Fund your validator's EVM address.**

Transfer CC tokens to your validator's EVM address or utilize the [faucet](https://www.cascadia.foundation/faucet). &#x20;

{% hint style="info" %}
Enter your converted EVM address from Step 3 into the faucet. A properly formatted EVM address will begin with "0x" followed by a series of alphanumeric characters, such as "0x2e...4B9T".
{% endhint %}



**Step 5: Confirm receipt of CC tokens.**

Confirm that you have received CC tokens by entering your EVM address from Step 4 into Cascadia's [block explorer](https://explorer.cascadia.foundation/).



**Step 6: Create your initial validator funding tx.**

To create a validator tx, run the following command:

{% code overflow="wrap" %}
```javascript
cascadiad tx staking create-validator \
--from <key_name> \
--chain-id cascadia_6102-1 \
--moniker="<validator_name>" \
--commission-max-change-rate=0.01 \
--commission-max-rate=1.0 \
--commission-rate=0.05 \
--details="<description>" \
--security-contact="<email_address>" \
--website="<your_website>" \
--pubkey $(cascadiad tendermint show-validator) \
--min-self-delegation="1" \
--amount <token_delegation>aCC \
--gas "auto" \
--gas-adjustment=1.2 \
--gas-prices="7aCC" \
--broadcast-mode block
```
{% endcode %}

**Fill in these parameters:**

`<key_name>`: The name you inputted in Step 2.

`<validator_name>`: The name you want to give your validator.

`<description>`: Details about your validator node.

`<email_address>`: Your email address.

`<your_website>`: The URL of your website, if available.

`<token_delegation>`: The number of tokens you want to delegate. This is denominated in aCC, which is equivalent to 1e18 CC, i.e. 1 CC = 1,000,000,000,000,000,000 aCC.

{% hint style="info" %}
For `gas-prices`, around 7 aCC is standard. However, you may need to adjust this amount if the tx is unsuccessful.
{% endhint %}

**For example:**

{% code overflow="wrap" %}
```javascript
cascadiad tx staking create-validator \
--from yourvalidator \
--chain-id cascadia_6102-1 \
--moniker="ubuntu" \
--commission-max-change-rate=0.01 \
--commission-max-rate=1.0 \
--commission-rate=0.05 \
--details="The World's First  Neocybernetic  Blockchain" \
--security-contact="admin@cascadia.foundation" \
--website="cascadia.foundation" \
--pubkey $(cascadiad tendermint show-validator) \
--min-self-delegation="1" \
--amount 1000000000000000000aCC \
--gas "auto" \
--gas-adjustment=1.2 \
--gas-prices="7aCC" \
--broadcast-mode block
```
{% endcode %}

Enter the passphrase you created in step 2, then confirm the transaction.

{% hint style="info" %}
You can verify the success of your validator status by checking whether your validator address appears on [Cascadia's validator explorer](https://validator.cascadia.foundation/validators).
{% endhint %}



Congratulations, you're successfully running a Cascadia validator!
