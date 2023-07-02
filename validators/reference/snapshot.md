# Snapshot

#### **Step 1: Stop service, reset data.**

{% code overflow="wrap" %}
```
sudo systemctl stop cascadiad
cp $HOME/.cascadiad/data/priv_validator_state.json $HOME/.cascadiad/priv_validator_state.json.backup
rm -rf $HOME/.cascadiad/data
```
{% endcode %}



**Step 2: Download latest snapshot.**

{% code overflow="wrap" %}
```
curl -L <snapshot>.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.cascadiad
mv $HOME/.cascadiad/priv_validator_state.json.backup $HOME/.cascadiad/data/priv_validator_state.json
```
{% endcode %}

{% hint style="info" %}
Community`<snapshot>` can be found in our [Directory](https://www.notion.so/cascadiafoundation/a560ef5f506847b2886148bd06428ca0?v=8d4e9324743949b5a3674d1675a609ae).&#x20;
{% endhint %}



**Step 3: Restart service, check logs.**

{% code overflow="wrap" %}
```
sudo systemctl start cascadiad && sudo journalctl -u cascadiad -fn 100 -o cat
```
{% endcode %}
