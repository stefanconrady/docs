# Smallpox Vaccine

### Context

> "Let me give you an example in which probabilities make all the difference. It echoes the public debate that erupted in Europe when the smallpox vaccine was first introduced. Unexpectedly, data showed that more people died from smallpox inoculations than from smallpox itself. Naturally, some people used this information to argue that inoculation should be banned, when in fact it was saving lives by eradicating smallpox."
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (pp. 43–44). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

### The Problem as a Bayesian Network&#x20;

* We implement this example as a Causal Bayesian network. "Causal" means that the arc directions represent causal relationships between the variables.
* You can download the XBL file and open it with any version of BayesiaLab:\
  <img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109039/xbl3_xmnk2g.svg" alt="" data-size="line"> [BoW\_VaccineSmallpox.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692034396/BoW\_VaccineSmallpox\_h2ihv6.xbl)
* In this network, the green node #Dead is a Function Node that calculates the number of children who died within a population of 1 million.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035115/Smallpox_yjdtjb.svg" alt=""><figcaption></figcaption></figure>

* We created a WebSimulator that allows you to experiment with this model and try out different scenarios: [https://simulator.bayesialab.com/#!simulator/685025884871](https://simulator.bayesialab.com/#!simulator/685025884871)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035365/WebSimulatorSmallpox_bhbmij.png" alt=""><figcaption></figcaption></figure>

### Question: Do Vaccines Kill?&#x20;

> "I can empathize with the parents who might march to the health department with signs saying, 'Vaccines kill!' And the data seem to be on their side; the vaccinations indeed cause more deaths than smallpox itself. But is logic on their side? Should we ban vaccination or take into account the deaths prevented?" (Pearl, p. 44)

#### Querying the Bayesian Network&#x20;

* We attempt to answer this counterfactual question in BayesiaLab.
* To do so, we need to set Vaccinated=False as Hard Evidence, thus simulating a counterfactual world in which no children are vaccinated.
* The Bayesian network infers that not vaccinating would cost the lives of 4,000 children, as shown in the green Function Node.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035244/Smallpox1_yvod7d.svg" alt=""><figcaption></figcaption></figure>

* To replicate the same step in the [WebSimulator](../../bayesialab-websimulator/) you need to move the slider Vaccinated=False to 100.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692035445/WebSimulatorNoVaccination_vbbbwl.gif" alt=""><figcaption></figcaption></figure>



