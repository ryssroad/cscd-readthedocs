# Manual Delegation

To delegate tokens using the **`cascadiad`** command, follow the structure below:

{% code overflow="wrap" %}
```javascript
cascadiad tx staking delegate <validator_address> <amount> --from <wallet_name> --chain-id cascadia_6102-1 --gas auto --gas-adjustment=1.2 --gas-prices 7aCC -y
```
{% endcode %}

**For example:**

{% code overflow="wrap" %}
```javascript
cascadiad tx staking delegate cascadiavaloper1zec8f7faf880q7l9s8dehz2054lnavfsuuf3gt 25000000000000000000000aCC --from ubuntu --chain-id cascadia_6102-1 --gas auto --gas-adjustment=1.2 --gas-prices 7aCC -y
```
{% endcode %}

| `<validator_address>`  | The address of the validator you want to delegate tokens. |
| ---------------------- | --------------------------------------------------------- |
| `<amount>`             | The amount of tokens you want to delegate.                |
| `--from <wallet_name>` | Specifies the wallet you want to use for delegation.      |
| `--gas-prices`         | Sets the gas price for the transaction.                   |



You can get more information by running the following command:

{% code overflow="wrap" %}
```javascript
cascadiad tx staking delegate --help
```
{% endcode %}
