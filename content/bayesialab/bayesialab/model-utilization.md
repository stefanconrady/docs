# Model Utilization

### Model Utilization&#x20;

* BayesiaLab provides a range of functions for systematically utilizing the knowledge contained in a Bayesian network. They make a Bayesian network accessible as a probabilistic expert system that can be queried interactively by an end-user.

#### Adaptive Questionnaire&#x20;

* The [Adaptive Questionnaire](https://www.bayesia.com/articles/bayesialab-knowledge-hub/inference-adaptive-questionnaire) function provides guidance regarding the optimum sequence for seeking evidence.
* BayesiaLab determines dynamically, given the evidence already gathered, the next best piece of evidence to obtain in order to maximize the information gain with respect to the [Target Node](https://www.bayesia.com/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-target-node-target-state) while minimizing the cost of acquiring such evidence.
* In a medical context, for instance, this would allow for the optimal “escalation” of diagnostic procedures from “low-cost/small-gain” evidence (e.g., measuring the patient’s blood pressure) to “high-cost/large-gain” evidence (e.g., performing an MRI scan).

{% hint style="info" %}
See Examples & Learn More

* [Chapter 6: Supervised Learning](https://www.bayesia.com/articles/bayesialab-knowledge-hub/6-supervised-learning)
* [Webinar: Diagnosis & Repair Optimization](https://www.bayesia.com/articles/bayesialab-knowledge-hub/diagnosis-repair-optimization-with-bayesian-networks)
{% endhint %}

#### WebSimulator&#x20;

* The [BayesiaLab WebSimulator](https://www.bayesia.com/articles/bayesialab-knowledge-hub/websimulator) is a platform for publishing interactive models and [Adaptive Questionnaires ](https://www.bayesia.com/articles/bayesialab-knowledge-hub/inference-adaptive-questionnaire)via the web, which means that any Bayesian network built with BayesiaLab can be shared privately with clients or publicly with a broader audience.
* Once a model is published via the WebSimulator, end users can try out scenarios and examine the dynamics of that model.

#### Code Export&#x20;

* [Batch Inference](https://www.bayesia.com/articles/bayesialab-knowledge-hub/inference-batch-inference) is available for automatically performing inference on many records in a dataset. For example, [Batch Inference](https://www.bayesia.com/articles/bayesialab-knowledge-hub/inference-batch-inference) can be used to produce a predictive score for all customers in a database.
* With the same objective, BayesiaLab’s optional [Code Export Module](https://www.bayesia.com/smart/bayesialab/network-network-export) can translate predictive network models into static code that can run in external programs. Modules are available that can generate code for R, SAS, PHP, VBA, Python, and JavaScript.

#### Bayesia Engine API&#x20;

* Developers can also access many of BayesiaLab’s functions—outside the graphical user interface—by using the [Bayesia Engine API](https://www.bayesia.com/articles/bayesialab-knowledge-hub/bayesia-engine-api).
* The Bayesia Modeling Engine allows you to construct and edit networks.
* The Bayesia Inference Engine can access network models programmatically for performing automated inference, e.g., as part of a real-time application with streaming data.
* Finally, the Bayesia Learning Engine gives you programmatic access to BayesiaLab's discretization and learning algorithms.
* The Bayesia Engine APIs are implemented as pure Java class libraries (jar files), which can be integrated into any software project.

{% hint style="info" %}
See Examples & Learn More

* [Bayesia Engine API Documentation](https://www.bayesia.com/articles/bayesialab-knowledge-hub/bayesia-engine-api)
* [Tech Talk: Epidemic Modeling with Bayesian Networks](https://www.bayesia.com/articles/bayesialab-knowledge-hub/epidemic-modeling-with-bayesian-networks)
{% endhint %}
