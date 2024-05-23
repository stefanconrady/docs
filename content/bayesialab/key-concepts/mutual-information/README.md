# Mutual Information

The Mutual Information $$I(X, Y)$$ measures the amount of information gained on variable $$X$$ (the reduction in the [Expected Log-Loss](https://bayesia.clickhelp.co/articles/bayesialab/key-concepts-log-loss-expected-log-loss)) by observing variable $$Y$$:

$$I(X,Y) = H(X) - H(X|Y)$$

The **Venn Diagram** below illustrates this concept:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690816003/MutualInformationVennDiagram_mgzpes.svg" alt="" width="375"><figcaption></figcaption></figure>

The Conditional Entropy $$H(X|Y)$$ measures, in bits, the [Expected Log-Loss](../log-loss/expected-log-loss.md) associated with variable $$X$$ once we have information on variable $$Y$$:

$$
H(X|Y) = - \sum\limits_{y \in Y} {p(y)\sum\limits_{x \in X} {p(x|y){{\log }_2}} } \left( {p(x|y)} \right)
$$

Hence, the Conditional Entropy is a key element in defining the Mutual Information between $$X$$ and $$Y$$.

Note that

$$
I(X,Y) = H(X) - H(X|Y)
$$

is equivalent to:

$$
I(X,Y) = \sum\limits_{x \in X} {\sum\limits_{y \in Y} {p(x,y){{\log }_2}} } {{p(x,y)} \over {p(x)p(y)}}
$$

and furthermore equivalent to:

$$
I(X,Y) = \sum\limits_{y \in Y} {p(y)\sum\limits_{x \in X} {p(x|y){{\log }_2}} } {{p(x|y)} \over {p(x)}}
$$

This allows computing the Mutual Information between any two variables.

### Usage <a href="#h2_519852009" id="h2_519852009"></a>

For a given network, BayesiaLab can report the Mutual Information in several contexts:

* `Main Menu > Analysis > Report > Target > Relationship with Target Node`.
* Note that this table shows the Mutual Information of each node, e.g., XRay, Dyspnea, etc., only with regard to the Target Node, Cancer.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/TargetAnalysisReportMutualInformation.png" alt=""><figcaption></figcaption></figure>

* `Main Menu > Analysis > Report > Relationship Analysis`:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/RelationshipAnalysisReportMI.png" alt=""><figcaption></figcaption></figure>

* The Mutual Information can also be shown by selecting `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information` and then clicking the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) or selecting `Main Menu > View > Show Arc Comments`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690813694/VisitAsiaArcMI_isd10n.svg" alt="" width="375"><figcaption></figcaption></figure>

* Note that the corresponding options under `Preferences > Analysis > Visual Analysis > Arc's Mutual Information Analysis` have to be selected first:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690813804/PreferencesMutualInformation_sqrlhf.svg" alt=""><figcaption></figcaption></figure>

* In Preferences, Child refers to the Relative Mutual Information from the Parent onto the Child node, i.e., in the direction of the arc.
* Conversely, Parent refers to the Relative Mutual Information from the Child onto the Parent node, i.e., in the opposite direction of the arc.
