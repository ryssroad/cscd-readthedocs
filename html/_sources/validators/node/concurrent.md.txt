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

# Concurrent

This guide explains how to install a Cascadia node on a server that already has a node installed.  By changing default ports, it's possible to run two nodes without conflict.



**Step 1: Check ports used by the existing node.**

Run the following command:

{% code overflow="wrap" %}
```javascript
ss -ntulp
```
{% endcode %}

The output will display a list of ports used by the nodes. By default, Cosmos nodes use the following ports: `26656`, `26657`, `6060`, `26658`, `26660`, `9090`, and `9091`.

You will receive a similar output, displaying a clear example of two nodes installed on the server, using different ports to avoid conflicts with each other. Here is an example of how that looks:

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



**Step 2: Change default ports.**

To avoid conflicts, change the default ports used by the new Cascadia node.  Here are the recommended port changes:

`config.toml`: Change `26658` to `36658`, `26657` to `36657`, `6060` to `6061`, `26656` to `36656`, and `26660` to `36660`.

{% code overflow="wrap" %}
```javascript
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:36658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:36657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6061\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:36656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":36660\"%" $HOME/.cascadiad/config/config.toml
```
{% endcode %}

`app.toml`: Change `9090` to `9190`, `9091` to `9191`, and `1317` to `1327`.

{% code overflow="wrap" %}
```javascript
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9190\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9191\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1327\"%" $HOME/.cascadiad/config/app.toml
```
{% endcode %}

`client.toml`: Change `26657` to `36657`.

{% code overflow="wrap" %}
```javascript
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:36657\"%" $HOME/.cascadiad/config/client.toml
```
{% endcode %}



**Step 3: Update `external_address` in config.toml.**

{% code overflow="wrap" %}
```javascript
external_address=$(wget -qO- eth0.me)
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:36656\"/" $HOME/.cascadiad/config/config.toml
```
{% endcode %}



**Step 4: Restart your Cascadia node.**

{% code overflow="wrap" %}
```bash
systemctl restart cascadiad && journalctl -u cascadiad -f -o cat
```
{% endcode %}
