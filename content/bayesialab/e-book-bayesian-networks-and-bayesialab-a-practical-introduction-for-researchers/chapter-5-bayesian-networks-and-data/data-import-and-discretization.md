# Data Import and Discretization

### Open Data&#x20;

As the first step, we start BayesiaLab’s [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/) by selecting `Main Menu > Data > Open Data Source > Text File`.

![BayesiaLab /](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataOpenDataSourceTextFile.png)

Then, we select the file “AmesHousePriceData.csv”, a comma-delimited, flat text file, which you can download here:

[AmesHousePriceData.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1689949828/AmesHousePriceData\_fnbm0t.csv)\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataOpenDataSourceTextFileAmes.png" alt=""><figcaption></figcaption></figure>

### Data Import Wizard&#x20;

This brings up the first screen of the [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/), which previews the to-be-imported dataset.

For this example, the coding options for Missing Values and Filtered Values are particularly important. By default, BayesiaLab lists commonly used codes that indicate an absence of data, e.g., #NUL! or NR (non-response). In the Ames dataset, a blank field (“ ”) indicates a Missing Value, and “FV” stands for Filtered Value. These are recognized automatically. If other codes were used, we could add them to the respective lists on this screen.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-1.png" alt=""><figcaption></figcaption></figure>

Clicking Next, we proceed to the screen that allows us to define variable types.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-2.png" alt=""><figcaption></figcaption></figure>

BayesiaLab scans all variables in the database and provides a best guess regarding the variable type. Variables identified as [Continuous](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-continuous-nodes) are shown in turquoise, and those identified as [Discrete](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-discrete-nodes) are highlighted in pastel red.

In BayesiaLab, a [Continuous](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-continuous-nodes) variable contains a wide range of numerical values (discrete or continuous), which need to be transformed into a more limited number of discrete states. Some other variables in the database only have very few distinct numerical values to begin with, e.g., \[1,2,3,4,5], and BayesiaLab automatically recognizes such variables as [Discrete](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-discrete-nodes). For them, the number of numerical states is small enough that creating bins of values is unnecessary. Also, variables containing text values are automatically considered Discrete.

For this dataset, however, we need to make a number of adjustments to the suggested data types. For instance, we set all numerical variables to [Continuous](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-continuous-nodes), including those highlighted in red that were originally identified as [Discrete](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-discrete-nodes). As a result, all columns in the data preview of the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source) are now shown in turquoise.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-3.png" alt=""><figcaption></figcaption></figure>

Given that our database contains some missing values, we need to select the type of Missing Values Processing in the next step. Instead of using ad hoc methods, such as pairwise or listwise deletion, BayesiaLab can leverage more sophisticated techniques and provide estimates (or temporary placeholders) for such missing values—without discarding any original data.

We will discuss Missing Values Processing in detail in [Chapter 9](../chapter-9-missing-values-processing/). For this example, however, we leave the default setting of Structural EM.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-4.png" alt=""><figcaption></figcaption></figure>

### Filtered Values&#x20;

At this point, however, we must introduce a very special type of missing value for which we must not generate any estimates. We are referring to so-called Filtered Values. These are “impossible” values that do not or cannot exist—given a specific set of evidence, as opposed to values that do exist but are not observed. For example, for a home that does not have a garage, there cannot be any value for the variable Garage Type, such as Attached to Home, Detached from Home, or Basement Garage. If there is no garage, there cannot be a garage type. As a result, it makes no sense to calculate an estimate of a Filtered Value. In a database, unfortunately, a Filtered Value typically looks identical to “true” missing value that does exist but is not observed. The database typically contains the same code, such as a blank, NULL, N/A, etc., for both cases.

Therefore, instead of “normal” missing values, which can be left as-is in the database, we must mark Filtered Values with a specific code, e.g., “FV.” The Filtered Value declaration should be done during data preparation before importing any data into BayesiaLab. BayesiaLab will then add a Filtered State (marked with “\*”) to the discrete states of the variables with Filtered Values and utilize a special approach for actively disregarding such Filtered States so that they are not taken into account during machine learning or for estimating effects.

### Discretization&#x20;

As the next step in the [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/), all [Continuous](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor-continuous-nodes) values must be discretized (or binned). We show a sequence of screenshots to highlight the necessary steps. The initial view of the Discretization and Aggregation step appears.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-5.png" alt=""><figcaption></figcaption></figure>

By default, the first column is highlighted, which happens to be SalePrice, the variable of principal interest in this example. Instead of selecting any available automatic discretization algorithms, we pick Manual from the Type drop-down menu, which brings up the Cumulative Distribution Function (CDF) of the SalePrice variable.\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-6.png" alt=""><figcaption></figcaption></figure>

