# 🛡️ Bayesia License Server (BLS)

### Overview

* The Bayesia License Server (BLS) manages the distribution, activation, and use of all of Bayesia's products. It is the central "authority" that keeps track of accounts, users, user groups, licenses, usage, etc.&#x20;
* If you have a Floating Token License, a WebSimulator account, or have subscribed to an Elastic Pricing plan, you can monitor and manage your Account on the Bayesia License Server (BLS) via the web interface described in this section.&#x20;
* If you have Single-User/Single-Machine (SUSM) License, your BayesiaLab software will only need to connect with BLS (automatically or manually) once at the beginning of each license term, e.g., once a year.
* Even if you do not require access to BLS for your purposes, it may be helpful for you to understand the relationships of properties related to the BayesiaLab license you use.

### Bayesia License Server Framework

#### Definition of Terms

* Account refers to the entity that has a commercial agreement with Bayesia. Typically, there is one Account per organization, although large organizations may have one Account for each division or separate Accounts for certain regions.
* Managers are authorized to create and delete Users and Groups and assign an Account's Subscriptions to Groups.
* Users are individuals — identified by their unique Usernames — who run and utilize Bayesia's software.
* A Group can be created to assign privileges to a collection of Users. By default, there is a User Group and a Manager Group. Managers can create any number of Groups to define and/or restrict access to Bayesia's software.&#x20;
* Subscriptions are "owned" by Accounts and refer to term-based licenses to Bayesia's software. Managers can authorize Groups to utilize the Subscriptions of an Account.
* Sessions refer to instances of running Bayesia's software. As such, Sessions have a start and end date/time and are linked to specific Users. The number of Sessions that can run simultaneously, and the physical locations where Sessions can run, is governed by the Account's Subscriptions.
* Usage (or Usage Hours) refers to the time duration between the start (or launch) of the Session and the end (or termination) of each Session.

The following diagram illustrates the hierarchy of elements in BLS:

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691799636/BLS_Structure_urnbxg.png" alt=""><figcaption></figcaption></figure>

</div>

### Bayesia License Server Account Management



{% content-ref url="bls-login.md" %}
[bls-login.md](bls-login.md)
{% endcontent-ref %}

{% content-ref url="bls-home-page.md" %}
[bls-home-page.md](bls-home-page.md)
{% endcontent-ref %}

{% content-ref url="bls-session-dashboard.md" %}
[bls-session-dashboard.md](bls-session-dashboard.md)
{% endcontent-ref %}

{% content-ref url="bls-account-management.md" %}
[bls-account-management.md](bls-account-management.md)
{% endcontent-ref %}

{% content-ref url="bls-connection.md" %}
[bls-connection.md](bls-connection.md)
{% endcontent-ref %}

### Data Security

* BayesiaLab and the Bayesia APIs always run locally on the hardware on which you installed the software, e.g., your desktop or laptop computer.
* BayesiaLab is not a SaaS product, i.e., it is not "software as a service."
* There is no provision for running BayesiaLab remotely on Bayesia's servers.&#x20;
* Your local BayesiaLab installation never transmits any of your data or models to the Global Bayesia License Server.
* The only information sent to the Global Bayesia License Server is the user login and hashed password, the user account, and the version of BayesiaLab software currently in use.
* For each session, only the username, account, start and end date/time of the session, plus the associated IP address, are stored on the Global Bayesia License Server.
* Any temporary connection ("ping") to the Global BayesiaLab License Server only serves the purpose of validating your licenses.
* All data and models are stored within the infrastructure you control unless you explicitly choose to upload them elsewhere, for instance, to the BayesiaLab WebSimulator Server, with the express intent of sharing your model​.
* Bayesia staff has no access to or visibility of your models or data through the BayesiaLab software.&#x20;
