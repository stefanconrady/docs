# Unsupervised Multivariate

### Context

* Unsupervised Multivariate is one of the [Automatic Discretization](./) algorithms for Continuous variables in [Step 4 — Discretization and Aggregation](../../) of the [Data Import Wizard](../../../).
* This multivariate discretization method is based on analyzing the relationship between variables.&#x20;

### Algorithm Details & Recommendations

* The Unsupervised Multivariate discretization algorithm focuses on representing multivariate probabilistic dependencies using Random Forests.
* Its functionality can be described as follows:
  * A new dataset is created as a clone of the original one.
  * In this new dataset, each variable is independently shuffled to render all the variables independent while keeping the same statistics for each variable.
  * The cloned dataset is concatenated with the original dataset. Then, a target variable is created to differentiate the clone from the original, indicating the independent set versus the original dependent set.
  * Various datasets are generated from this concatenated dataset with Data Perturbation.
  * For each perturbed dataset, a multivariate tree is learned to predict the target variable with a subset of variables. If a structure is already defined, it is used to bias the selection of the variables for each dataset.
  * Extracting the most frequent thresholds produces the discretization.
  * Being based on Random Forests, this algorithm is computationally expensive and stochastic by nature, specifically when the number of variables is important.
* The Unsupervised Multivariate discretization algorithm is also available after the data import via `Main Menu > Learning > Discretization`.
* However, it is not available in the Node Editor (`Node Context Menu > Edit > Curve > Generate a Discretization`).
