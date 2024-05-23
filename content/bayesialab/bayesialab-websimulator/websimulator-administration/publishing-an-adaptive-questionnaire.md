# Publishing an Adaptive Questionnaire

### Overview

* This section covers the process of publishing a fully configured Bayesian network model as an Adaptive Questionnaire.

#### Prerequisites

* You need to have a Bayesian network model available that was configured with the [WebSimulator Editor ](../websimulator-editor/)in BayesiaLab.
* You have successfully logged in to the [WebSimulator Administration Page](./).

### New Questionnaire Workflow

* Click the New Questionnaire button in the upper right corner of the Administration Page.
* A new pop-up window presents you with four tabs:
  * ​Bayesian Network &#x20;
  * Description&#x20;
  * Properties
  * Title Bar&#x20;

### Bayesian Network

* Click the Select File button to choose the Bayesian network (in XBL format) that you have configured for use with the Adaptive Questionnaire.
* Click OK to upload the selected file to the server.
* If the uploaded file meets the requirements, the message "Valid" appears behind the Select File button.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/NewQuestionnaire.gif" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Many of the settings in this tab and the following tabs repeat options that you could have specified in the [WebSimulator Editor](../websimulator-editor/) before uploading the XBL file. As a result, many of the fields contain default values. However, you can modify any existing content by providing new values. Please note that such edits only apply "downstream" to the WebSimulator, but they will not propagate backward to your Bayesian network file.
{% endhint %}

* By default, the Name field adopts any name you specified in the [Simulator](../websimulator-editor/editor-simulator-settings.md) tab of the WebSimulator Editor. Note that this field is mandatory.
* The same applies to the Author field. Note that the Author information will appear in the context of the properties of your model, which are available to the end-user by clicking the information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) in the published WebSimulator.

{% hint style="info" %}
The slide-in message on the bottom-right corner of the browser window states that all observations have been removed from your model. This means that any dataset that had been associated with your XBL was immediately stripped and is no longer available on the WebSimulator Server.
{% endhint %}

### Description

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/NewQuestionnaireDescriptionTab.png" alt=""><figcaption></figcaption></figure>

* The Description tab allows you to provide background and contextual information regarding your Bayesian network model.
* By default, this field adopts the Description defined in the Simulator tab of the WebSimulator Editor, which, in turn, utilizes any available Network Comments associated with the Bayesian network model.&#x20;
* End-users can access the Description by clicking the Information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg) in the published WebSimulator.
* If an Image was already provided in the WebSimulator Editor, ​the eye icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184056/BayesiaLab\_Icons/eye\_rs46m5.svg) will indicate its presence. Typically, you would use an Image depicting the Bayesian network model. Clicking the eye icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184056/BayesiaLab\_Icons/eye\_rs46m5.svg) provides you with a preview.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/35651863/35651873.png" alt=""><figcaption></figcaption></figure>

* Furthermore, you can remove any existing Image and replace it with a visual of your choice by clicking on Select File.
* Field of Study and Analysis Type allow you to characterize your Bayesian network model. Especially with public WebSimulators, it can help you direct end-users to your model.

### Properties

The elements of the Properties tab repeat some of the options that are also available in the Simulator tab of the [WebSimulator Editor](../websimulator-editor/).

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/QuestionnairePropertiesTab.png" alt=""><figcaption></figcaption></figure>

* If you check the Display Variations option, the Questionnaire will highlight the impact of the pieces of evidence set by the end-user, either with respect to the previous state or the Reference State (see next item).

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714046/13860947.png" alt=""><figcaption></figcaption></figure>

* If you check the Store Initial Reference State option, the Questionnaire will display variations relative to the marginal distributions of the Outputs. More specifically, the Initial Reference State refers to the probabilities and values of the marginal distribution of the Outputs before setting any observations. With this option checked, the variations will be computed as the difference between the current state and the reference state. Otherwise, the variations are computed as the difference between the current state and the previous state, i.e., before setting the most recent piece of evidence.
* For an illustration of the Layout Options, please see Layout in the [WebSimulator Editor — Simulator Settings](../websimulator-editor/editor-simulator-settings.md#layout).

### Title Bar

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/QuestionnaireTitleBarTab.png" alt=""><figcaption></figcaption></figure>

* ​You can specify a Logo or banner to appear in the upper left corner of your model's Questionnaire page.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714046/12845388.png" alt=""><figcaption></figcaption></figure>

* Logo URL allows you to associate a hyperlink with the Logo.
* You can specify the Title to be shown at the top of the published WebSimulator page.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/35651863/35651868.png)

* Theme Color refers to the background color of the horizontal panel at the top of your published Questionnaire.

