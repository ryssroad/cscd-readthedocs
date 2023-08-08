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

We take a node [snapshot](https://www.cascadia.foundation/snapshot) every 6 hours. We then delete all the previous snapshots to free up the space on the file server.

The snapshot is designed for node operators to run an efficient validator service on the Cascadia chain. To make the snapshot as small as possible while still viable as a validator, we use the following setting to save disk space. We suggest you make the same adjustment on your node too. Please notice that your node will have very limited functionality beyond signing blocks with efficient disk space utilization. For example, your node will not be able to serve as an RPC endpoint (which is not suggested to run on a validator node anyway).

Since we periodically state-sync our snapshot nodes, you might notice that sometimes the size of our snapshot is surprisingly small.

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
