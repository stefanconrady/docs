# Floating Token License Installation

### Overview

This section provides you with step-by-step instructions for installing a floating license of BayesiaLab on your computer.

Before you can start the installation, you will need to receive the following two emails below from [bls@bayesia.com](mailto:bls@bayesia.com).

{% content-ref url="account-information.md" %}
[account-information.md](account-information.md)
{% endcontent-ref %}

{% content-ref url="software-download-and-activation-instructions.md" %}
[software-download-and-activation-instructions.md](software-download-and-activation-instructions.md)
{% endcontent-ref %}

### Activation

Upon starting BayesiaLab, you will be prompted to enter your **User Name** and **Password** to connect to the [**Bayesia License Server**](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/bayesia-license-server).

Please note that the **User Name** and **Password** for connecting to the BayesiaLab License Server are different from your download credentials.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392721/6652861.png" alt="" width="375"><figcaption></figcaption></figure>

For the Floating License to work, BayesiaLab must be able to connect to and remain connected with bls1.bayesia.com:2424. If you enter your credentials and there is no response from the login window, this means that BayesiaLab cannot connect with the [**Bayesia License Server**](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/bayesia-license-server) **(BLS)**. Please open a web browser and go to [http://bls1.bayesia.com](http://bls1.bayesia.com/) to check whether you can access this URL.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392721/12845152.png" alt="" width="375"><figcaption></figcaption></figure>

If you are able to get the BLS' Login page but are still unable to get a response from the login window, you most likely have a problem with your Firewall. Please ask your IT administrator to define an outbound rule that will specifically allow BayesiaLab to communicate with the [Bayesia License Server](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/bayesia-license-server) at address bls1.bayesia.com:2424. For instance, if you had BayesiaLab installed in the _C:\Program Files\Bayesia_ directory, your IT administrator would need to establish an outbound rule for _C:\Program Files\Bayesia\BayesiaLab\jreXXX\bin\javaw.exe_ (see screenshot below from a Windows Server 2008 installation).

Upon connecting successfully, BayesiaLab will start up.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/2392721/6652863.png" alt="" width="375"><figcaption></figcaption></figure>

If you cannot solve the firewall issue, a workaround consists of using an external, non-corporate Internet connection, e.g., at home or using a cellphone as a hotspot, etc., and connect to the BayesiaLab License Server from there without the firewall blocking problem. Then, you can enable the “[Borrow Session](http://library.bayesia.com/pages/viewpage.action?pageId=6684825)” option on the second screen when you start up BayesiaLab. Then, you can work offline for the duration you have specified.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/floating-license-2392721-2020-06-09.png)
