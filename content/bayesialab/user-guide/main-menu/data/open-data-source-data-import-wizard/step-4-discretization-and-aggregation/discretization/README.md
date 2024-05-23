# Discretization

### Context

* The Discretization screen is part of [Step 4 — Discretization and Aggregation](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-discretization-aggregation) within the [Data Import Wizard](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/open-data-source).&#x20;
* This screen is only available if you designated at least one Continuous variable in [Step 2 — Definition of Variable Types](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-definition-variable-types).
* BayesiaLab requires the discretization of all Continuous variables, and in this screen, you need to specify how to discretize those variables.
* The Discretization process determines how a Continuous variable will be imported into BayesiaLab, i.e.,&#x20;
  * the number of intervals (or bins);&#x20;
  * the values of the thresholds which define the ranges of the intervals.
* These attributes define the transformation of the underlying Continuous variable in the dataset into a discretized Continuous node in BayesiaLab.

{% hint style="info" %}
To learn more about the important distinction between Continuous and Discrete nodes, please see these topics:

* Continuous Nodes
* Discrete Nodes
{% endhint %}

### Usage

* Select one or more Continuous variables and click into one of the headers or one of the corresponding columns.
* The Discretization panel appears.
* At the bottom of the screen, the Data panel carries over from [Step 3 — Data Selection, Filtering, and Missing Value Processing](https://bayesia.clickhelp.co/articles/bayesialab-knowledge-hub/data-import-wizard-data-selection-filtering-missing-values-processing), although now without any options.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689814131/DataImportWizard-4-DiscretizationContinuous_gcqhmb.png" alt=""><figcaption></figcaption></figure>

### Discretization Types Overview

* The first item in the Discretization panel is the Discretization Type drop-down menu.&#x20;
* The items on this list can be grouped into Automatic Discretization versus Manual Discretization.
  * The bottom item on the drop-down menu, Manual, refers to a Manual Discretization approach in which you have full control over thresholds, etc.
  * The remaining eleven items all refer to different kinds of Automatic Discretization.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689814219/DataImportWizard-4-DiscretizationType_csdz15.png" alt=""><figcaption></figcaption></figure>

* However, even in Manual Discretization, you take advantage of the algorithms available with Automatic Discretization.&#x20;

### Discretization Types in Detail

* Manual Discretization
* Automatic Discretization
