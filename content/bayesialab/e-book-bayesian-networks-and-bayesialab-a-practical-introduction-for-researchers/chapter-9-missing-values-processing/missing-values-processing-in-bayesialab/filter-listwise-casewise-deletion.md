# Filter (Listwise/Casewise Deletion)

BayesiaLab’s Filter method is generally known as “listwise deletion” or “casewise deletion” in the field of statistics. It is the first option listed in [Step 3 of the Data Import Wizard](../../../user-guide/main-menu/data/open-data-source-data-import-wizard/step-3-data-selection-filtering-and-missing-value-processing.md). It represents the simplest approach to dealing with missing values, and it is presumably the most commonly used one, too. This method deletes any record that contains a missing value in the specified variables.

{% hint style="danger" %}
The Filter method is not to be confused with [Filtered Values](../filtered-values.md).
{% endhint %}

The screenshot below shows Filter applied to `X1_obs` only. Given this selection, the Number of Rows, i.e., the number of cases or records in the dataset, drops from the original 10,000 to 8,950. Note that Filter can be applied variable by variable. Thus, it is possible to apply Filter to a subset of variables only and use other methods for the remaining variables.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-18\_21-20-22.png)

Before we can evaluate the effect of the Filter, we need to complete the [Data Import Wizard](../../../user-guide/main-menu/data/open-data-source-data-import-wizard/). However, given the number of times we have already presented the entire import process, we omit a detailed presentation of these steps. Instead, we fast forward to review the Monitors of the processed variables in BayesiaLab.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/9-Missing-Values-Processing/Filter-Listwise-Casewise-Deletion/MissingValuesProcessingFilter.png" alt=""><figcaption></figcaption></figure>

In the Graph Panel, the absence of the question mark icon on X1obs signals that it no longer contains any missing values.

The Monitors now show the processed distributions. However, for a formal review of the processing effects, we must compare the distributions of the newly processed variables with their unprocessed counterparts.

In the overview below, we compare the original distributions (left column), followed by the distributions corresponding to the 10,000 generated samples (center column), and the distributions produced by the application of Missing Values Processing (right column). This is the format we will employ to evaluate all missing values processing methods.

Recalling the section on [MCAR](../missing-completely-at-random-mcar.md) data, we know that applying Filter to an [MCAR](../missing-completely-at-random-mcar.md) variable should not affect its distribution. Indeed, for `X1_obs` (top right) versus `X1` (top left), the difference between the distributions is insignificant, and it is only due to the sample size. Sampling an infinite-size dataset would lead to the exact same distribution.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690985582/MissingValuesProcessingFilterX1_gvjnbt.svg" alt=""><figcaption></figcaption></figure>

Now we turn to test the application of Filter to all variables with missing values, i.e., `X1_obs`, `X2_obs`, and `X4_obs`.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/9-Missing\_Values-web-resources/image/2015-09-19\_20-31-05.png)

Even before evaluating the resulting distributions, we see in the Information Panel that over half of the rows of data are being deleted due to applying Filter. It is easy to see that in a dataset with more variables, this could quickly reduce the number of remaining records—potentially down to zero. In a dataset in which not a single record is completely observed, Filter is obviously not applicable at all.

The following illustration presents the final distributions (right column), which are all substantially biased compared to the originals (left column). Whereas filtering alone on `X1_obs`, an [MCAR](../missing-completely-at-random-mcar.md) variable, was at least “safe” for `X1_obs` by itself, filtering on `X1_obs`, `X2_obs`, and `X4_obs`, adversely affects all variables, including `X1_obs` and even `X3_obs`, which does not contain any missing values.

As a result, we must strongly advise against using this method within BayesiaLab or in any statistical analysis unless it is certain that all to-be-deleted incomplete observations correspond to missing values that have been generated completely at random ([MCAR](../missing-completely-at-random-mcar.md)). Another exception would be if the to-be-deleted observations only represented a very small fraction of all observations. Unfortunately, these caveats are rarely observed, and the Filter method, i.e., listwise or casewise deletion, remains one of the most commonly used methods of dealing with missing values ([Peugh and Enders, 2004](https://journals.sagepub.com/doi/10.3102/00346543074004525)).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690986754/MissingValuesProcessingFilter_vww9h8.svg" alt="" width="563"><figcaption></figcaption></figure>
