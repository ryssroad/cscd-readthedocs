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

# Google Cloud Platform

**Step 1: Create a Google Cloud Services Account**

To begin, create a Google account if you do not already have one. Sign up for a free account at [https://console.cloud.google.com/freetrial](https://console.cloud.google.com/freetrial).

{% hint style="info" %}
**"Enable"** the API if the Cloud account is freshly set up.
{% endhint %}



**Step 2: Create a Virtual Machine**

After creating an account, create a virtual machine (VM) to execute your node. Proceed to the Google Cloud console and select the **"Compute Engine"** tab. Then, opt for **"Create Instance"** to produce a new VM instance.&#x20;

While setting up the VM, you must select the following:

1. An instance name.
2. A region and zone.
3. A machine configuration (check the minimum requirements [here](https://cascadia.gitbook.io/gitbook/validators/system-requirements)).
4. A Boot disk, such as Ubuntu 20.04 LTS x86/64.

{% hint style="info" %}
We suggest using the "N2" Series, "n2-standard-4" Machine Type, and Ubuntu 20.04 LTS (or more recent versions).
{% endhint %}

Once you have completed the configuration, click **"Create"** to initiate your VM.



**Step 3: Establish a Connection with Your VM**&#x20;

Click on the "SSH" button next to your VM instance in the console and follow the next steps [here](https://cascadia.gitbook.io/gitbook/validators/install-your-node).
