# Perturbed Tree

### Context

* Perturbed Tree is one of the [Automatic Discretization](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-automatic-discretization) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation) of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).

### Algorithm Details & Recommendations

* The Perturbed Tree algorithm is designed to optimize the representation of the probabilistic dependency between a Target variable and the to-be-discretized variable. It is an extension of the [Tree](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-tree) discretization algorithm, and it functions as follows:
  * [Data Perturbation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/16318954) generates a range of datasets.
  * For each perturbed dataset, a univariate tree is learned to predict the Target variable with the to-be-discretized continuous variable.
  * Extracting the most frequent thresholds produces the final discretization.
* The Perturbed Tree algorithm takes into account the Minimum Interval Weight and can reduce the number of bins if necessary. It can also be more robust than the simple [Tree](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/discretization-tree) discretization.
