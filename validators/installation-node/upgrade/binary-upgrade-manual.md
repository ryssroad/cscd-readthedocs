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

# Binary Upgrade (Manual)

This guide will help you manually and automatically upgrade the `cascadiad` binary.



**Step 1: Initiate the upgrade proposal**

On the chain side, the upgrade proposal will be initiated and passed through the governance voting process. The chain will then stop at height: 1774000.



**Step 2: Stop the node**

Stop the node using the following command:

```javascript
sudo systemctl stop cascadiad
```



**Step 3: Download and replace the new binary**

Download the new v0.1.4 binary from the following link: [https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad](https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad) and replace the binary with this command:

{% code overflow="wrap" %}
```javascript
wget https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad -O $(which cascadiad)
```
{% endcode %}



**Step 4: Restart the cascadiad service**

Finally, restart the cascadiad service using the command:

```javascript
sudo systemctl restart cascadiad
```