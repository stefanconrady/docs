# BLS Connection

### Global Bayesia License Server

* By default, all BayesiaLab software and the Bayesia APIs connect to the Global Bayesia License Server, which is physically located at Bayesia’s corporate headquarters.
* This requires your locally-installed BayesiaLab software to connect to bls1.bayesia.com on the destination port 2424, i.e., the BayesiaLab software opens a TCP/IP connection with bls1.bayesia.com:2424.​

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Artwork/Vector_Graphics/BLS3.svg" alt=""><figcaption></figcaption></figure>

* If your computer is behind a firewall, you may need to ask your IT department to define an exception to allow you to connect.
* To check whether you can connect to the Global Bayesia License Server, open Command Prompt (on a Windows PC) or Terminal (on a Mac) and enter ping bls1.bayesia.com.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Pricing-Licensing/Bayesia-License-Server/ping.png" alt=""><figcaption></figcaption></figure>

### Local Bayesia License Server

* If a corporate firewall prevents TCP/IP connections to bls1.bayesia.com, a Local Bayesia License Server can be installed within your corporate environment.
* The Local Bayesia License Server consists of a small program that runs in the background on a server to which your locally-installed BayesiaLab software and the APIs can connect.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Artwork/Vector_Graphics/BLS2.svg" alt=""><figcaption></figcaption></figure>

* This setup requires a one-time connection per license term, e.g., annually, to the Global Bayesia License Server to initialize the Local Bayesia License Server.
* For the ongoing operation, however, no Internet connection is required on your server, and all ports can be blocked.

### Data Security

* BayesiaLab and the Bayesia APIs always run locally on the hardware on which you installed the software, e.g., your desktop or laptop computer.
* There is no provision for running BayesiaLab remotely on Bayesia's servers.&#x20;
* Your local BayesiaLab installation never transmits any of your data or models to the Global Bayesia License Server.
* The only information sent to the Global Bayesia License Server is the user login and hashed password, the user account, and the version of BayesiaLab software currently in use.
*
