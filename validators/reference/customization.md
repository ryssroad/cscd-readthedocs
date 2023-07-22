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

# Customization

To personalize your validator, such as changing your avatar, follow these steps:



**Step 1: Sign up for an account on** [**Keybase.io**](https://keybase.io)**.**



**Step 2: Upload your avatar to your Keybase profile.**



**Step 3: Link your Validator ID to your Keybase identity.**

{% code overflow="wrap" %}
```javascript
cascadiad tx staking edit-validator \
--identity="<keybase_identity>" \
--chain-id cascadia_6102-1 \
--from <wallet_name> \
--gas "auto" \
--gas-adjustment=1.2 \
--gas-prices="7aCC"
```
{% endcode %}

`<keybase_identity>`: This is your Keybase 64-bit public key \[16 alpha numeric].

`<wallet_name>`: This is the name of your Cascadia wallet.
