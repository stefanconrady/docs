# Missing Not at Random (MNAR)

{% hint style="info" %}
Missing Not at Random (MNAR) or Not Missing at Random (NMAR) are equivalent expressions; MNAR and NMAR appear equally frequently in the literature. We use MNAR throughout this chapter.
{% endhint %}

Missing Not at Random (MNAR) refers to situations in which the missingness of a variable depends on hidden causes (unobserved variables), such as the data-generating variable itself. This condition is depicted in the subnetwork below.

An example of the MNAR condition would be a hypothetical telephone survey about alcohol consumption. Heavy drinkers might decline to provide an answer out of fear of embarrassment. On the other hand, survey participants who drink very little or nothing at all might readily report their actual drinking habits. As a result, the missingness is a function of the very variable in which we are interested.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/E-Book/9-Missing-Values-Processing/Types-of-Missingness/MNAR/MNARX4.svg" alt="" width="375"><figcaption></figcaption></figure>

In order to proceed to simulation, we need to specify the parameters of the missingness mechanism and the observable variable:

* `X4` is a continuous variable with values between 0 and 1, and a Normal distribution models the DGP.
* `MNAR_X4` is a boolean variable with one parent, which specifies that the missingness probability depends directly on the hidden variable X4. However, the exact values are unimportant. We need to state that the probabilities of missingness are proportional to the values of `X4`:

$$
P(MA{R_{X4}} = true|X4) \propto X4
$$

* `X4_obs` has two parents, i.e., the data-generating variable `X4` and the missingness mechanism `MNAR_X4`.&#x20;
* The following deterministic rule defines the conditional probability distribution: `IF MNAR_X4 THEN X4_obs=? ELSE X4_obs=X4`

The impact of the mechanism of the missing value becomes apparent as we compare the Monitors of the network side by side.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690935807/MissingValuesProcessingX4_shwyfm.svg" alt=""><figcaption></figcaption></figure>

As the above screenshot shows, the mean and standard deviation in the Monitor of `X4_obs` (center column) indicate that the distribution of the observed values of `X4` differs significantly from the original distribution (left column), leading to an underestimation of `X4` in this example. We can simulate the deletion of incomplete observations by setting negative evidence on “?” (green arrow labeled “Delete”). The simulated distribution of `X4_obs` (right column) indeed differs from the one of `X4` (left column).
