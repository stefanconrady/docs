# Infer — Static Imputation

Static Imputation resembles the [Replace By (Mean/Modal Imputation)](replace-by-mean-modal-imputation.md) method but differs in three important aspects:

The buttons under Infer are available whenever a variable with missing values is selected in the Data Panel.

1. While [Replace By (Mean/Modal Imputation)](replace-by-mean-modal-imputation.md) is deterministic, Static Imputation performs random draws from the marginal distributions of the observed data and saves these randomly drawn values as “placeholder values.”
2. The imputation is only performed internally, and BayesiaLab still “remembers” exactly which observations are missing.
3. Whereas [Replace By (Mean/Modal Imputation)](replace-by-mean-modal-imputation.md) can be applied to individual variables, any of the options under Infer apply to all variables with missing values, with the exception of those that have already been processed by [Filter (Listwise/Casewise Deletion)](filter-listwise-casewise-deletion.md) or [Replace By (Mean/Modal Imputation)](replace-by-mean-modal-imputation.md).

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/9-Missing\_Values-web-resources/image/2015-09-19\_17-21-50.png)

Although this probabilistic imputation method is not optimal at the observation/individual level (it is not the rational decision for minimizing the prediction error), it is optimal at the dataset/population level.

As illustrated below, drawing the imputed values from the current distribution keeps the distributions of variables pre and post-processing the same. As a result, Static Imputation returns distributions that match the ones produced by [Filter (Listwise/Casewise Deletion)](filter-listwise-casewise-deletion.md) but without deleting any observations. As no records are discarded, Static Imputation does not introduce any additional biases. However, the distributions of X2 ([MAR](../missing-at-random-mar.md)) and X4 ([MNAR](../missing-not-at-random-mnar.md)) remain strongly biased.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690987693/MissingValuesProcessingStaticImputation_vz4ceb.svg" alt="" width="563"><figcaption></figcaption></figure>
