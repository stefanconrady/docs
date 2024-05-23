# Importing the Test Dataset into BayesiaLab

We show the first two steps of the [Data Import Wizard](../../../user-guide/main-menu/data/open-data-source-data-import-wizard/) only for reference, as their options have already been discussed in previous chapters.

Our test dataset consisting of 10,000 records was saved as a CSV file, so we start the import process via `Main Menu > Data > Open Data Source > Text File`.

### Step 1: Data Structure Definition <a href="#h2__223960219" id="h2__223960219"></a>

Note the missing values in columns `X1_obs`, `X2_obs`, and `X4_obs` in the Data Panel. Column `X5_obs` features Filtered Values, which are marked with an asterisk (\*).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-18\_15-48-28.png)

### Step 2: Definition of Variable Types <a href="#h2_399967883" id="h2_399967883"></a>

The next step of the [Data Import Wizard](../../../user-guide/main-menu/data/open-data-source-data-import-wizard/) requires no further input, but we can review the statistics provided in the Information Panel: we have 5,547 missing values (=11.09% of all cells in the Data panel) and 1,364 Filtered Values (=2.73%).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-18\_20-49-02.png)

### Step 3: Data Selection, Filtering, and Missing Values Processing <a href="#h2__396120353" id="h2__396120353"></a>

The next screen brings us to the core task of selecting the Missing Values Processing method. In the screenshot, the default option Structural EM is pre-selected, but we will explore all options systematically from the top. The default method can be specified under `Main Menu > Window > Preferences > Data > Import & Associate > Missing & Filtered Values`.&#x20;

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-18\_21-02-16.png)

We explain and evaluate each Missing Values Processing method separately. Please select the topic below or open it in the navigation bar.

* [Filter (Listwise/Casewise Deletion)](filter-listwise-casewise-deletion.md)
* [Replace By (Mean/Modal Imputation)](replace-by-mean-modal-imputation.md)
* [Infer — Static Imputation](infer-static-imputation.md)
* [Infer — Dynamic Imputation](infer-dynamic-imputation.md)
* [Infer — Structural EM](infer-structural-em.md)
* [Infer — Entropy-Based Imputations](infer-entropy-based-imputations.md)
* [Approximate Dynamic Imputation](approximate-dynamic-imputation.md)
