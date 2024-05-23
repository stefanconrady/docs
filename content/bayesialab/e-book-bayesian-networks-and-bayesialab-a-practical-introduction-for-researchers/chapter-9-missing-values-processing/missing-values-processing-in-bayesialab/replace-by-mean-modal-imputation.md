# Replace By (Mean/Modal Imputation)

As opposed to deletion-type methods, such as [Filter (Listwise/Casewise Deletion)](filter-listwise-casewise-deletion.md), we now consider the “opposite” approach, i.e., filling in the missing values with imputed values. Here, imputing means replacing the non-observed values with estimates in order to facilitate the analysis of the whole dataset.

In BayesiaLab, this function is available via the Replace By option. We can specify to impute any arbitrary value, e.g., based on expert knowledge or an automatically generated value. For a Continuous variable, BayesiaLab offers a default replacement of the missing values with the mean value of the variable. For a Discrete variable, the default is the modal value, i.e., the most frequently observed value of the variable. In our example, `X1_obs` has a mean value of 0.40878022. This is the value to be imputed for all missing values for `X1_obs`.

Note that Replace By can be applied variable by variable. Thus, it is possible to apply Replace By to a subset of variables only and use other methods for the remaining variables.

For the purposes of our example, we use Replace By for `X1_obs`, `X2_obs`, and `X4_obs`. As soon as this is specified, the number of the remaining missing values is updated in the Information Panel. By using the selected method, no missing values remain.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/9-Missing\_Values-web-resources/image/2015-09-19\_15-34-17.png)

In the same way, we studied the performance of Filter, we now review the results of the Replace By method. Whereas this imputation method is optimal at the individual/observation level (it is the rational decision for minimizing the prediction error), it is not optimal at the population/dataset level. The right column in the following screenshot shows that imputing all missing values with the same value has a strong impact on the shape of the distributions. Even though the mean values of the processed variables (right column) remain unchanged compared to the observed values (center column), the standard deviation is much reduced.

Similar to our verdict on [Filter (Listwise/Casewise Deletion)](filter-listwise-casewise-deletion.md), Replace By cannot be recommended either for general use. However, its application could be justified if expert knowledge were available for setting a specific replacement value or if the number of affected records were negligible compared to the overall size of the dataset.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690987365/MissingValuesProcessingReplaceBy_sdyxlr.svg" alt="" width="563"><figcaption></figcaption></figure>
