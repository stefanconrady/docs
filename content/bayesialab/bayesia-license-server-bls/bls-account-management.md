# BLS Account Management

### Context

In Account Management, you can manage all the different components and properties of your Account.&#x20;

### Definition of Terms

* Account refers to the entity that has a commercial agreement with Bayesia. Typically, there is one Account per organization, although large organizations may have one Account for each division or separate Accounts for certain regions.
* Managers are authorized to create and delete Users and Groups and assign an Account's Subscriptions to Groups.
* Users are individuals — identified by their unique Usernames — who run and utilize Bayesia's software.
* A Group can be created to assign privileges to a collection of Users. By default, there is a User Group and a Manager Group. Managers can create any number of Groups to define and/or restrict access to Bayesia's software.&#x20;
* Subscriptions are "owned" by Accounts and refer to term-based licenses to Bayesia's software. Managers can authorize Groups to utilize the Subscriptions of an Account.
* Sessions refer to instances of running Bayesia's software. As such, Sessions have a start and end date/time and are linked to specific Users. The number of Sessions that can run simultaneously, and the physical locations where Sessions can run, is governed by the Account's Subscriptions.
* Usage (or Usage Hours) refers to the time duration between the start (or launch) of the Session and the end (or termination) of each Session.

### Example

This diagram illustrates a typical example of an Account:

* 6 Users, including:
  * 1 Manager
  * 5 Users
* 3 Subscriptions, including:
  * Floating Token License
  * WebSimulator
  * API
* 3 Groups, including:
  * 1 Manager Group
  * 2 User Groups

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073332.jpg" alt=""><figcaption></figcaption></figure>

* Manager #1 can manage the Account and has access to all Subscriptions.
* User #1 and User #2 belong to Group U1 and can use the Floating Token License and the WebSimulator.
* User #4 and User #5 belong to Group U2 and can use the WebSimulator and the API.
* User #3 belongs to both Groups, i.e., U1 and U2, and therefore has access to all Subscriptions.

### Properties

* There are four types of properties that control the access and usage of individual Users to Bayesia software subscriptions.

### Users' Group (Membership) Properties

* Managers define the Group memberships of a User using two properties:
  * User's Group (Membership) Expiration Date: on this date, the User's membership in the Group will expire, meaning he will no longer have access to the Subscriptions assigned to this Group.
  * **#Hours** (applies only to Floating Token Licenses and Elastic Pricing Plans): the maximum number of hours a User can utilize a Subscription as a member of the Group. Once the limit is reached, access to the Group's Subscription is revoked. 00:00:00 indicates that no limit is defined.

### Group's Subscription Properties

* Managers can use five properties to customize a Group's access to the Subscriptions of an Account:
  * **Groups' Subscription Expiration Date**: on this date, the Group's access to the listed Subscription will be disabled. As a result, all Users who are members of the Group will no longer have access to the Subscription.
  * **#Hours**: Managers can set a maximum number of Usage Hours that applies to all Users that are members of the Group. A value of 00:00:00 indicates that no limit is set at the Group level. However, an individual User can still have a Usage limit regarding his membership in the Group.&#x20;
  * **Max Borrow Time** (applies Floating Token Licenses and Elastic Pricing Plans only): Users in the Group can borrow tokens for no longer than the duration specified here.
  * **Primary Access Priority** (applies to Floating Token Licenses only): Users who are members of the Group have the specified priority in situations when there are competing requests for access to Subscriptions. For instance, the Group _Student Interns_ may be given a lower priority than the Group _Senior Analysts_ regarding the use of a limited number of available Subscriptions. "Primary Access" refers to the first Session a User launches.
  * **Secondary Access Priority** (applies to Floating Token Licenses only ): Same as above, except that it refers to the second Session as User launches. Thus, a User in the Group _Research Fellows_ could be allowed to launch two Sessions simultaneously, while Users in the Group _Trainees_ cannot launch any Session at all. Setting 0 for this priority prevents the Group's Users from launching a second Session.
* When a member requests access to a subscription and no tokens are available, a primary or secondary session with a lower priority (if any) is closed to release the token. The user of the to-be-closed session is notified that a user with a higher priority is requesting access to the token, and he is then prompted to save his current work.

### Subscriptions

* The **Kick Order** is the only subscription property modifiable by the managers. This is only for subscriptions using tokens.
* This parameter allows you to define the policy used when a session has to be closed because a higher-priority user is requesting access to a session that has no more available tokens. When several sessions with the lowest priority have been identified, the session to be closed is either the older one (**First Session**) or the most recent one (**Last Session)**.

