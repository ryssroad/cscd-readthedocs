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

# Snapshot

{% hint style="info" %}
Cascadia's most recent, official snapshot can be found [here](https://snapshot.cascadia.foundation/).  Additional snapshots can be found in the [Community Directory](https://www.askclu.com/index.php/Community\_Directory:\_Snapshot).
{% endhint %}

Node snapshots are taken every 6 hours. Previous snapshots are cleared to free up space on the file server.

The snapshot is designed for node operators to run an efficient validator service on Cascadia. To make the snapshot as small as possible while still viable as a validator, the following settings are used to save disk space. It's suggested that you make the same adjustment on your node as well.

**app.toml**

```
# Prune Type
pruning = "custom"

# Prune Strategy
pruning-keep-recent = "100"
pruning-keep-every = "0"
pruning-interval = "10"
```

**config.toml**

```
indexer = "null"
```



**Limitations and Functionalities**

Please note, with an efficient utilization of disk space, your node's functionalities may be limited beyond signing blocks.  For instance, your node may not function as a RPC endpoint.



**Periodic State-Sync**

The nodes used for snapshot creation undergo state sync periodically. As a result, the snapshot size might occasionally appear unusually small.  This process is part of an ongoing effort to optimize for decentralization, performance, and efficiency.
