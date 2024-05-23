# Symmetric Normalized Mutual Information

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

The following Venn Diagram illustrates that the Mutual Information is symmetrical for the two variables $$X$$ and $$Y$$, i.e., $$I(X,Y)=I(Y,X)$$.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690816003/MutualInformationVennDiagram_mgzpes.svg" alt="" width="375"><figcaption></figcaption></figure>

However, the variables $$X$$ and $$Y$$can each have a different number of states. Therefore, their respective entropies can be very different.

This means that the absolute value of Mutual Information cannot be interpreted without context. In the Venn Diagram, for instance, $$I(X|Y)$$ reduces $$H(Y)$$ by a bigger percentage than does $$H(X)$$. As such, $$I(X,Y)$$ would be more "important" with regard to $$Y$$ than it would be with regard to $$X$$.

### Definition <a href="#h2__634660619" id="h2__634660619"></a>

The Symmetric Normalized Mutual Information measure takes the difference of the respective entropies of X and Y into account:

$$
{I_{SN}}(X,Y) = 2 \times \frac{{I(X,Y)}}{{{{\log }_2}({S_X}) + {{\log }_2}({S_Y})}}
$$

As a result, we have an easy-to-interpret measure that relates to both $$X$$ and $$Y$$ together.

### Usage <a href="#h2_519852009" id="h2_519852009"></a>

For a given network, BayesiaLab can report the Symmetric Normalized Mutual Information in several contexts:

* `Main Menu > Analysis > Report > Relationship Analysis`:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/Information-Theory/Mutual-Information/Symmetric-Normalized-Mutual-Information/RelationshipAnalysisReportSNMI.png" alt=""><figcaption></figcaption></figure>

* The Symmetric Normalized Mutual Information can also be shown by selecting `Main Menu > Analysis > Visual > Overall > Arc > Mutual Information` and then clicking the Show Arc Comments icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184178/BayesiaLab\_Icons/arc-comment\_rkga6a.svg) or selecting `Main Menu > View > Show Arc Comments`.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690816429/VisitAsiaArcSymmetricMutualInformation_qiwqjw.svg" alt="" width="375"><figcaption></figcaption></figure>

* Note that the corresponding options under `Preferences > Analysis > Visual Analysis > Arc's Mutual Information Analysis` have to be selected first:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690813804/PreferencesMutualInformation_sqrlhf.svg" alt=""><figcaption></figcaption></figure>

* In Preferences, Child refers to the Relative Mutual Information from the Parent onto the Child node, i.e., in the direction of the arc.
* Conversely, Parent refers to the Relative Mutual Information from the Child onto the Parent node, i.e., in the opposite direction of the arc.
