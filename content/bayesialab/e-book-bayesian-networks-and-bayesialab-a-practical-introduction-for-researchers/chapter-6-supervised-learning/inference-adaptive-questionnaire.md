# Inference: Adaptive Questionnaire

### Context

* In situations in which individual cases are under review, e.g., when diagnosing a patient, BayesiaLab can provide diagnostic support by means of the Adaptive Questionnaire.
* This approach helps prioritize what variable to investigate or what pieces of evidence to collect in order to reduce the uncertainty regarding a target variable of interest.
* Whenever you have a Bayesian network with a Target Node, regardless of whether the network was machine-learned or created from expert knowledge, you can launch the Adaptive Questionnaire.
* Importantly, the Adaptive Questionnaire seeks the optimal sequencing of evidence for a specific case or instance rather than creating a set of rules that apply in general.
* For creating a generalized set of priorities, please see Target Interpretation Tree in this chapter.

### Usage

The Adaptive Questionnaire can be started via `Main Menu > Inference > Adaptive Questionnaire`.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaire.png" alt=""><figcaption></figcaption></figure>

For a Target Node with more than two states, it can be helpful to specify a Target State for the Adaptive Questionnaire.

Setting a Target Node allows BayesiaLab to compute the Binary Mutual Information and then focus on the designated Target State.

However, as the Target Node in our example is binary by default, setting a Target State is superfluous.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireOptions.png" alt=""><figcaption></figcaption></figure>

### Costs

Furthermore, we can set the cost of collecting observations via the Cost Editor, which can be started by clicking the Edit Observations Costs button.

This is helpful if certain variables are more costly to observe or require more effort to obtain than others. So, Costs do not necessarily have to represent a financial cost. For instance, we could make Costs proportional to the difficulty of collecting observations.&#x20;

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireCostEditor.png)

### Adaptive Evidence-Seeking



{% hint style="warning" %}
In analyzing Fine Needle Aspirates, all image attributes are obtained simultaneously. As a result, this particular domain is not ideal for demonstrating the Adaptive Questionnaire.&#x20;

A better example would be a diagnostic process, in which a clinician collects observations from a patient in a targeted way. We can imagine that a physician starts the diagnosis process by collecting easy-to-obtain data, such as blood pressure, before proceeding to more elaborate (and more expensive) diagnostic techniques, such as performing an MRI.
{% endhint %}

Here, we simulate using the Adaptive Questionnaire as if we could choose the order of collecting evidence.

After starting the Adaptive Questionnaire, BayesiaLab presents the Monitor of the Target Node and displays its marginal probability. That Monitor is highlighted in green.

Furthermore, the Monitors are automatically sorted in descending order with regard to the Target Node by taking into account the [Mutual Information](../../key-concepts/mutual-information/) (or Binary Mutual Information, if applicable) and the Cost of obtaining the evidence:

1. $$concave\ points$$
2. $$area$$
3. $$concavity$$
4. $$texture$$
5. $$fractal\_dimension$$

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep1.svg" alt="" width="563"><figcaption></figcaption></figure>

Given this order, it would be ideal to collect the value of $$concave\ points$$ as the first observation.

#### Observation #1

Let us suppose that we can do that and obtain $$concave\ points<=0.079$$ as the first piece of evidence.

Upon setting that state in the Monitor of $$concave\ points$$, the Monitor Panel is updated as follows:

* In the Monitor of the Target Node, we see that the probability of $$diagnosis=malignant$$ has increased to 69.08%.
* The order of Monitors is resorted according to [Mutual Information](../../key-concepts/mutual-information/) and Cost:
  1. $$texture$$
  2. $$area$$
  3. $$concavity$$
  4. $$fractal\_ dimensions$$
* The Monitor of the node we just observed drops to the bottom of the list. Given that we already know its value, no further information can be gained from it.
* Also, the distributions of all the not-yet-observed nodes have changed, with $$concavity$$increasing substantially.
* The small gray arrows inside the Monitors indicate how much the probabilities have changed.&#x20;

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep2.svg" alt="" width="563"><figcaption></figcaption></figure>

Note that we are not merely seeing the next-in-line Monitor "moving up." Rather, the entire list is recomputed, given the most recent piece of evidence.

For instance, when we started the Adaptive Questionnaire, $$area$$ was two spots ahead of $$texture$$. Given the last observation, however, $$texture$$ has become more important than area.

#### Observation #2

So, given the above ordering, $$texture$$ would be the next best evidence to obtain.

In real-world applications, it is possible that the ideal evidence is not available and, therefore, must be skipped. We simulate such a situation by observing $$area$$ instead of $$texture$$.

We find $$area<=696.25$$ and enter that evidence in the corresponding Monitor:

* The probability of $$diagnosis=malignant$$ decreases to 56.23%
* The order of the remaining unobserved nodes is now:
  1. $$texture$$
  2. $$concavity$$
  3. $$fractal\_dimension$$

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep3.svg)

#### Observation #3

For this iteration, we follow the top recommendation, i.e., $$texture$$, and observe $$texture<=16.395$$.

* The probability of $$diagnosis=malignant$$ decreases further to 15.70%
* The order of the remaining unobserved nodes is now:
  1. $$concavity$$
  2. $$fractal\_dimension$$

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep4.svg)

#### Observation #4

For this iteration, we follow the recommendation and observe $$concavity>0.072$$.

* The probability of $$diagnosis=malignant$$ increased to 19.04%
* At this point, only $$fractal\_dimension$$ remains unobserved.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep5.svg)

#### Observation #5

For the last node, $$fractal\_dimension$$, we obtain $$fractal\_dimension<=0.056$$.

In this hypothetical example, the last observation appears to have a rather substantial impact on the diagnosis.

The Monitor of the Target Node now reports that $$diagnosis=malignant$$ has a probability of 93.05%

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/6-Supervised-Learning/AdaptiveQuestionnaireStep6.svg)

### Workflow Animation

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690845944/AdaptiveQuestionnaire_jm9xds.mp4" %}

### Summary & Next Steps

The Adaptive Questionnaire is a highly practical tool for seeking the optimal next piece of evidence when trying to determine the state of a Target Node.

We used the Adaptive Questionnaire via the Graphical User Interface in BayesiaLab in this example. For situations when end-users do not have access to the BayesiaLab software, you can publish an Adaptive Questionnaire via the WebSimulator. This allows anyone to interact with an Adaptive Questionnaire through a web browser.

Finally, BayesiaLab can produce a static version of the Adaptive Questionnaire, which can be used entirely offline. This tool is the Target Interpretation Tree, which we discuss in the next section.
