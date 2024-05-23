# Breast Cancer

### Context

> "Subjectivity (Ed, i.e., the prior) is sometimes seen as a deficiency of Bayesian inference. Others regard it as a powerful advantage; it permits us to express our personal experience mathematically and combine it with data in a principled and transparent way. Bayes’s rule informs our reasoning in cases where ordinary intuition fails us or where emotion might lead us astray. We will demonstrate this power in a situation familiar to all of us.
>
> Suppose you take a medical test to see if you have a disease, and it comes back positive. How likely is it that you have the disease? For specificity, let’s say the disease is breast cancer, and the test is a mammogram."
>
> [Pearl, Judea. The Book of Why: The New Science of Cause and Effect (pp. 104-105). Basic Books. Kindle Edition.](https://amzn.to/322imYl)

### Representing the Problem Domain as a Bayesian Network&#x20;

* We implement this example as a causal Bayesian network, which means the arc between Breast Cancer and Mammogram represents a causal relationship.
* The resulting Bayesian network in XBL format is available here:\
  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) [BoW\_BreastCancer.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692037449/BoW\_BreastCancer\_wxq5hp.xbl)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692037586/BreastCancer_obhkuj.svg" alt="" width="375"><figcaption></figcaption></figure>

* You can also experiment with this model via our WebSimulator: [https://simulator.bayesialab.com/#!simulator/186824514911](https://simulator.bayesialab.com/#!simulator/186824514911)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692037677/WebSimulatorBreastCancer_ussnmm.png" alt=""><figcaption></figcaption></figure>

### Should I worry about a positive test result?&#x20;

> "Suppose a forty-year-old woman gets a mammogram to check for breast cancer, and it comes back positive. The hypothesis, D (for “disease”), is that she has cancer. The evidence, T (for “test”), is the result of the mammogram. How strongly should she believe the hypothesis? Should she have surgery?" (Pearl, p. 105)

### Calculating the Cancer Risk with BayesiaLab&#x20;

* We use the probabilities described by Pearl to set the parameters of the Causal Bayesian Network:
  * For a typical forty-year-old woman, the probability of getting breast cancer in the next year is about one in seven hundred, 0.14%. We use that as our prior;
  * The sensitivity (true-positive) of a mammogram is 73%;
  * The specificity (true-negative) of a mammogram is 88%.
* Notice the Input component Breast Cancer—Your Prior Estimate in the [WebSimulator](https://simulator.bayesialab.com/#!simulator/186824514911). This allows you to set your own initial belief that a patient has breast cancer.
* Upon setting Mammogram=Positive as Hard Evidence, the probability of Breast Cancer=True increases from 0.14% to 0.86%.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692037977/BreastCancerMammogramPositive_s2k04l.mp4" %}

### Counterintuitive Results&#x20;

> "The conclusion is startling. I think that most forty-year-old women who have a positive mammogram would be astounded to learn that they still have less than a 1 percent chance of having breast cancer. Figure 3.3 might make the reason easier to understand: the tiny number of true positives (i.e., women with breast cancer) is overwhelmed by the number of false positives."(Pearl, p. 106)

### Should I worry now?&#x20;

> "However, the story would be very different if our patient had a gene that put her at high risk for breast cancer—say, a one-in-twenty chance within the next year. \[...]
>
> For a woman in this situation, the chances that the test provides lifesaving information are much higher. That is why the task force continued recommending annual mammograms for high-risk women.
>
> This example shows that P(disease | test) is not the same for everyone; it is context-dependent (Ed: it depends on the prior). If you know that you are at high risk for a disease to begin with, Bayes’s rule allows you to factor that information in. Or if you know that you are immune, you need not even bother with the test!" (Pearl, pp. 107–108)

### Recalculating the Risk&#x20;

* To answer this question with BayesiaLab, you can either modify the model by setting the prior of Breast Cancer to 5% via the Node Editor, or you can set a Probabilistic Evidence via the Monitor.
* In the WebSimulator, you would set the Input Breast Cancer—Your Prior Estimate (initial belief) to 5%.
* Upon setting Mammogram=Positive, the probability of Breast Cancer=True increases to 24.25%.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692037978/BreastCancerWebSimulatorMammogramPositiveHyperParameter_btdqpm.mp4" %}

### Visualizing the Impact of the Prior

* To illustrate the impact of the prior (or prevalence), we added a parent node to Breast Cancer for defining such prior. This is what we call a "hyperparameter."
* The updated network, including the hyperparameter, is available here:  \
  ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) [BoW\_BreastCancer\_Prevalence.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692038302/BoW\_BreastCancer\_Prevalence\_ukupai.xbl)
* You can now set Mammogram=Positive as Hard Evidence.
* With this evidence set, you can use Target Mean Analysis to explore a range of values for the prior, from 0% to 100%: `Main Menu > Analysis > Visual > Target > Target's Posterior > Curves > Total Effects`.
* You will obtain a plot in which the x-axis represents the prior of Breast Cancer=True, i.e., the hyper-parameter.
* The y-axis represents the updated probability of Breast Cancer=True given a positive mammogram result.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692037978/BreastCancerBayesiaLabMammogramPositiveHyperParameter_rfv7kw.mp4" %}
