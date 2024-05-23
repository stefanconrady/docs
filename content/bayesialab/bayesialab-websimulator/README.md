# 🎛️ BayesiaLab WebSimulator

### Overview&#x20;

* The BayesiaLab WebSimulator is a web application that allows you to share interactive models with your internal or external audience (e.g., your research clients), without having to install any software on their computers and without having end-users be familiar with the concept of Bayesian networks.
* The BayesiaLab WebSimulator publishes an interactive web page based on an XBL file, a Bayesian network model you created in BayesiaLab.
* You can designate which of the nodes in your network should be displayed to the end-user as Inputs and Outputs.
* Upon publishing the network, the BayesiaLab WebSimulator utilizes the [Bayesia Engine API ](../bayesia-engine-api/)— entirely in the background — to perform inference in your network. This allows end-users to enter observations/evidence on the nodes in your network via their web browser. Whenever evidence is set, the user will immediately see updated probability distributions of the Outputs.&#x20;
* The BayesiaLab WebSimulator's web interface is responsive, allowing even tablet or smartphone users to work dynamically with your network.&#x20;

### Example: Differential Diagnosis of COVID-19 and Influenza-Like Diseases

[https://simulator.bayesialab.com/#!questionnaire/377786492943](https://simulator.bayesialab.com/#!questionnaire/377786492943)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/WebSimulator/COVID-19-AdaptiveQuestionnaire.png" alt=""><figcaption></figcaption></figure>

### WebSimulator Infrastructure&#x20;

The WebSimulator infrastructure is comprised of three main constituents:

1. The analyst/developer uses BayesiaLab on his local hardware to build and configure a Bayesian network model for publication.
2. The BayesiaLab WebSimulator Server, located on the premises of Bayesia S.A.S., hosts and serves the uploaded and published model.
3. The end-users access the published model using a web browser. Importantly, models can be made available in two ways:
   * To a restricted group of users with a Private WebSimulator Account.
   * To the general public through a Public WebSimulator Account.

<div data-full-width="false">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692619963/WebSimulator_Diagram_qano6j.svg" alt="" width="375"><figcaption></figcaption></figure>

</div>

### WebSimulators and Adaptive Questionnaires&#x20;

The overarching concept of "WebSimulator" actually covers two closely related applications, the WebSimulator proper and the Adaptive Questionnaire.&#x20;

* Both the WebSimulator and the Adaptive Questionnaires allow end-users to perform interactive inference via a web interface.
* In a WebSimulator, the end-user sets observations on the Inputs, which updates the posterior probability distributions of the Outputs.
* In an Adaptive Questionnaire, as the end-user sets observations, the remaining Inputs are dynamically ordered, from high to low, according to the information they bring to the Target (or the set of Targets), given the current set of observations. The Adaptive Questionnaire provides a dynamic recommendation for seeking the optimal next piece of evidence with the objective of reducing the uncertainty of the Targets. &#x20;
* Whenever we refer to "WebSimulators" in general, we mean both types of simulators available in BayesiaLab: the WebSimulator proper and the Adaptive Questionnaire.&#x20;

### Instructions for WebSimulator Designers & Developers&#x20;

* You must have already created a Bayesian network model in BayesiaLab to publish a WebSimulator or Adaptive Questionnaire.&#x20;
* The following two steps explain your workflow for configuring and publishing WebSimulators and Adaptive Questionnaires:
  * Preparing Your Model — In the [WebSimulator Editor](websimulator-editor/) in BayesiaLab, you configure the functionality and appearance of your to-be-published model.
  * Publishing Your Model — The [WebSimulator Administration Page](websimulator-administration/) (i.e., the web interface of the WebSimulator server) allows you to upload, apply modifications, and publish your model.

{% hint style="info" %}
Please note that the process for creating a WebSimulator and an Adaptive Questionnaire is nearly identical.
{% endhint %}

### Instructions for WebSimulator End-Users&#x20;

This section applies to end-users, i.e., the individuals who will access the WebSimulator via web browser and utilize the published model for interactive inference.

* [Using the WebSimulator](using-the-websimulator.md)
* [Using the Adaptive Questionnaire](using-the-adaptive-questionnaire.md)

{% hint style="info" %}
There are no software or hardware requirements for end-users other than a web browser and an Internet connection.
{% endhint %}
