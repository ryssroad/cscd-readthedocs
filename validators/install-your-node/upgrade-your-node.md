# Upgrade your Node

Follow these steps to update your Cascadia node to the latest version.\


**Step 1: Stop the cascadiad service.**

```javascript
sudo systemctl stop cascadiad
```

\
**Step 2: Navigate to the home directory.**

```javascript
cd $HOME
```

\
**Step 3: Download the latest Cascadia release.**

{% code overflow="wrap" %}
```javascript
curl -L https://github.com/CascadiaFoundation/cascadia/releases/download/v0.1.2/cascadiad-v0.1.2-linux-amd64 -o cascadiad
```
{% endcode %}

{% hint style="info" %}
The latest `cascadiad` binary release can be found on [GitHub](https://github.com/cascadiafoundation/cascadia/releases).
{% endhint %}

\
**Step 4: Make the downloaded file executable.**

```javascript
chmod +x cascadiad
```

\
**Step 5: Replace the existing Cascadia binary with the new one.**

```javascript
sudo mv cascadiad $(which cascadiad)
```

\
**Step 6: Restart the Cascadia service.**

```javascript
sudo systemctl restart cascadiad
```



{% hint style="info" %}
Node snapshots can be found in the Directory: [https://www.notion.so/cascadiafoundation/a560ef5f506847b2886148bd06428ca0?v=8d4e9324743949b5a3674d1675a609ae](https://www.notion.so/cascadiafoundation/a560ef5f506847b2886148bd06428ca0?v=8d4e9324743949b5a3674d1675a609ae)
{% endhint %}
