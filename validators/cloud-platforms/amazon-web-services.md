# Amazon Web Services

**Step 1: Sign up for an AWS account.**

1. Navigate to [https://aws.amazon.com](https://aws.amazon.com/), and click on **"Create an AWS account."**
2. Provide your email address, password, and your preferred AWS account name.
3. Choose the **"Basic"** support plan and confirm.



**Step 2: Set up an EC2 instance.**

Once you have created an AWS account, sign in to the AWS Management Console and go to the EC2 Dashboard.

1. Click on **"Launch Instance."**
2. Choose the **"Ubuntu Server 20.04 LTS"** or a later version.
3. Select an appropriate instance type.  The "t2" series, **"t2.micro"**, is included in the Free Tier.  **"T3.large"** is recommended.&#x20;
4. Create a new key pair (or select an existing one you have), and download the private key file.
5. Add the appropriate storage.  Check the minimum requirements [here](https://cascadia.gitbook.io/gitbook/validators/system-requirements).



**Step 3: Connect to your EC2 instance.**

To connect to your EC2 instance, open your preferred terminal and click the **"EC2 Instance Connect"** button.  This will allow you to securely connect to your instance using SSH.



{% hint style="info" %}
Once the command prompt opens up, follow the next steps [here](https://cascadia.gitbook.io/gitbook/validators/install-your-node).
{% endhint %}
