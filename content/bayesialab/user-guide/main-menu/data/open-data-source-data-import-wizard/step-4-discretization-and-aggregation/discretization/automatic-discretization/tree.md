# Tree

### Context

* Tree is one of the [Automatic Discretization](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-automatic-discretization) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation) of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).

### Algorithm Details & Recommendations

* Tree is a bivariate discretization method. It machine-learns a decision tree that uses the to-be-discretized variable for representing the conditional probability distributions of the Target variable given the to-be-discretized variable. Once the Tree is learned, it is analyzed to extract the most useful thresholds.
* It is the method of choice in the context of Supervised Learning, i.e., if you plan to machine-learn a model to predict the Target variable.
* At the same time, we do not recommend using Tree in the context of Unsupervised Learning. The Tree algorithm creates bins that are biased toward the designated Target variable. Naturally, emphasizing one particular variable would run counter to the intent of Unsupervised Learning.
* Note that if the to-be-discretized variable is independent of the selected Target variable, it will be impossible to build a tree, and BayesiaLab will prompt you to select a univariate discretization algorithm.
* All manually discretized variables can be used as a Target variable for Tree discretization.

{% hint style="danger" %}
Using a Target variable for Discretization does not create a Target Node in the network.&#x20;
{% endhint %}
