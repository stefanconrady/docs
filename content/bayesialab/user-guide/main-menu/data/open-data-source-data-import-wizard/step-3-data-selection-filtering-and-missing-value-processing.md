# Step 3 — Data Selection, Filtering, and Missing Value Processing

### ﻿​Context

* Step 3 of the five-step Data Import Wizard deals with Data Selection, Filtering, and Missing Values Processing.

### Overview of Elements <a href="#h2__772583257705084832" id="h2__772583257705084832"></a>

* [Missing Values Processing](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_\_273572749869204528)
* [Information](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_\_2101430728869204528) (same as in [Step 2 — Definition of Variable Types](about:blank/data-import-wizard-definition-variable-types.html#h2\_\_2101430728\_1387816040))
* [Select Values](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_\_536365532869204528)
* [Data](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_2620942869204528)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689811344/DataImportWizard-3_etfjjg.png" alt=""><figcaption></figcaption></figure>

### Data

We start with the Data panel — although it is at the bottom of the window — as it can help inform decisions about [Missing Values Processing](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_\_956560667869204528).

This Data panel resembles the Data panel from Step 2 — Definition of Variable Types.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689811384/DataImportWizard-3-DataPanel_u4i7w2.png" alt=""><figcaption></figcaption></figure>

However, there are several important additional pieces of information available:

* A Missing Values icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184179/BayesiaLab\_Icons/database-missing-value\_tisskz.svg) indicates the presence of at least one Missing Value in the corresponding variable.
* A triangle icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184161/BayesiaLab\_Icons/console-down\_shro08.svg) indicates that variable-specific statistics are available. It appears on all variable headers with the exception of variables of the type [Row Identifier](about:blank/data-import-wizard-definition-variable-types.html#h4\_1049110101\_1387816040) and [Unused](about:blank/data-import-wizard-definition-variable-types.html#h3\_\_426962452\_1387816040).
* Clicking on the triangle icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184161/BayesiaLab\_Icons/console-down\_shro08.svg) or the associated variable header brings up a table with variable statistics:
  * For Discrete variables, it shows the frequencies of all states, including Missing Values and Filtered Values:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689811706/DataImportWizard-3-DataPanelStatisticsDiscrete_ra9y4j.png" alt=""><figcaption></figcaption></figure>

* The Filter checkboxes ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184225/BayesiaLab\_Icons/checkbox-true\_kfgr1b.svg) allow you to uncheck/deselect specific values.
* The checked box ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184225/BayesiaLab\_Icons/checkbox-true\_kfgr1b.svg) means that the value is included, which is the default condition.
* The unchecked box ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184225/BayesiaLab\_Icons/checkbox-unchecked1\_zekl2b.svg) means that the value is excluded and that all rows​ that contain that value will be filtered, i.e., removed.
* As you experiment with checking/unchecking, you can see how the Number of Rows in the Information panel changes.



{% hint style="info" %}
In terms of a data query, the Filter checkbox would be the equivalent of a nominal value row filter.
{% endhint %}

{% hint style="warning" %}
Note that the number of Filtered Values does not refer to the number of excluded rows due to an unchecked Filter checkbox.
{% endhint %}

* For Continuous variables, it shows the standard statistics, such as Minimum, Maximum, Mean, and Standard Deviation. Additionally, the table displays the frequencies of non-missing values, Missing Values, and Filtered Values:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812034/DataImportWizard-3-DataPanelStatisticsContinuous_cckoi5.png" alt=""><figcaption></figcaption></figure>

### Select Values <a href="#h2__536365532705084832" id="h2__536365532705084832"></a>

