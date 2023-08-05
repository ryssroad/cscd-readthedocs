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
Snapshots can be found in the [Community Directory](https://www.askclu.com/index.php/Community\_Directory:\_Snapshot).
{% endhint %}

\
**Step 1: Install lz4 if needed**

```
sudo apt update
sudo apt install snapd -y
sudo snap install lz4
```

\
**Step 2: Download the snapshot, for example**

{% code overflow="wrap" %}
```
wget -O cascadia_latest.tar.lz4 https://snapshot.cascadia.foundation/snapshots/null --inet4-only
```
{% endcode %}



**Step 3: Stop your node**

```
sudo systemctl stop cascadiad
```

\
**Step 4: Reset your node**

{% code overflow="wrap" %}
```
cascadiad tendermint unsafe-reset-all --home $HOME/.cascadiad --keep-addr-book
```
{% endcode %}

**WARNING:** This will erase your node database. If you are already running a validator, be sure you backed up your `priv_validator_key.json` before running the command. The command does not wipe the file. However, you should already have a backup of it in a safe location.

\
**Step 5: Decompress the snapshot to your database location**&#x20;

Your database location will be something to the effect of `~/.cascadiad` depending on your node implementation.

{% code overflow="wrap" %}
```
lz4 -c -d cascadia_latest.tar.lz4 | tar -x -C $HOME/.cascadiad data
```
{% endcode %}

\
**Step 6: Restart your node**

```
sudo systemctl start cascadiad
```

\
**Step 7: Remove the downloaded snapshot to free up space**

```
rm -v cascadia_latest.tar.lz4
```

\
**Step 8: Make sure that your node is running**

```
sudo systemctl status cascadiad
sudo journalctl -u cascadiad -f
```

ADVANCED ROUTE: The above solution requires you to download the compressed file, uncompress it and then delete the original file. This requires extra storage space on your server. You can run the following combo command to stream the snapshot into your database location. For advanced users only:

{% code overflow="wrap" %}
```
curl -o - -L https://snapshot.cascadia.foundation/snapshots/$(curl -s https://snapshot.cascadia.foundation/snapshots/cascadia/info | jq -r .filename) | lz4 -c -d - | tar -x -C $HOME/.cascadiad data
```
{% endcode %}

\
We take a node snapshot every day. We then delete all the previous snapshots to free up the space on the file server.

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
