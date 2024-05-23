# Confidence Intervals Report

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

* Whenever you learn a Bayesian network from a small dataset, you must consider whether the number of observations is sufficient for correctly estimating all Probability Tables and Conditional Probability Tables in the network.
* For instance, using the [Occurrences Report](occurrences-report.md), you can evaluate whether all Conditional Probability Tables in your network meet the rule-of-thumb criterion of at least 5 observations per cell.
* For a deeper analysis, BayesiaLab can produce the Confidence Intervals Report, which we discuss on this page.

#### Frequentist Parameter Estimation <a href="#h2_1105226502" id="h2_1105226502"></a>

* To understand how Confidence Intervals can be computed, we first need to explain the estimation of probabilities in the Probability Tables and Conditional Probability Tables, the so-called parameters.
* In BayesiaLab, these parameters are estimated using Maximum Likelihood, i.e., using the frequencies observed in the dataset:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709396154/Maximum-Likelihood_bjvyrn.png" alt="" width="375"><figcaption></figcaption></figure>

* where:
  * $${\hat \theta }$$ is the estimated probability,
  * $${{x_i}}$$ is the state $$i$$ of variable $$x$$,
  * $$N( \cdot )$$ represents the number of occurrences of the argument in the data set.
* So, the Parameter Estimation is straightforward and happens entirely in the background in BayesiaLab.
* As a result, we may not always be aware of what numbers gave rise to the probabilities we see in a Probability Table or Conditional Probability Table, as the following diagram illustrates:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709405115/OccurrencesProbabilityDiagram2_nbwutz.svg" alt="" width="375"><figcaption></figcaption></figure>

* So, BayesiaLab could have estimated a probability of  0.1 (or 10%) for $${x_0}$$ in numerous ways, e.g., based on a sample of 10 or 10,000: $$\frac{1}{{10}} = \frac{{1,000}}{{10,000}} = 0.1$$.
* However, in terms of our confidence in the estimate, the two approaches are not the same. Our intuition tells us that we should have more confidence in the 0.1 value calculated based on the sample of 10,000.

### Confidence Intervals <a href="#h2__134627026" id="h2__134627026"></a>

*   From Frequentist Statistics, we know how to calculate a Confidence Interval $${I_c}$$

    for a proportion in a sample, which is exactly what the parameter $${\hat \theta }$$ represents.
* BayesiaLab is using precisely the same approach for the Confidence Intervals Report.
*   So, for a Confidence Level of 95%, the Confidence Interval $${I_c}$$ is calculated as: \
    $${I_c} = \left[ {{{\hat \theta }_v} - 1.96 \cdot \frac{{\sigma (V)}}{{\sqrt N }};{{\hat \theta }_v} + 1.96 \cdot \frac{{\sigma (V)}}{{\sqrt N }}} \right]$$

    where\
    $$\sigma (V) = \sqrt {{{\hat \theta }_v}(1 - {{\hat \theta }_v})}$$
* If zero observations were observed for a given state, e.g., $$N(X = {x_0}) = 0$$, the Rule of Three would have to be used instead to produce Confidence Intervals:\
  $${I_c} = \left[ {{{\hat \theta }_v} - \frac{3}{{\sqrt N }};{{\hat \theta }_v} + \frac{3}{{\sqrt N }}} \right]$$
* However, in BayesiaLab, you can avoid resorting to this heuristic by using Uniform Prior Samples.

### Usage <a href="#h2__2045975414" id="h2__2045975414"></a>

* To illustrate the Confidence Intervals Report, we use the following network:\
  [![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) NHANES\_DEMO\_BMX.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1709405953/NHANES\_DEMO\_BMX\_yuazr9.xbl)
* Within this network, focus on the three nodes BMI, Age, and Gender:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709406516/BMIAgeGenderOccurrences2_v7ruuc.svg" alt="" width="375"><figcaption></figcaption></figure>

* Go to `Main Menu > Network > Reports > Confidence Intervals` to start the Confidence Intervals Report.
* The Confidence Interval Report window opens up.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709406604/ConfidenceIntervalsReport_amhb1a.png" alt="" width="375"><figcaption></figcaption></figure>

* At the top of the report, the Confidence Level that serves as the basis for the reported Confidence Intervals is displayed.
* Then, for each node, one table is shown.
* For each cell containing a parameter estimate, an adjacent cell to the right displays the corresponding Confidence Interval in percentage points.&#x20;
* The color-coding scheme is identical to the one used in the [Occurrences Report](occurrences-report.md)**.**
* The fields in the report are color-coded to highlight potential issues:
  * Cells with 0 Occurrences are marked with a <mark style="background-color:red;">red background</mark>.
  * Cells with 5 Occurrences are highlighted with a <mark style="background-color:yellow;">yellow background</mark>. This is generally considered the minimum acceptable number of Occurrences.
  * Cells with 40 or more Occurrences are marked with a <mark style="background-color:green;">green background</mark>.

### Options&#x20;

* You can adjust the **Confidence Level** used for this report.
* Go to `Main Menu > Window > Preferences > Tools > Statistical Tools`.
* Select the desired value from the **Confidence Level** dropdown menu.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1709406981/PreferencesToolsStatisticalToolsConfidenceLevel_lajxdc.png" alt=""><figcaption></figcaption></figure>

*   Note that your selection here also applies to all other statistical tools and tests used in BayesiaLab.

    \