### Publishing the Questionnaire

* Once your Questionnaire is set up, you can proceed to publish it.
* From the Administration Page, select your model and then click the Publish button.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/PublishQuestionnaire.gif" alt=""><figcaption></figcaption></figure>

* Once you have published your model, its symbol will switch from ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184057/BayesiaLab\_Icons/minus\_lcoqss.svg) to ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184058/BayesiaLab\_Icons/redo2\_mjyqjy.svg) in the Published column of the Administration Page.
* The Sharing column indicates whether you have shared your model publicly ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184059/BayesiaLab\_Icons/users\_qcw0d0.svg) or privately ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184057/BayesiaLab\_Icons/lock1\_uqcujy.svg).

### Public & Private Questionnaires

* Generally, you can publish your Bayesian network model as a public ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184059/BayesiaLab\_Icons/users\_qcw0d0.svg) or a private ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184057/BayesiaLab\_Icons/lock1\_uqcujy.svg)  Questionnaire. This is analogous to the options for publishing a WebSimulator.
* Depending on your subscription type, you may only have the public option available or both the public and the private.
* The dates show the respective expiration dates of your subscriptions.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/BlabC/attachments/12714046/12845222.png)\


### **​Public Questionnaire** ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184059/BayesiaLab\_Icons/users\_qcw0d0.svg)

* "Public" means that anyone with an Internet connection can access the Questionnaire of the model you published.
* A public Questionnaire will also appear as a tile on the public WebSimulator homepage at [https://simulator.bayesia.com](https://simulator.bayesia.com/). This is a great way to showcase your work to the wider world.
* By default, all BayesiaLab Professional licenses allow you to publish public Questionnaires.

### **Private Questionnaire**  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184057/BayesiaLab\_Icons/lock1\_uqcujy.svg)

* "Private" means that you can restrict access to your Questionnaire to users whom you have given a specific URL plus a password.
  * To publish private and password-protected models, you need to subscribe to a private WebSimulator Account. Please see the pricing guide for more details.

{% hint style="info" %}
A private WebSimulator Account allows you to publish both private WebSimulators and private Adaptive Questionnaires.
{% endhint %}

* As you publish a private model, you will be prompted to create a password that will be linked to the URL of your Questionnaire.
* The password should have at least 8 characters, including at least one number.
* This means that access to your private Questionnaire is controlled by one URL and one password.&#x20;
* Anyone to whom you give the URL plus the password will have access to your private Questionnaire.
* To revoke access to your private Questionnaire, you need to unpublish it.
* Even once you have subscribed to a private WebSimulator Account, you still retain your free public account and thus have both options available when publishing a model.

{% hint style="danger" %}
Be careful not to inadvertently publish a model publicly that you intended to share privately.
{% endhint %}

### Show Details

* The Show Details button on the Administrator Page allows you to view all settings of the WebSimulator highlighted in the list.
* A pop-up window shows all settings specified in the [New Questionnaire Workflow](publishing-an-adaptive-questionnaire.md#new-questionnaire-workflow) and also features the same tabs:
  * Bayesian Network
  * Description
  * Properties
  * Title Bar
* The Bayesian Network tab, however, provides additional elements:
  * The Identifier is an automatically assigned 12-digit number that uniquely identifies your Questionnaire.
  * Creation Date
  * Modification Date
  * Published Date
  * Password reveals the password you set for the Questionnaire when you published it. For public Questionnaires, this field is blank.
  * Direct URL is the URL you can share with end-users so they can go directly to your Questionnaire.
  * The format of the URL follows the pattern: `https://simulator.bayesialab.com/#!simulator/Identifier`

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/QuestionnaireShowDetails.gif)

### Edit Properties

* Clicking the Edit Properties button allows you to modify the properties that you previously specified in the [New Questionnaire Workflow](publishing-an-adaptive-questionnaire.md#new-questionnaire-workflow) or, before that, in the [WebSimulator Editor](../websimulator-editor/).
* Edit Properties is only available for _unpublished_ Questionnaires. If you wish to modify a _currently published_ Questionnaire, you first need to click the Unpublish button on the Administration Page.
* Upon modification, you can click Publish to republish your Questionnaire again.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/EditPropertiesQuestionnaire.png" alt=""><figcaption></figcaption></figure>

### Run

* Clicking the Run button opens up your Questionnaire so you can see it and use it like an end-user.
* More specifically, your browser opens the URL `https://simulator.bayesialab.com/#!simulator/Identifier`
* This is now the live version of the Questionnaire, of which you could previously only launch a static preview from the [WebSimulator Editor](../websimulator-editor/).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/WebSimulator-Administration/RunQuestionnaire.gif)
