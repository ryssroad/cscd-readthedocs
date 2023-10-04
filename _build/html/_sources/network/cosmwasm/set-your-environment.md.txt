# Set your Environment

Before you start, you have to decide where you'll run and test your contracts:

**Run Your Own Node**\
This option lets you set up and run a node locally.

**Connect to the Malaga Testnet**\
The Malaga testnet is live for quick testing, allowing you to deploy and run your contracts. To ensure it's active, check:

```bash
https://rpc.malaga-420.cosmwasm.com/status
https://faucet.malaga-420.cosmwasm.com/status
```

**Tokens on Testnet**\
Andalucía (uand) - Used for validators.\
Málaga (umlg) - Used for paying fees.



**Step 1: Choose an Interaction Tool**

You have two primary tools for interacting with the testnet:

**`wasmd`**: A Go client.

**Node REPL**: This tool is recommended for contract operations.&#x20;



**Step 2: Setting Up `wasmd` Go CLI**

Initialize the configuration of the network:

{% code overflow="wrap" %}
```
source <(curl -sSL https://raw.githubusercontent.com/CosmWasm/testnets/master/malaga-420/defaults.env)
```
{% endcode %}



Create wallet addresses by typing:

```
wasmd keys add wallet
wasmd keys add wallet2
```

{% hint style="info" %}
Remember to safely store your mnemonic.
{% endhint %}



**Credit Tokens**

If you're using a local node, you can skip this step, otherwise:

{% code overflow="wrap" %}
```
JSON=$(jq -n --arg addr $(wasmd keys show -a wallet) '{"denom":"umlg","address":$addr}') && curl -X POST --header "Content-Type: application/json" --data "$JSON" https://faucet.malaga-420.cosmwasm.com/credit

JSON=$(jq -n --arg addr $(wasmd keys show -a wallet2) '{"denom":"umlg","address":$addr}') && curl -X POST --header "Content-Type: application/json" --data "$JSON" https://faucet.malaga-420.cosmwasm.com/credit
```
{% endcode %}

**Configure `wasmd`**

{% code overflow="wrap" %}
```
eexport NODE="--node $RPC"
export TXFLAG="${NODE} --chain-id ${CHAIN_ID} --gas-prices 0.25${FEE_DENOM} --gas auto --gas-adjustment 1.3"
```
{% endcode %}



**Step 3: Setting Up the CosmJS CLI Client**

**Prerequisites**

You'll need Node.js (v12+) and npx.



**Initialize CosmJS CLI**

{% code overflow="wrap" %}
```
npx @cosmjs/cli@^0.28.1 --init https://raw.githubusercontent.com/InterWasm/cw-plus-helpers/main/base.ts --init https://raw.githubusercontent.com/InterWasm/cw-plus-helpers/main/cw20-base.ts
```
{% endcode %}



**Contract Interactions**

{% code overflow="wrap" %}
```
const [address, client] = await useOptions(malagaOptions).setup("password",".new.key");
client.getAccount(address);
client.getBalance(address,"umlg");
```
{% endcode %}
