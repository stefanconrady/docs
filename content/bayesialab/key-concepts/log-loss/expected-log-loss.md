# Expected Log-Loss

### Context&#x20;

The **Log-Loss** $$LL(E)$$ reflects the number of bits required to encode an n-dimensional piece of evidence (or observation) $$E$$ given the current Bayesian network $$B$$. As a shorthand for "the number of bits required to encode," we use the term "cost" in the sense that "more bits required" means computationally "more expensive."

$$L{L_B}(E) = - {\log _2}\left( {{P_B}(E)} \right),$$

where $$PB(E)$$ is the joint probability of the evidence $$E$$ computed by the network $$B$$:

Furthermore, one of the key metrics in Information Theory is [Entropy](../entropy/):

$$H(X) = - \sum\limits_{x \in X} {p(x){{\log }_2}\left( {p(x)} \right)}$$

As a result, Entropy can be considered the sum of the **Expected Log-Loss** values of each state $$x$$ of variable $$X$$ given network $$B$$.

$$H(X) = \sum\limits_{x \in X} {L{L_x}}$$

where

$$L{L_x} = - {p_B}(x){\log _2}\left( {{p_B}(x)} \right)$$

### Usage&#x20;

To illustrate these concepts, we use the familiar Visit Asia network:

[VisitAsia.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1690489585/VisitAsia\_yyelir.xbl)

In BayesiaLab, the **Expected Log-Loss** values can be shown in the context of the Monitors.

#### Monitors&#x20;

We consider the nodes $$Dyspnea$$ and $$Bronchitis$$ in the VisitAsia.xbl network.

* On the left, the Monitors of the two nodes show their marginal distributions.
* On the right, we set $$p\left( {Bronchities = True} \right) = 100\%$$, which updates the probability of $$Dyspnea$$, i.e., $$p\left( {Dyspnea = True} \right) = 80.54\%$$.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Log-Loss/VisitAsiaProbabilities.svg" alt="" width="563"><figcaption></figcaption></figure>

* On the Monitor of $$Dyspnea$$, we now select `Monitor Context Menu > Show Expected Log-Loss` that the **Expected Log-Loss** values for the states of $$Dyspnea$$ are shown instead of their probabilities.
* This is an interesting example because setting $$Bronchitis=True$$ does reduce the Entropy of $$Dyspnea=True$$, but does not seem to change the Expected Log-Loss of $$Dyspnea=False$$.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Log-Loss/VisitAsiaExpectedLogLoss.svg" alt="" width="563"><figcaption></figcaption></figure>

#### Visual Illustration

The following plot illustrates $$H(Dyspnea)$$, $$LL(Dyspnea=True)$$, and $$LL(Dyspnea=False)$$. For a compact representation in the plot, we substituted $$X$$ for $$Dyspnea$$.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Log-Loss/Expected-Log-Loss/Entropy2.svg" alt=""><figcaption></figcaption></figure>

In this binary case, the curves show how the $$Entropy H(X)$$ can be decomposed into $$LL(x=True)$$ and $$LL(x=False)$$.

The blue curve also confirms that the **Expected Log-Loss** values are identical for the two probabilities of $$Dyspnea=False$$, i.e., 80.54% and 42.52%.

* $$LL(p(Dyspnea=False)=1-0.1946=0.8054)=0.459$$
* $$LL(p(Dyspnea=False)=1-0.5748=0.4252)=0.459$$&#x20;

#### Monitor Tooltip&#x20;

Instead of replacing the states' probabilities with the Expected Log-Loss values in a Monitor, you can bring up the  Expected Log-Loss values ad hoc as a Tooltip.

* Click on the Information Mode icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184081/BayesiaLab\_Icons/tooltip\_tndtk6.svg) in the Toolbar.&#x20;
* Then, when you hover over any Monitor with your cursor, a Tooltip shows the Expected Log-Loss values.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Log-Loss/Expected-Log-Loss/ExpectedLogLossTooltip.svg" alt="" width="563"><figcaption></figcaption></figure>

### Workflow Animation&#x20;

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1690490570/VisitAsiaExpectedLogLoss_sm8dlp.mp4" %}
