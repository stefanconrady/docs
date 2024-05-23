# Normalized Mutual Information

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

Based on [Mutual Information](https://bayesia.clickhelp.co/articles/bayesialab/key-concepts-mutual-information), Normalized Mutual Information includes a normalization factor:

$$
\frac{1}{{{{\log }_2}({S_X})}}
$$

where $$S_X$$ denotes the number of states of $$X$$.

This means that the Mutual Information $$I(X,Y)$$ is divided by the maximum possible entropy of $$X$$, i.e., $${\log _2}({S_X})$$.

With that, the formal definition of Normalized Mutual Information is:

$$
{I_N}(X,Y) = \frac{{I(X,Y)}}{{{{\log }_2}({S_X})}}
$$

### Usage <a href="#h2_519852009" id="h2_519852009"></a>

* BayesiaLab reports the Normalized Mutual Information in the Target Analysis Report: `Main Menu > Analysis > Report > Target > Relationship with Target Node`.
* Note that this table shows the Normalized Mutual Information of each node, e.g., XRay, Dyspnea, etc., with regard to the Target Node, Cancer.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/Normalized-Mutual-Information/TargetAnalysisReportNormalizedMutualInformation.png" alt=""><figcaption></figcaption></figure>

* The Normalized Mutual Information can also be shown by selecting `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information` and then clicking the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) or selecting `Main Menu > View > Show Arc Comments`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690814445/VisitAsiaArcNMI_kkn59x.svg" alt="" width="563"><figcaption></figcaption></figure>

* Note that the corresponding options under `Main Menu > Preferences > Analysis > Visual Analysis > Arc's Mutual Information Analysis` have to be selected first:\
  ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/PreferencesMutualInformation.svg)
* In Preferences, Child refers to the Normalized Mutual Information from the Parent onto the Child node, i.e., in the direction of the arc.
* Conversely, Parent refers to the Normalized Mutual Information from the Child onto the Parent node, i.e., in the opposite direction of the arc.
