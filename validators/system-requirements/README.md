# System Requirements

Validators are encouraged to use a reputable cloud provider or set up a secure physical operation with limited access to key management.  They should prepare their data center location with backup storage, good connectivity, redundant power, and multiple networking boxes.

In Cascadia's early development stages, we expect initial network requirements to be low.  As the network expands, more bandwidth, CPU, and memory may be needed.



**Supported OS**

Cascadia Network supports the following architectures for macOS, Windows, and Linux:

{% code overflow="wrap" %}
```javascript
darwin/arm64
darwin/x86_64
linux/arm64
linux/amd64
windows/x86_64
```
{% endcode %}



**Minimum System Requirements**

To run validator nodes on Cascadia, we suggest the following:

* 2 x dedicated/physical CPUs with`SSE4.1` and `SSE4.2` flags (use [lscpu](https://manpages.ubuntu.com/manpages/trusty/man1/lscpu.1.html) to verify)
* 8 GB RAM
* 200 GB SSD
* 100 Mbit/s always-on internet connection with 4 TB/month data plan
* Linux OS **(Ubuntu 20.04 or the latest version is recommended)**

{% hint style="info" %}
It's important to anticipate potential growth in server requirements and plan for necessary upgrades.
{% endhint %}
