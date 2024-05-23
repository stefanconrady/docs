# Symmetric Relative Mutual Information

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

Symmetric Relative Mutual Information computes the percentage of information gained by observing $$X$$ and $$Y$$:

$$
{I_{SR}}(X,Y) = \frac{{I(X,Y)}}{{\sqrt {H(X) \times H(Y)} }}
$$

This normalization is calculated similarly to Pearson's Correlation Coefficient $$\rho$$.

$$
{\rho _{X,Y}} = \frac{{{\mathop{\rm cov}} (X,Y)}}{{\sqrt {\sigma _X^2\sigma _Y^2} }}
$$

where $$\sigma ^2$$ denotes variance.

So, [Mutual Information](./) is comparable to covariance, and [Entropy](../entropy/) is analogous to variance.

### Usage <a href="#h2_519852009" id="h2_519852009"></a>

For a given network, BayesiaLab can report the Symmetric Relative Mutual Information in several contexts:

* `Main Menu > Analysis > Report > Relationship Analysis`:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/Symmetric-Relative-Mutual-Information/RelationshipAnalysisReportSRMI.png" alt=""><figcaption></figcaption></figure>

* The Symmetric Normalized Mutual Information can also be shown by selecting `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information` and then clicking the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) or selecting `Main Menu > View > Show Arc Comments`.&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690817083/VisitAsiaArcSymmetricRelativeMutualInformation_yakyvn.svg" alt="" width="375"><figcaption></figcaption></figure>

* Note that the corresponding options under `Preferences > Analysis > Visual Analysis > Arc's Mutual Information Analysis` have to be selected first:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690813804/PreferencesMutualInformation_sqrlhf.svg" alt=""><figcaption></figcaption></figure>

* In Preferences, Child refers to the Relative Mutual Information from the Parent onto the Child node, i.e., in the direction of the arc.
* Conversely, Parent refers to the Relative Mutual Information from the Child onto the Parent node, i.e., in the opposite direction of the arc.
