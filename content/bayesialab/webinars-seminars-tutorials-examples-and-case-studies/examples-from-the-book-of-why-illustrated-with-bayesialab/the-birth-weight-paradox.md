# The Birth-Weight Paradox

### Context

> "In the mid-1960s, Jacob Yerushalmy pointed out that a mother’s smoking during pregnancy seemed to benefit the health of her newborn baby, if the baby happened to be born underweight."
>
> Pearl, Judea. The Book of Why: The New Science of Cause and Effect (p. 183). Basic Books. Kindle Edition.

### The Paradox Illustrated&#x20;

* We implemented this counterintuitive example as a causal Bayesian network, which means the arcs represent causal relationships.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050126/BoW_SmokingNB_u0p61p.svg" alt="" width="375"><figcaption></figcaption></figure>

* Since the problem's description in the book is purely qualitative, and no data is available, we associated arbitrary probability distributions with the nodes. Although arbitrary, we specified the probabilities so that the network produces the paradoxical behavior described by Pearl.
* You can download this Bayesian network in XBL format and open it with any version of BayesiaLab:\
  [![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1692036394/xbl3\_xmnk2g.svg) BoW\_SmokingNewBorns.xbl](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1692050160/BoW\_SmokingNewBorns\_p8bl11.xbl)
* Alternatively, you can experiment with this model using our WebSimulator: [https://simulator.bayesialab.com/#!simulator/115411982911](https://simulator.bayesialab.com/#!simulator/115411982911)

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050247/WS_SmokingNB1_x6eky3.png" alt=""><figcaption></figcaption></figure>

* The birth-weight paradox can be highlighted with two observations:
  *   Babies of smokers have a lower birth weight than babies of non-smokers. \


      <figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050357/547_qoax2o.png" alt="" width="375"><figcaption></figcaption></figure>
  *   Low-birth-weight babies of smoking mothers have a higher survival rate compared to those of non-smokers.&#x20;

      <figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050357/547_2_mygrqg.png" alt="" width="563"><figcaption></figcaption></figure>

### The Paradox Resolved&#x20;

> "Smoking may be harmful in that it contributes to low birth weight, but certain other causes of low birth weight, such as serious or life-threatening genetic abnormalities, are much more harmful. There are two possible explanations for low birth weight in one particular baby: it might have a smoking mother, or it might be affected by one of those other causes." (Pearl, pp. 184–185)

* In other words, Low-Birth-Weight is a collider in the structure Smoking Mother → Low-Birth-Weight ← Birth Defect.
* By observing Low-Birth-Weight, we open a noncausal ("back-door") path between Smoking Mother and Mortality of Child, which gives rise to the paradox. Please see our discussion of the [Back-Door Criterion](the-back-door-criterion/) for more details on noncausal paths.
*   In BayesiaLab, we can illustrate what happens by highlighting all information paths:

    * Set Mortality of Child as Target Node.
    * Set evidence on Low-Birth-Weight.
    * Select Smoking Mother. Then, run `Main Menu > Analysis > Visual > Graph > Influence Paths to Target`.
    * Now, all influence paths are visible.



    <figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050564/BirthWeightInfluencePaths_bkqibj.png" alt=""><figcaption></figcaption></figure>
* If we observe Smoking Mother=False, this explains away Low-Birth Weight=True and reduces the probability of Birth Defect=True;
* On the other hand, if we observe Smoking Mother=False, the probability of Birth Defect=True increases, and the probability of Mortality of Child=True increases, too.​​​

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1692050636/BirthWeightParadox_bmm2u6.mp4" %}

* Alternatively, we can use the [WebSimulator](../../bayesialab-websimulator/) to replicate these two scenarios:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050798/WS_SmokingNB2a_vfajey.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1692050720/WS_SmokingNB2_dn8sfp.png" alt=""><figcaption></figcaption></figure>
