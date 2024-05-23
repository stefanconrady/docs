# Relative Mutual Information

### Definition&#x20;

Based on [Mutual Information](./), Relative Mutual Information is defined as:

$$
{I_R}\left( {X,Y} \right){\rm{ }} = {\rm{ }}{{I\left( {X,Y} \right)} \over {H\left( X \right)}}
$$

Relative Mutual Information expresses in percent how much the entropy (or uncertainty) of $$X$$ is reduced by observing $$Y$$.&#x20;

{% hint style="warning" %}
In older versions of BayesiaLab, Relative Mutual Information was also called Normalized Mutual Information.

Please see the up-to-date definition of Normalized Mutual Information.  \

{% endhint %}

### Usage&#x20;

* BayesiaLab reports the Relative Mutual Information in the Target Analysis Report: `Main Menu > Analysis > Report > Target > Relationship with Target Node`.
* Note that this table shows the Relative Mutual Information of each node, e.g., XRay, Dyspnea, etc., only with regard to the Target Node, Cancer.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab-knowledge-hub/Information-Theory/Mutual-Information/Relative-Mutual-Information/TargetAnalysisReportRelativeMutualInformation.png" alt=""><figcaption></figcaption></figure>

* The Relative Mutual Information can also be shown by selecting `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information` and then clicking the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) or selecting `Main Menu > View > Show Arc Comments`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690815669/VisitAsiaArcRMI_woiame.svg" alt="" width="375"><figcaption></figcaption></figure>

* Note that the corresponding options under `Preferences > Analysis > Visual Analysis > Arc's Mutual Information Analysis` have to be selected first:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690813804/PreferencesMutualInformation_sqrlhf.svg" alt=""><figcaption></figcaption></figure>

* In Preferences, Child refers to the Relative Mutual Information from the Parent onto the Child node, i.e., in the direction of the arc.
* Conversely, Parent refers to the Relative Mutual Information from the Child onto the Parent node, i.e., in the opposite direction of the arc.