By clicking Density Function, we can bring up the Probability Density Function (PDF) of SalePrice.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-7.png" alt=""><figcaption></figcaption></figure>

Either view allows us to examine the distribution and identify any salient points. We stay on the current screen to set the thresholds for each discretization bin. In many instances, we would use an algorithm to define bins automatically unless the variable will serve as the target variable. In that case, we usually rely on available expert knowledge to define the binning. In this example, we wish to have evenly-spaced, round numbers for the interval boundaries. We add boundaries by right-clicking on the plot (right-clicking on an existing boundary removes it again). Furthermore, we can fine-tune a threshold’s position by entering a precise value in the Threshold Value field. We use {75000, 150000, 225000, 300000} as the interval boundaries.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-8.png" alt=""><figcaption></figcaption></figure>

#### Tree Discretization&#x20;

Now that we have manually discretized the target variable SalePrice (column highlighted), we still need to discretize the remaining continuous variables. However, we will take advantage of an automatic discretization algorithm for those variables.

We click Select All Continuous. BayesiaLab automatically excludes SalePrice from this selection because we have already discretized it.

Numerous automatic discretization algorithms are available, but for the purpose of this example, we only consider the bivariate Tree discretization algorithm.

{% hint style="info" %}
Please see the main entry for Discretization in this library for a detailed description of all available algorithms.
{% endhint %}

As its name suggests, the Tree discretization algorithm machine-learns a decision tree that uses the to-be-discretized variable for representing the conditional probability distributions of the target variable given the to-be-discretized variable. Once the Tree is learned, it is analyzed to extract the most useful thresholds. This is the method of choice in the context of [Supervised Learning](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/learning-supervised-learning), i.e., when planning to machine-learn a model to predict the target variable.

At the same time, we do not recommend using Tree in the context of [Unsupervised Learning](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/learning-unsupervised-structural-learning). The Tree algorithm creates bins that are biased toward the designated target variable. Naturally, emphasizing one particular variable would run counter to the intent of [Unsupervised Learning](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/learning-unsupervised-structural-learning).

Note that if the to-be-discretized variable is independent of the target variable, it will be impossible to build a tree, and BayesiaLab will prompt the selection of a univariate discretization algorithm.

In this example, we focus our analysis on SalePrice, which can be considered a type of [Supervised Learning](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/learning-supervised-learning). Therefore, we discretize all continuous variables with the Tree algorithm, using SalePrice as the Target variable. Note the Target must either be a Discrete variable or a Continuous variable that has already been manually discretized, which is the case for SalePrice.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/DataImportWizard-9.png" alt=""><figcaption></figcaption></figure>

Clicking Finish completes the import process.

The import process concludes with a pop-up window that offers to display the Import Report.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/OpenImportReport.png" alt=""><figcaption></figcaption></figure>

Clicking Yes brings up the Import Report, which can be saved in HTML format. It lists the discretization intervals of the Continuous variables, the States of the Discrete variables, and the discretization method used for each variable.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/ImportReport.png" alt=""><figcaption></figcaption></figure>

### Graph Panel&#x20;

Once we close out this report, we can see the result of the import process. All the imported variables are now represented as nodes on the [Graph Panel](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel). The dashed borders of some nodes indicate that the corresponding variables were discretized during data import.

Furthermore, we can see icons that indicate the presence of Missing Values ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184111/BayesiaLab\_Icons/indicator\_missing\_value\_fygnrd.svg) and Filtered Values  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184109/BayesiaLab\_Icons/indicator\_filtered\_state\_wagk61.svg) in the respective nodes.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/GraphPanel.png" alt=""><figcaption></figcaption></figure>

The lack of warning icons on any nodes indicates that all their parameters, i.e., their marginal probability distributions, were automatically estimated upon data import.

To verify, we open the [Node Editor](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/graph-windows-graph-panel-node-editor) of SalePrice (`Node Context Menu > Edit > Probability Distribution > Probabilistic`) and check the node’s marginal distribution.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/SalePriceNodeEditorProbabilistic.png" alt=""><figcaption></figcaption></figure>

Clicking on the [Occurrences](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/node-editor-probability-distribution-occurrences) tab shows the observations per cell, which were used for the [Maximum Likelihood Estimation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/key-concepts-maximum-likelihood-estimation) of the marginal distribution.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/E-Book/5-Bayesian-Networks-and-Data/SalePriceNodeEditorOccurrences.png" alt=""><figcaption></figcaption></figure>

### Workflow Animation&#x20;

The following animation shows all the above steps in a continuous workflow.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1689958502/5-DataImportWizard_ssjb7t.mp4" %}
