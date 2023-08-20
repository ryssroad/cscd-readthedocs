# Staking Metrics

#### **APR Calculation**

To calculate the APR for staking, use the formula:

apr = staking\_rewards \* annual\_provision / bonded\_tokens



**Parameters**

**annual\_provision**

Retrieve from:

{% code overflow="wrap" %}
```
curl https://lcd.cascadia.foundation/cascadia/inflation/v1/annual_provisions
```
{% endcode %}



**staking\_rewards**

Retrieve from:

```
curl https://lcd.cascadia.foundation/cascadia/reward/params
```



**bonded\_tokens**

Retrieve from:

```
curl https://lcd.cascadia.foundation/cosmos/staking/v1beta1/pool
```