### Group Properties

* Fives properties are available for Managers to customize Groups:
  * **Group Expiration Date**: beyond this date, the group is set **Disabled,** which prevents its members to use the associated subscriptions.
  * **#Hours**: when this property is set to a value different from 00:00:00, it is associated with each member, unless the member has already a value that has been set via the Users' Group Properties or the Groups' Subscription Properties.
  * **Max Borrow Time**: maximum duration of an offline session allowed for the group members. This will only be applied as a default value for the subscriptions using tokens or elastic plans, unless this property has been set via the Groups' Subscription Properties.
  * **Primary Access Priority**: priority level associated with the user's primary session of the group members. This will only be applied as a default value for the subscriptions using tokens, unless this property has been set via the Groups' Subscription Properties.
  * **Secondary Access Priority**: priority level associated with the user's concurrent sessions (except his/her primary session) of all the group members. Note that setting 0 for this priority prevents the member to have any concurrent sessions. This will only be applied as a default value for the subscriptions using tokens unless this property has been set via the Groups' Subscription Properties.

### Views/Tabs

#### Account

* This view allows accessing the information about the account.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073347.png" alt=""><figcaption></figcaption></figure>

* The fields highlighted in green can be edited by the managers.

#### Groups

* This tab allows managing the groups.
* One Manager Group and one User Group are automatically generated when a new Account is created. These two groups are mandatory, and they cannot be removed, nor have their Type changed.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073368.png" alt=""><figcaption></figcaption></figure>

* The fields highlighted in green can be edited by the managers.

#### Users

* This tab allows adding and removing users to the account.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073355.png" alt=""><figcaption></figcaption></figure>

* The fields highlighted in green can be edited by Managers.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073372.png" alt=""><figcaption></figcaption></figure>

* The **Username** should be the user's email.
* The user is associated with the default User Group.
* When a subscription with tokens or an elastic plan is associated with the group, the "_BayesiaLab Download & Activation Instructions_" email is automatically sent to the user upon validation.
* The managers need thus to go to the Users' Group to change the group or some other properties.
* The _**Remove**_ button becomes active upon the selection of a user.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/5799963.png" alt=""><figcaption></figcaption></figure>

* Note that users that had an activity are not really removed; they are only set to **Disabled**.

#### Users' Group

* This tab allows defining the group membership of users and their properties.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073357.png" alt=""><figcaption></figcaption></figure>

* The Users' Group Properties have the highest priority, i.e., they cannot be overridden by the properties defined via another view.
* When a subscription with tokens or an elastic plan is associated with the group, the "BayesiaLab Download & Activation Instructions" email is automatically sent to the user upon validating the creation of a user.&#x20;
* To resend this email, the managers just have to select the user and click "**Send Download Information**".

#### Subscriptions

* This view returns the subscriptions (tokens or elastic plans) associated to the account.

\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073358.png" alt=""><figcaption></figcaption></figure>

* Among all these fields, only the fields highlighted in green can be edited by the managers.

#### WebSimulator Subscriptions

* This view provides information about the BayesiaLab WebSimulator subscriptions.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073359.png" alt=""><figcaption></figcaption></figure>

* Among all these fields, only the field highlighted in green can be edited by the managers.
  * **Number of Models**: number of simulators you can publish simultaneously with this subscription.
  * **Number of Available Models**: number of simulators that can still be published with this subscription.
  * **Type:** indicates if the subscription corresponds to _**Public**_ (anyone can potentially access your simulator and experiment with it) or _**Private**_ simulators (you can restrict access to designated users who require a model-specific ID and password).
  * **End Date**: the expiration date of the subscription.

#### Groups' Subscriptions

* This tab allows managing the association between Groups and Subscriptions.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073376.png" alt=""><figcaption></figcaption></figure>

* Among all these fields, only the fields highlighted in green can be edited by the managers.
* The Groups' Subscription Properties have a higher priority than the Group Properties. This means that if they are not defined in this view, they inherit those defined in the Group Properties; otherwise, they are not overridden.

#### Registration Codes

* Instead of manually adding users, the managers can create a registration code to let their team members register by themselves via the Sign In function.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/5668875/15073362.png" alt=""><figcaption></figcaption></figure>

* **Duration**: validity period of the form (_optional_).
* **Access duration**: validity period of access to the products of the account by the user (_optional_).
* **Expected**: number of users that are expected to register (_optional_).
* **Registered**: number of users that have used the form so far to register
* **Code**: registration codes the team members have to use in the registration form to get BLS credentials and be associated with the account.