The Select Values panel relates to the [Filter](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#Filter869204528) checkboxes plus any [Required Minima and Maxima](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#MinimumMaximum869204528) applied in the [Data](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_2620942869204528) panel.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812109/DataImportWizard-3-SelectValuesPanel_pby3kq.png" alt=""><figcaption></figcaption></figure>

Three actions are available in this panel:

* You can choose the logic for combining the Filters and Minima/Maxima assigned in the Data panel:
  * OR: a row will be removed if ANY of the selected Filters or specified Minima/Maxima across all variables apply to that row.
  * AND: a row will only be removed of ALL of the selected Filters and specified Minima/Maxima across all variables that apply to that row.&#x20;
* Click the Show Selections button to review what Filters and Minima/Maxima are currently in place.
* Note the syntax for Discrete variables: The variable name is followed by "in" (i.e., is an element of) followed by the included values shown as an array in square brackets.
* Further logical expressions are shown as conjunctions (AND) or disjunctions (OR) in separate lines.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812171/DataImportWizard-3-SelectValuesUsedSelections_rvsxko.png" alt=""><figcaption></figcaption></figure>

* Clicking the Delete Selections button removes all Filters and Minima/Maxima currently in place.

### Missing Values Processing <a href="#h2__956560667705084832" id="h2__956560667705084832"></a>

In the Missing Value Processing panel you can specify which kind of processing to apply to variables with Missing Values, i.e., Filter, Replace, and Infer.

This panel is only active if you select one of the variables that feature a small question mark icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184179/BayesiaLab\_Icons/database-missing-value\_tisskz.svg). This icon indicates that the corresponding variable contains at least one Missing Value.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812245/DataImportWizard-3-MissingValuesPanel_dkkicv.png" alt=""><figcaption></figcaption></figure>

#### Filter <a href="#h3__1623789156705084832" id="h3__1623789156705084832"></a>

The Filter function allows you to remove rows from the dataset that contain Missing Values. This is equivalent to what is commonly known as casewise deletion.

You can apply the Filter individually to any variable that contains Missing Values.

**Usage**

* In the [Data](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h2\_2620942869204528) panel, click on the header or into the column of the variable with Missing Values.&#x20;
* Then, check the Filter checkbox in the Missing Values Processing panel.
* Next, choose the logical condition to apply when you select multiple variables to be subject to the Filter.
  * OR: a row will be removed if ANY of the selected variables contain a Missing Value in that row.
  * AND: a row will only be removed of ALL of the selected variables containing a Missing Value in that row.



{% hint style="warning" %}
Before applying Filter, please consider the implications discussed in Chapter 9: Missing Values Processing.
{% endhint %}

#### Replace By <a href="#h3__1949240721705084832" id="h3__1949240721705084832"></a>

With the Replace By function, you can specify a value for replacing the Missing Values in the selected variable.

You have several options in this regard:

* You can set a specific value:
  * For a Discrete variable, you can select among the values observed in the variable from a drop-down list.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812432/DataImportWizard-3-ReplaceByValue_g0hlkw.png" alt=""><figcaption></figcaption></figure>

* Alternatively, you can choose the Modal value, i.e., the most frequently occurring value of the variable in the dataset.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812469/DataImportWizard-3-ReplaceByModal_v2hyw0.png" alt=""><figcaption></figcaption></figure>

* For a Continuous variable, you can select to use the Mean value computed from the dataset.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812500/DataImportWizard-3-ReplaceByMean_kdl4um.png" alt=""><figcaption></figcaption></figure>

* As an alternative, you can specify any arbitrary value.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1689812538/DataImportWizard-3-ReplaceByValueContinuous_pkzh0k.png" alt=""><figcaption></figcaption></figure>

#### Infer <a href="#h3_1460672510705084832" id="h3_1460672510705084832"></a>

For practical analysis purposes, the Infer option is the most common method for Missing Values Processing.

To learn about Missing Values Processing beyond [Filter](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h3\_\_1623789156869204528) and [Replace By](about:blank/data-import-wizard-data-selection-filtering-missing-values-processing.html#h3\_\_1949240721869204528), please see Missing Values Processing in Chapter 9 of our e-book.

**The Methods in Detail:**

* Infer — Static Imputation
* Infer — Dynamic Imputation
* Infer — Structural EM
* Infer — Entropy-Based Imputations

### Information <a href="#h2__2101430728705084832" id="h2__2101430728705084832"></a>

The Information panel is identical in its functionality to the Information panel in [Step 2 — Definition of Variable Types](step-2-definition-of-variable-types.md). Please refer to that topic for details.

***

***

***
