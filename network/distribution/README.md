---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Distribution

#### **APR Calculation**

`apr = staking_rewards * annual_provision / bonded_tokens`



**Parameters**

**annual\_provision**

{% code overflow="wrap" %}
```
curl https://lcd.cascadia.foundation/cascadia/inflation/v1/annual_provisions
```
{% endcode %}

**staking\_rewards**

```
curl https://lcd.cascadia.foundation/cascadia/reward/params
```

**bonded\_tokens**

```
curl https://lcd.cascadia.foundation/cosmos/staking/v1beta1/pool
```
