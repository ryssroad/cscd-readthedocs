# CLI Setup

CLI stands for Command Line Interface. It's a way to interact with a computer program by typing commands into a terminal or console. Running a program in CLI mode means that it is being executed through a terminal, rather than through a graphical user interface.

{% hint style="info" %}
CLI is a different approach to [node setup](./).  Minimum requirement is **Python 3.8.**
{% endhint %}



**Step 1: Initiate CLI, and choose a node type.**

<pre class="language-javascript" data-overflow="wrap"><code class="lang-javascript"><strong>curl https://raw.githubusercontent.com/CascadiaFoundation/chain-configuration/master/cascadia-installer.py > i.py &#x26;&#x26; python3 i.py
</strong></code></pre>

Select 1 to run a Full Archive Node or 2 to run a Client Node.



**Step 2: Choose a network to join.**

Enter option `2`: Testnet  `cascadia_6102-1`.



**Step 3: Do you want to install Cascadia in the default location?**

Enter choice `1`: Yes, use the default location.\


**Step 4: Input desired node name.**

Enter your desired name.



**Step 5: Do you want to run Cascadia on default ports?**

Enter choice `1`: Yes, use default ports.



**Step 6: Please choose your desired pruning settings.**

Enter choice `2`: Nothing, keep everything (select this if running an archive node).



**Step 7: Please choose from the following options.**

Enter choice `2`: Start at block 1 and automatically upgrade at upgrade heights.



**Step 8: Do you want to use Cosmovisor to automate future upgrades?**

Enter choice `2`: No, just set up a `cascadiad` background service.
