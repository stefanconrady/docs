# Chapter 9: Missing Values Processing

### Introduction&#x20;

Missing values are encountered in virtually all real-world data collection processes. Missing values can result from non-responses in surveys, poor record-keeping, server outages, attrition in longitudinal surveys, faulty sensors of a measuring device, etc. Despite the intuitive nature of this problem and the fact that almost all quantitative studies are affected by it, applied researchers have given it remarkably little attention in practice. [Burton and Altman (2004)](https://pubmed.ncbi.nlm.nih.gov/15188004/) state this predicament very forcefully in the context of cancer research: “We are concerned that very few authors have considered the impact of missing covariate data; it seems that missing data is generally either not recognized as an issue or considered a nuisance that it is best hidden.”

Given the abundance of “big data” in the field of analytics, missing values processing may not be a particularly fashionable topic. After all, who cares about a few missing data points if there are many more terabytes of observations waiting to be processed? One could be tempted to analyze complete data only and remove all incomplete observations. Regardless of how many more complete observations might be available, this naive approach would almost certainly lead to misleading interpretations or create a false sense of confidence in one’s findings.

Koller and Friedman (2009) provide an example of a hypothetical medical trial that evaluates the efficacy of a drug. In this trial, patients can drop out, in which case their results are not recorded. If patients withdraw at random, there is no problem ignoring the corresponding observations. On the other hand, if patients prematurely quit the trial because the drug does not seem to help them, discarding these observations introduces a strong bias in the efficacy evaluation. As this example illustrates, it is important to understand the mechanism that produces the missingness, i.e. the conditions under which some values are not observed.

As missing values processing — beyond the naive ad hoc approaches — can be a demanding task, both methodologically and computationally. Traditionally, the process of specifying an imputation model has been a scientific modeling effort on its own, and few non-statisticians dared to venture into this specialized field [(van Buuren, 2007)](https://doi.org/10.1177%2F0962280206074463).&#x20;

With Bayesian networks and BayesiaLab, handling missing values properly now becomes feasible for researchers who might otherwise not attempt to deal with missing values beyond the ad hoc approaches. Responding to Burton and Altman’s serious concern, we believe that the presented methods can help missing values processing become an integral part of more research projects in the future.&#x20;

We have already mentioned missing values processing several times in earlier chapters, as it is one of the steps in the Data Import Wizard. However, we have delayed a formal discussion of the topic until now because the recommended missing values processing methods are tightly integrated with BayesiaLab’s learning algorithms. Indeed, all of BayesiaLab’s core functions for learning and inference are prerequisites for successfully applying missing values processing. With all the building blocks in place, we can now explore this subject in detail.

### Types of Missingness&#x20;

Four principal types of missing values are typically encountered in research:

{% content-ref url="missing-completely-at-random-mcar.md" %}
[missing-completely-at-random-mcar.md](missing-completely-at-random-mcar.md)
{% endcontent-ref %}

{% content-ref url="missing-at-random-mar.md" %}
[missing-at-random-mar.md](missing-at-random-mar.md)
{% endcontent-ref %}

{% content-ref url="missing-not-at-random-mnar.md" %}
[missing-not-at-random-mnar.md](missing-not-at-random-mnar.md)
{% endcontent-ref %}

{% content-ref url="filtered-values.md" %}
[filtered-values.md](filtered-values.md)
{% endcontent-ref %}

1. [Missing Completely at Random (MCAR)](missing-completely-at-random-mcar.md)
2. [Missing at Random (MAR)](missing-at-random-mar.md)
3. [Missing Not at Random (MNAR)](missing-not-at-random-mnar.md) or Not Missing at Random (NMAR). Both of these equivalent expressions, MNAR and NMAR, appear equally frequently in the literature. We use MNAR throughout this chapter.
4. [Filtered Values](filtered-values.md)

We can explain each of these conditions with the following causal Bayesian network. It illustrates:

* the data-generating process (DGP);
* the mechanism that causes the missingness;
* the observable variables that contain the missing values.

### Reference Network Model

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690932671/MissingValuesX1X2X3X4X5_rc30d1.svg" alt=""><figcaption></figcaption></figure>

### Generating a Test Dataset&#x20;

We use this reference network to simulate all missingness conditions and generate a test dataset from it for subsequent evaluation:

* [Learn about Generating the Test Dataset](missing-values-processing-in-bayesialab/generating-the-test-dataset.md)

With such a test dataset, the problems associated with missingness become very obvious. Given that we have specifically encoded all types of missingness mechanisms in the reference network, the resulting test dataset is a kind of worst-case scenario, which is ideal for testing purposes.

However, before we can apply any missing values processing methods, we need to bring the test dataset into BayesiaLab. While the [Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/) is explained in detail in the BayesiaLab User Guide (see [Open Data Source](../../user-guide/main-menu/data/open-data-source-data-import-wizard/)), we quickly summarize the steps in the following sub-topics:

* [Importing the Test Dataset into BayesiaLab](missing-values-processing-in-bayesialab/importing-the-test-dataset-into-bayesialab.md)

### Missing Values Processing in BayesiaLab&#x20;

Once imported into BayesiaLab, we attempt to recover the reference network's original distributions from the test dataset.

In a typical data analysis workflow in BayesiaLab, a researcher encounters Missing Values Processing in [Step 3 of the Data Import Wizard](../../user-guide/main-menu/data/open-data-source-data-import-wizard/step-3-data-selection-filtering-and-missing-value-processing.md), i.e., when importing a dataset. So, we evaluate each available Missing Values Processing method in the context of a prototypical workflow.

* [Filter (Listwise/Casewise Deletion)](missing-values-processing-in-bayesialab/filter-listwise-casewise-deletion.md)
* [Replace By (Mean/Modal Imputation)](missing-values-processing-in-bayesialab/replace-by-mean-modal-imputation.md)
* [Infer — Static Imputation](missing-values-processing-in-bayesialab/infer-static-imputation.md)
* [Infer — Dynamic Imputation](missing-values-processing-in-bayesialab/infer-dynamic-imputation.md)
* [Infer — Structural EM](missing-values-processing-in-bayesialab/infer-structural-em.md)
* [Infer — Entropy-Based Imputations](missing-values-processing-in-bayesialab/infer-entropy-based-imputations.md)
* [Approximate Dynamic Imputation](missing-values-processing-in-bayesialab/approximate-dynamic-imputation.md)

Each of the above methods yields an imputed dataset. Now we can examine how well the imputed datasets match the distributions from the reference model. We explore the advantages and disadvantages of each method on this basis.&#x20;

Ultimately, this assessment of approaches is meant as a guide for choosing a Missing Values Processing method as a function of what we know about the data-generating process and the missingness mechanism in particular.

{% hint style="danger" %}
Before we even present results, we need to warn you that some of the to-be-evaluated methods, such as [Filter (Listwise/Casewise Deletion)](missing-values-processing-in-bayesialab/filter-listwise-casewise-deletion.md) and [Replace By (Mean/Modal Imputation)](missing-values-processing-in-bayesialab/replace-by-mean-modal-imputation.md), are not recommended for default use. We still include them for two reasons: first, they are almost universally used in statistical analysis, and second, under certain circumstances, they can be safe to use. Regardless of their suitability for research, they can help us understand the challenges of missing values processing.
{% endhint %}
