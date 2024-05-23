# Filtered Values

There is a fourth type of missingness, which is less often mentioned in the literature. In BayesiaLab, we refer to missing data of this kind as Filtered Values (see also [Filtered Values in Chapter 5](../chapter-5-bayesian-networks-and-data/)). In fact, Filtered Values are technically not missing at all. Rather, Filtered Values are values that do not exist in the first place. Clearly, something nonexistent cannot become missing due to a missingness mechanism.

For instance, in a hotel guest survey, a question about one’s satisfaction with the hotel swimming pool cannot be answered if the hotel property does not have a swimming pool. This question is not applicable. The absence of a swimming pool rating for this hotel would not be a missing value. On the other hand, for a hotel with a swimming pool, the absence of an observation would be a missing value.

Conceptually, Filtered Values are quite similar to [Missing at Random (MAR)](missing-at-random-mar.md) values, as Filtered Values usually depend on other variables in the dataset, too, which may or may not be fully observed. However, Filtered Values should never be processed as missing values. In our example, it is certainly not reasonable to impute a value for the swimming pool rating if there is no swimming pool. Rather, a Filtered Value should be considered a special type of observation.

In BayesiaLab, an additional state, marked with a chequered icon, is added to this type of variable in order to denote Filtered Values (BayesiaLab’s learning algorithms implement a kind of local selection for excluding the observations with Filtered Values while estimating the probabilistic relationships). The following illustration shows an example of a network including Filtered Values.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690936177/FilteredValuesX5_ssjcyi.svg" alt="" width="375"><figcaption></figcaption></figure>

Once again, we must describe the parameters of the subnetwork, including the Filtered Values mechanism and the observable variable:

* `Filter_X5` is a boolean variable with one parent, which specifies that it depends on the hidden variable `X4`. Here, `X5` becomes a Filtered Value if `X4` is greater than 0.7.
* `X5` is a continuous variable with values between 0 and 1. It has two parents, `X4` and the Filtered Values mechanism: `IF Filter_X5 THEN X5=Filtered Value ELSE X5=f(X4)`
* `X5_obs` is a pure clone of `X5`, i.e., `X5` is fully observed: `X5_obs=X5`

For the sake of completeness, we present the Monitors of `X5` (left) and `X5_obs` (right):

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690936317/MissingValuesProcessingX5_abcqj5.svg" alt="" width="563"><figcaption></figcaption></figure>
