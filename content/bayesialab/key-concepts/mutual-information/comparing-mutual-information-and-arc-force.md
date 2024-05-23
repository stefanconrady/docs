# Comparing Mutual Information and Arc Force

### Mutual Information <a href="#h2_1240489188" id="h2_1240489188"></a>

The [Mutual Information](./) between two variables $$X$$ and $$Y$$ is defined as follows:

$$
I(X,Y)=\sum_{x \in X}\sum_{y \in Y} p(x,y)\log_2 \frac{p(x,y)}{p(x)p(y)}
$$

### Arc Force  <a href="#h2_720999677" id="h2_720999677"></a>

The Kullback-Leibler Divergence (or KL Divergence) is used to measure the strength of the relationship between two nodes that are directly connected by an arc.&#x20;

We commonly refer to the KL Divergence as Arc Force.

Formally, ​the Kullback-Leibler Divergence $${D_{KL}}$$ measures the difference between two distributions $$P$$ and $$Q$$.

$$
D_{KL}(P({\cal X})\|Q({\cal X}))=\sum_{\cal X}P({\cal X})log_2\frac{P({\cal X})}{Q({\cal X})}
$$

For our purposes, we consider $$P$$ the Bayesian network that does include the arc for which we wish to compute the Arc Force, and $$Q$$ the Bayesian network that does not contain that arc but is otherwise identical.

We interpret this difference $${D_{KL}}$$ as the "force of the arc" or Arc Force.

### Comparing Mutual Information and Arc Force <a href="#h2__1815622978" id="h2__1815622978"></a>

Mutual Information can be rewritten as:

$$I(X,Y)=D_{KL}(p(x,y)\|p(x)p(y))$$

Therefore, Mutual Information $$I$$ and Arc Force $${D_{KL}}$$  are identical if there are no spouses (co-parents) involved in the relationship of interest.

### Example 1 <a href="#h2_1330111217" id="h2_1330111217"></a>

Let's consider the following network consisting of two nodes, _X_ and _Z_.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XZ.svg" alt="" width="563"><figcaption></figcaption></figure>

The Conditional Probability Table associated with the node Z is defined as follows:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XZCPT.svg" alt=""><figcaption></figcaption></figure>

We now analyze this relationship in terms of Mutual Information in Validation Mode using `Main Menu > Analysis > Visual > Overall > Arc > Arcs' Mutual Information` and click on the Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) in the Toolbar.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XZMI.svg)

The top number in the box shows the Mutual Information $$I$$.

The bottom number in the box is Symmetric Normalized Mutual Information $${I_{SN}}$$.

$$
{I_{SN}}(X,Y) = 2 \times \frac{{I(X,Y)}}{{{{\log }_2}({S_X}) + {{\log }_2}({S_Y})}}
$$

Next, we now analyze this relationship in terms of Arc Force using `Main Menu > Analysis > Visual > Overall > Arc > Kullback-Leibler` and, again, click on the Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) in the Toolbar.\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XZKL.svg" alt="" width="563"><figcaption></figcaption></figure>

The top number in the box shows the Arc Force $${D_{KL}}$$.

The bottom number, in blue, represents the relative weight of this arc compared to the sum of all Arc Forces in the network. Given that this network consists only of one arc, this arc's weight accounts for 100%.

So, for now, both analyses return the same value, i.e., 0.3436. As we stated above, Mutual InformationI and Arc Force $${D_{KL}}$$are identical with regard to an arc if no spouses (co-parents) are involved in the relationship of interest.&#x20;

### Example 2 <a href="#h2_1330111218" id="h2_1330111218"></a>

However, as soon as we have spouses (co-parents) involved, the Arc Force provides a more comprehensive characterization of the relationship.

Let's consider the following deterministic example, in which node Z represents an Exclusive-OR (XOR) gate with regard to its inputs X and Y.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XYZ.svg" alt="" width="563"><figcaption></figcaption></figure>

The Truth Table associated with the node Z is defined as follows:\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XYZCPT.svg" alt=""><figcaption></figcaption></figure>

We now analyze this relationship in terms of Mutual Information in Validation Mode using `Main Menu > Analysis > Visual > Overall > Arc > Arcs' Mutual Information` and click on the Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) in the Toolbar.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XYZMI.svg" alt="" width="563"><figcaption></figcaption></figure>

We can easily validate this assessment by simulating evidence for X and Y individually.

<div data-full-width="true">

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690823425/XYZEvidenceScenarios_nyjht2.svg" alt=""><figcaption></figcaption></figure>

</div>

Indeed, there is no impact of either X and Y on Z.

### Comparison with Arc Force (Kullback-Leibler Divergence) <a href="#h2__1079107754" id="h2__1079107754"></a>

Next, we now analyze this relationship in terms of Arc Force using `Main Menu > Analysis > Visual > Overall > Arc > Kullback-Leibler` and, again, click on the Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) in the Toolbar.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/ComparingMutualInformationArcForce/XYZKL.svg" alt="" width="563"><figcaption></figcaption></figure>

The Arc Force, which takes into account the network as a whole, reveals the perfectly-deterministic relationship between X, Y, and Z.
