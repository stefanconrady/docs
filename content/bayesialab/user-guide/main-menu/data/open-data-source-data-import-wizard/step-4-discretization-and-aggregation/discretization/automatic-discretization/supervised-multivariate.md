# Supervised Multivariate

### Context

* Supervised Multivariate is one of the [Automatic Discretization](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-automatic-discretization) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation) of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).

### Algorithm Details & Recommendations

* The Supervised Multivariate discretization algorithm focuses on representing the multivariate probabilistic dependencies involving a Target variable.
* It utilizes Random Forests to find the most useful thresholds for predicting the Target variable.
* Its function can be summarized as follows:
  * [Data Perturbation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/16318954) generates a range of datasets.
  * For each perturbed dataset, a multivariate tree is learned to predict the Target variable with a subset of variables. If a structure is already defined, it is used to bias the selection of the variables for each dataset.
  * Extracting the most frequent thresholds produces the final discretization.
* The Supervised Multivariate takes into account the Minimum Interval Weight and can improve the generalization capability of the model.
* Being based on Random Forests, this algorithm is computationally expensive and stochastic by nature.
* After the conclusion of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source), the Supervised Multivariate discretization algorithm is also available from `Main Menu > Learning > Discretization`.
* Not that the Supervised Multivariate discretization algorithm is not available via `Node Context Menu > Node Editor > States > Curve > Generate a Discretization`.
