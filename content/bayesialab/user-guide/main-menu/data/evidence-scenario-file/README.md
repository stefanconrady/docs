# Evidence Scenario File

### Context

* In BayesiaLab, you can manage sets of actual or potential observations in a Bayesian network using Evidence Scenario Files.&#x20;
* For instance, an Evidence Scenario File can serve as a convenient way to manage multiple sets of assumptions, such as what-if scenarios. This is particularly helpful when scenarios contain many individual assumptions. Imagine the business case of an airline represented as a Bayesian network. It would have to include assumptions regarding travel demand for all origin-destination pairs. Manually setting and modifying assumptions for hundreds of nodes would not be practical. &#x20;

### Definition

* An Evidence Scenario File consists of one or more Evidence Scenarios.&#x20;
* And, each Evidence Scenario contains one or more node-specific observations, as illustrated below:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692452520/EvidenceScenarioFileSchema_scpl7a.svg" alt="" width="563"><figcaption></figcaption></figure>

* Applying an Evidence Scenario means setting the stored pieces of evidence to the corresponding nodes.

{% hint style="info" %}
Note that evidence cannot be set on Not Observable Nodes, i.e., nodes that have a Cost of 0 (see [Cost Management](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-panel-graph-window-cost-management)).
{% endhint %}

### Store Evidence Scenarios in Validation Mode&#x20;

With a given Bayesian network, any current observation on a node or sets of observations set on multiple nodes can be recorded as an Evidence Scenario. As soon as you store an Evidence Scenario, BayesiaLab "starts a tab" by creating an internal Evidence Scenario File.

Four types of evidence can be saved as an Evidence Scenario:

* Hard Evidence
* Likelihood Evidence
* Probabilistic Evidence
* Numerical Evidence

To learn more about setting evidence, please see the section on Setting Evidence in Contextual Menu of Monitors.

### Usage

* To store an observation as an Evidence Scenario, click the ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184077/BayesiaLab\_Icons/store-evidence\_atnzcs.svg) icon.
* Then, enter an optional comment in the pop-up window and assign a Weight to the Evidence Scenario you are storing. If you don't enter a comment, the Evidence Scenario will merely be indexed sequentially, starting with 0.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Evidence-Scenario-File/StoreEvidencePrompt.png)

* Click OK to confirm.
*   Now, an additional icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg) in the Status Bar indicates that there is an Evidence Scenario File. \


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Graph-Windows/Status-Bar/StatusBarEvidenceScenario.png" alt=""><figcaption></figcaption></figure>
* Right-clicking the ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg) icon in the Status Bar brings up the list of stored Evidence Scenarios, enumerated by an index and, if available, with corresponding comments. &#x20;
* You can add further Evidence Scenarios to the ones already stored in the internal Evidence Scenario File.
* So, the next time to click the ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184077/BayesiaLab\_Icons/store-evidence\_atnzcs.svg) icon, the pop-up window asks whether you want to append the new Evidence Scenario to the list of Evidence Scenarios or replace a particular existing Evidence Scenario.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Evidence-Scenario-File/StoreEvidencePromptReplace.png)

* To apply (or recall) a stored Evidence Scenario, right-click on the Evidence Scenario File icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg) in the Status Bar and click on the scenario you want to apply to the network.\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Menus/Data/Evidence-Scenario-File/RecallEvidenceScenarios.png)
*   Also, hovering over the Evidence Scenario File icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg) with your pointer brings up the number of available Evidence Scenarios.\


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Graph-Windows/Status-Bar/StatusBarEvidenceScenarioCount.png" alt=""><figcaption></figcaption></figure>
*   Upon selecting (and therefore applying) an Evidence Scenario, the corresponding comment, if available, appears in the Status Bar.\


    <figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/User-Guide/Graph-Windows/Status-Bar/ObservationSetComment.png" alt=""><figcaption></figcaption></figure>
* You can remove the current Evidence Scenario File by left-clicking on the ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg) icon.&#x20;
* Note that an Evidence Scenario File is saved with the Bayesian network file. So, reopening the saved network makes all stored Evidence Scenarios available again.

### Inference with an Evidence Scenario File

In addition to recalling Evidence Scenarios one by one, you can also use them in BayesiaLab batch-processing functions:

* Batch Labeling
* Batch Inference
* Batch Joint Probability
* Batch Outlier Explanation

In this context, the Evidence Scenario File provides the observations in the same way as an internal or external dataset.
