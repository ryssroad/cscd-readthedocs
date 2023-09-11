# Deployment

**Step 1: Deploy the wasm binary to the testnet**

Use the `wasmd Go CLI` or `CosmJS Node Console`.

To upload the code to the blockchain:

```
wasmd query wasm list-code $NODE
```

Alternative for uninitialized environment variables:

{% code overflow="wrap" %}
```
wasmd query wasm list-code --node https://rpc.malaga-420.cosmwasm.com:443
```
{% endcode %}



**Step 2: Store the bytecode on-chain and get the Code Id.**&#x20;

{% code overflow="wrap" %}
```
RES=$(wasmd tx wasm store artifacts/cw_nameservice.wasm --from wallet --other-options...)
echo $RES
CODE_ID=$(echo $RES | jq -r '.logs[0].events[-1].attributes[0].value')
```
{% endcode %}



**Step 3: Check instantiated contracts using the Code Id.**

```
wasmd query wasm list-contract-by-code $CODE_ID $NODE --output json
```



**Step 4: Verify the uploaded wasm binary.**

{% code overflow="wrap" %}
```
wasmd query wasm code $CODE_ID $NODE download.wasm
diff artifacts/cw_nameservice.wasm download.wasm
```
{% endcode %}



**Step 5: Instantiate the wasm contract:**

{% code overflow="wrap" %}
```
wasmd tx wasm instantiate $CODE_ID "$INIT" --from wallet --other-options...
```
{% endcode %}



**To interact with a contract**

Register a name:

{% code overflow="wrap" %}
```
wasmd tx wasm execute $CONTRACT "$REGISTER" --amount 100umlg --from wallet --other-options...
```
{% endcode %}

Transfer the name record to another address:

{% code overflow="wrap" %}
```
wasmd tx wasm execute $CONTRACT "$TRANSFER" --amount 999umlg --from wallet --other-options...
```
{% endcode %}



**Using CosmJS Node Console for deployment:**

Initialize a CosmJS CLI session:

{% code overflow="wrap" %}
```
npx @cosmjs/cli@^0.28.1 --init https://raw.githubusercontent.com/InterWasm/cw-plus-helpers/main/base.ts
```
{% endcode %}

Import necessary utilities and upload the wasm binary.



**Instantiate the Contract in CosmJS:**

Define default fees, create an instance using the code id, and get the contract address.



**Contract Interaction in CosmJS:**

Register a name and transfer ownership to another address.

\
