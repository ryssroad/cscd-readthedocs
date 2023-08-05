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

Cascadia takes a snapshot to ensure smooth and efficient validator service operation. Following the completion of each new snapshot, previous snapshots are removed to maximize available server space. &#x20;

The node snapshot has been designed with the intention to optimize validator service performance on the Cascadia chain. To ensure the snapshot size is minimized while remaining fully functional for validators, the following settings are employed to economize disk space. It is advised that node operators adopt these adjustments in their nodes as well.

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

Please note, with this efficient utilization of disk space, your node's functionalities may be limited beyond signing blocks. For instance, your node may not function as an RPC endpoint.



**Periodic State-Sync**

The nodes used for snapshot creation undergo state sync periodically. As a result, the snapshot size might occasionally appear unusually small. This process is part of an ongoing effort to optimize performance and efficiency.
