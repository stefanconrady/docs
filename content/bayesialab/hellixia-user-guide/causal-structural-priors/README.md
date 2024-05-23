# Causal Structural Priors

### Context

With the [causality-analysis.md](../causality-analysis.md "mention") function, Hellixia allows you to retrieve domain knowledge from ChatGPT about a potential causal relationship between two nodes.

The Causal Structural Priors function extends this concept to more than two nodes.

### Usage & Example

* We illustrate the Causal Structural Priors workflow with the well-known "Visit Asia" example from the domain of lung diseases.
* We have a synthetic dataset from this domain, which has already been imported into BayesiaLab.
* So, our starting point is an unconnected network, as shown in the following screenshot.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689603068/Unconnected-Network_v2r9kd.webp" alt=""><figcaption></figcaption></figure>

* In addition to the descriptive and self-explanatory node names, Comments are associated with each node, as indicated by the information icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184116/BayesiaLab\_Icons/information-icon\_rcikcj.svg).
* For instance, the node Smoking has an associated Node Comment that says, "The patient is a regular smoker."
* Our objective is to find the causal relationships between risk factors, conditions, symptoms, and diagnostic imaging.
* However, we know that machine learning alone cannot discover the true causal structure of this domain.
* We begin with machine learning the associations between all nodes anyway and use the Unsupervised EQ learning algorithm for that purpose.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689602948/EQ_vqlhn5.webp" alt=""><figcaption></figcaption></figure>

* This newly-learned Bayesian network features directed arcs, but they can clearly not be interpreted as causal, e.g., Smoking could not possibly be a cause of Age.
* Applying the Genetic Grid layout highlights the implausibility of the arc directions.
* Select `Main Menu > View > Layout > Genetic Grid Layout > Top-Down Repartition`.
* Note that the algorithm keeps searching for a better layout until you stop the process by clicking the red button![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103679/BayesiaLab-Logos/red-button\_r825yi.svg)to the left of the Progress Bar.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689605379/Top-Down-Repartition_dtjcbe.webp" alt=""><figcaption></figcaption></figure>

* In the past, we would have had to use any available domain knowledge from experts to correct the arc directions.
* With Hellixia, however, we can tap into the domain knowledge available via ChatGPT.
* So, select all arcs and then select `Main Menu > Hellixia > Causal Structural Priors`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689613442/Causal-Structural-Priors-Window_dobhhh.webp" alt=""><figcaption></figcaption></figure>

* In the Causal Structural Priors window, you need to specify a number of items:
  * Under Completion Model, choose a model for which you have a subscription, e.g., GPT\_35 or GPT\_4.
  * You can specify a General Context of the problem domain. In this example, "Lung Diseases" would be appropriate.
  * Under Subject of the Query, check all fields that contain information regarding the subject matter. We have information in the Node Name and the Node Comment in the example.
* Clicking OK starts the search for causal relationships via ChatGPT. The progress bar at the bottom of the Graph Panel shows the search status.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689614067/Progress-Bar_kvo1j8.webp" alt=""><figcaption></figcaption></figure>

* A chime marks the completion of the search.
* Furthermore, the Structural Priors icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103672/BayesiaLab-Logos/structural-priors\_mrkohy.svg) appears in the bottom-right corner of the Graph Panel.
* To view the Structural Priors obtained from ChatGPT, you can click on the Structural Priors icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1684103672/BayesiaLab-Logos/structural-priors\_mrkohy.svg) or select `Graph Panel Contextual Menu > Edit Structural Priors`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689615213/Edit-Structural-Priors_bjjkmb.webp" alt=""><figcaption></figcaption></figure>

* This table displays the causal arc directions obtained from ChatGPT in the three left columns.
* The reason for the arc orientation is provided in the Explanation column.
* The final column, Check, indicates whether the causal direction matches ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184060/BayesiaLab\_Icons/validate-mean\_neyjmj.svg) the current orientation or not ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184075/BayesiaLab\_Icons/stop\_pgb4vf.svg).
* Clicking Preview opens a window showing a simplified view of the causal arc directions proposed by ChatGPT.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689618453/Structural-Priors-Preview_abuujh.webp" alt="" width="375"><figcaption></figcaption></figure>

Now, there are two ways to proceed, as illustrated in the following workflows 1 and 2.

{% content-ref url="workflow-1.md" %}
[workflow-1.md](workflow-1.md)
{% endcontent-ref %}

{% content-ref url="workflow-2.md" %}
[workflow-2.md](workflow-2.md)
{% endcontent-ref %}
