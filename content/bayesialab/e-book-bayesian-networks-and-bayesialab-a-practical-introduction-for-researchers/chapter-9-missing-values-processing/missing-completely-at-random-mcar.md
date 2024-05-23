# Missing Completely at Random (MCAR)

Missing Completely at Random (MCAR) means that the missingness mechanism is entirely independent of all other variables. In our causal Bayesian network, we encode this independent mechanism with a boolean variable named `MCAR_X1`.

Furthermore, we assume that there is a variable `X1` that represents the original data-generating process. This variable, however, is hidden, so we cannot observe it directly. Rather, we can only observe `X1` via the variable `X1_obs`, which is a “clone” of `X1` but with one additional state, “?”, which indicates that the value of `X1` is not observed.

The Bayesian network shown below is a subnetwork of the complete network presented above. The behavior of the three variables we just described is encoded in this subnetwork.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690933206/MCARX1_sqtc3t.svg" alt="" width="375"><figcaption></figcaption></figure>

In addition to this qualitative structure, we need to describe the quantitative part, i.e., the parameters of this subnetwork, including the missingness mechanism and the observable variable:

* `X1` is a continuous variable with values between 0 and 1. We have arbitrarily defined a Normal distribution for modeling the DGP.
* `MCAR_X1` is a boolean variable without any parent nodes. This means that `MCAR_X1` is independent of all variables, whether hidden or not. Its probability of being true is 10%.
* `X1_obs` has two parents: the data-generating variable `X1` and the missingness mechanism `MCAR_X1` . The following deterministic rule defines the conditional probability distribution of `X1_obs: IF MCAR_X1  THEN X1_obs =? ELSE  X1_obs = X1`&#x20;

Now that our causal Bayesian network is fully specified, we can evaluate the impact of the missingness mechanism on the observable variable X1obs. Given that we have created a complete model of this small domain, we automatically have perfect knowledge of the distribution of `X1`. Thus, we can directly compare `X1` and `X1_obs` via the Monitors.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690933905/MissingValuesProcessingX1_walbsy.svg" alt=""><figcaption></figcaption></figure>

We see that `X1` (left) and `X1_obs` (center) have the same mean and the same standard deviation. This suggests that the remaining observations in `X1_obs` (center) are not different from the non-missing cases in `X1` (left). The only difference is that `X1_obs` (center) has one additional state (“?”) for missing values, representing 10% of the observations. Thus, deleting the missing observations of an MCAR variable should not bias the estimation of its distribution. In BayesiaLab, we can simulate this assumption by setting negative evidence on “?” (green arrow labeled “Delete”). As we can see, the distribution of `X1_obs` (right) is now exactly the same as the one of `X1` (left).

Under real-world conditions, however, we typically do not know whether the missing values in our dataset were generated completely at random (MCAR). This would be a strong assumption to make, and it is generally not testable. As a result, we can rarely rely on this fairly benign condition of missingness and, thus, should never be too confident in deleting missing observations.
