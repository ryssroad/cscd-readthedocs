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

# Automated

This guide will help you automatically upgrade the `cascadiad` binary.



**Step 1: Create the upgrade-info.json file.**

The upgrade-info.json file will be created in the data folder after the upgrade proposal is passed.

{% code overflow="wrap" %}
```javascript
{"name":"v0.1.4","time":"0001-01-01T00:00:00Z","height":1774000,"info":"{\"binaries\":{\"linux/amd64\":\"https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad-v0.1.4-linux-amd64.tar.gz\"}"}
```
{% endcode %}

{% hint style="info" %}
The latest `cascadiad` binary release can be found on [GitHub](https://github.com/cascadiafoundation/cascadia/releases).
{% endhint %}



**Step 2: Prepare for an automated upgrade.**

To automate the upgrade using cosmovisor, ensure your `cosmovisor/` directory is structured as follows:

```javascript
cosmovisor/
├── current/   # either genesis or upgrades/<name>
├── genesis
│   └── bin
│       └── cascadiad
└── upgrades
    └── v0.1.4
        ├── bin
        │   └── cascadiad
        └── upgrade-info.json
```



**Step 3: Download and extract the cascadiad binary.**

Use the following command to download and extract the cascadiad binary to the upgrades folder:

{% code overflow="wrap" %}
```javascript
mkdir [your cosmovisor path]/cosmovisor/upgrades
mkdir [your cosmovisor path]/cosmovisor/upgrades/upgrades
mkdir [your cosmovisor path]/cosmovisor/upgrades/upgrades/v0.1.4

wget -O - https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad-v0.1.4-linux-amd64.tar.gz | tar -xzvf - -C [your cosmovisor path]/cosmovisor/upgrades/v0.1.4 
```
{% endcode %}



**Step 4: Create the upgrade-info.json file in the upgrade folder.**

Finally, create the upgrade-info.json file in the 'upgrades/v0.1.4' folder using this command:

{% code overflow="wrap" %}
```javascript
cat <<EOF > [your cosmovisor path]/cosmovisor/upgrades/upgrades/v0.1.4/upgrade-info.json
{"name":"v0.1.4","time":"0001-01-01T00:00:00Z","height":1774000,"info":"{\"binaries\":{\"linux/amd64\":\"https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.4/cascadiad-v0.1.4-linux-amd64.tar.gz\"}"}
EOF
```
{% endcode %}
