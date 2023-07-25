# Snapshot

**Process**

A snapshot of nodes is taken daily in Cascadia to ensure smooth and efficient validator service operation. Following the completion of each new snapshot, all previous snapshots are removed to maximize available server space.



**Purpose of Node Snapshot**

The node snapshot has been designed with the intention to optimize validator service performance on the Cascadia chain. To ensure the snapshot size is minimized while remaining fully functional for validators, certain settings are employed to economize disk space. It is advised that node operators adopt these adjustments in their nodes as well.



**Limitations and Functionalities**

Please note, with this efficient utilization of disk space, your node's functionalities may be limited beyond signing blocks. For instance, your node may not function as an RPC endpoint, which isn't recommended to be run on a validator node in any case.



**Periodic State-Sync**

The nodes used for snapshot creation undergo state sync periodically. As a result, the snapshot size might occasionally appear unusually small. This process is part of an ongoing effort to optimize performance and efficiency.

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



**How To Process a Snapshot**

Install lz4 if needed

```
sudo apt update
sudo apt install snapd -y
sudo snap install lz4
```



**Download the snapshot, for example**

{% code overflow="wrap" %}
```
wget -O cascadia_latest.tar.lz4 https://snapshot.cascadia.foundation/snapshots/null --inet4-only
```
{% endcode %}



**Stop your node**

```
sudo systemctl stop cascadiad
```



**Reset your node**&#x20;

```
cascadiad tendermint unsafe-reset-all --home $HOME/.cascadiad --keep-addr-book
```

{% hint style="info" %}
**WARNING:** This will erase your node database. If you are already running validator, be sure you backed up your **`` `priv_validator_key.json` ``** prior to running the command. The command does not wipe the file. However, you should have a backup of it already in a safe location.
{% endhint %}



**Decompress the snapshot to your database location**

Your database location will be something to the effect of **`` `~/.cascadiad` ``** depending on your node implementation.

```
lz4 -c -d cascadia_latest.tar.lz4 | tar -x -C $HOME/.cascadiad data
```



**If everything is good, now restart your node**

```
sudo systemctl start cascadiad
```



**Remove the downloaded snapshot to free up space**

```
rm -v cascadia_latest.tar.lz4
```



**Make sure that your node is running**

```
sudo systemctl status cascadiad
sudo journalctl -u cascadiad -f
```

{% hint style="info" %}
**ADVANCED ROUTE**: The above solution requires you to download the compressed file, uncompressed it and then delete the original file. This requires extra storage space on your server.&#x20;
{% endhint %}

You can run the following combo command to stream the snapshot into your database location. For advanced users only:

{% code overflow="wrap" %}
```
curl -o - -L https://snapshot.cascadia.foundation/snapshots/$(curl -s https://snapshot.cascadia.foundation/snapshots/cascadia/info | jq -r .filename) | lz4 -c -d - | tar -x -C $HOME/.cascadiad data
```
{% endcode %}
