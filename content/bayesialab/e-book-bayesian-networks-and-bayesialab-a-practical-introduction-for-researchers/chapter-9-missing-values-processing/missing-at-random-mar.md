# Missing at Random (MAR)

Secondly, data can be Missing at Random (MAR). Here, the missingness of data depends on observed variables. A brief narrative shall provide some intuition for the MAR condition: in a national survey of small business owners about the business climate, there is a question about the local cost of energy. Chances are that the owner of a business that uses little electricity, e.g., a yoga studio, may not know of the current cost of 1 kWh of electric energy and could not answer that question, thus producing a missing value in the questionnaire. On the other hand, the owner of an energy-intensive business, e.g., an electroplating shop, would presumably be keenly aware of the electricity price and able to respond accordingly. In this story, the probability of non-response is presumably inversely proportional to the energy consumption of the business.

In the subnetwork shown below, `X3_obs` is the observed variable that causes the missingness, e.g., the energy consumption in our story. `X2_obs` would be the stated price of energy if known. `X2` would represent the actual price of energy in our narrative. Indeed, from the researcher’s point of view, the actual cost of energy in each local market and for each electricity customer is hidden.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690934520/MARX2_ewyyck.svg" alt="" width="375"><figcaption></figcaption></figure>

To simulate this network, we need to define its parameters, i.e., the quantitative part of the network structure:

* `X2` is a continuous variable with values between 0 and 1. Here, too, we have arbitrarily defined a Normal distribution for modeling the DGP.
* `MAR_X2` is a boolean variable with one parent, which specifies that the missingness probability depends directly on the fully observed variable `X3_obs`. The exact values are not important here, as we only need to know that the probabilities of missingness are inversely proportional to the values of `X3_obs`:

$$
P(MA{R_{X2}} = true|X{3_{obs}}) \propto \frac{1}{{X{3_{obs}}}}
$$

* `X2_obs` has two parents, i.e., the data-generating variable `X2` and the missingness mechanism `MAR_X2`. The conditional probability distribution of `X2_obs` can be described by the following deterministic rule: `IF MAR_X2 THEN X2_obs=? ELSE X2_obs=X2`

Given the fully specified network, we can now simulate the impact of the missingness mechanism on the observable variable `X2_obs`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690934653/MissingValuesProcessingX2_y24fh1.svg" alt=""><figcaption></figcaption></figure>

As the above screenshot shows, the mean and standard deviation in the Monitor of `X2_obs` indicates that the distribution of the observed values of `X2` differs significantly from the original distribution, leading to an overestimation of `X2` in this example. We can simulate the deletion of incomplete observations by setting negative evidence on “?” in the Monitor of `X2_obs` (green arrow labeled “Delete”). The simulated distribution of `X2_obs` (right) clearly differs from the one of `X2` (left).
