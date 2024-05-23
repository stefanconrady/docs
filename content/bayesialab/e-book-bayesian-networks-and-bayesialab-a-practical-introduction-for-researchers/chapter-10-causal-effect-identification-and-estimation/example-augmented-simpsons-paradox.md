# Example: Augmented Simpson's Paradox

Now that we have seen how to estimate the Average Causal Effect by manually interacting with the BayesiaLab's Monitors, with both [Graph Surgery](causal-identification-and-estimation/effect-estimation/graph-surgery.md) and Likelihood Matching, we will use the BayesiaLab's Direct and Total Effect functions to compute causal effects automatically for a set of variables. But first, we present a slightly more complex version of Simpson's Paradox to illustrate these features (see [Example: Simpson's Paradox](example-simpsons-paradox.md)).

### Augmented Simpson's Paradox

Our updated story contains four additional dimensions:

* Treatment Availability: the treatment is not always available;&#x20;
* Side Effects: the treatment may produce severe side effects;
* Efficacy: some patients do not respond to the drug;
* Litigation: the families of patients who died may sue the pharmaceutical company that had provided the treatment.

The manually designed CDAG shown below describes this new domain qualitatively:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691177306/CDAGAugmentedSimpsonParadox_ek1c5x.svg" alt="" width="188"><figcaption></figcaption></figure>

Next, we describe the quantitative part of the domain. First, we state that Treatment Availability is 75%.&#x20;

We also assume that the treatment may have Side Effects, which are much more frequent for females. The following conditional probability table quantifies this direct causal dependency on Gender:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691177007/AugmentedSimpsonParadoxSideEffects_xl8huw.svg" alt="" width="375"><figcaption></figcaption></figure>

Patients decide whether or not to take the treatment based on two criteria, Treatment Availability and Side Effects. The dependencies are described in the following table. It states that if the treatment is unavailable, patients cannot have the treatment, which is deterministic (and obvious). However, if the treatment is available, those patients who do not have any risk of experiencing side effects will always choose the treatment, while those at risk will be unlikely to submit to the treatment:&#x20;

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691178208/AugmentedSimpsonParadoxTreatmentSideEffects_sf8msa.svg" alt="" width="375"><figcaption></figcaption></figure>

Furthermore, the Efficacy of the treatment depends on Drug Administration plus some hidden factors that render the treatment ineffective in 20% of patients:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691178563/AugmentedSimpsonParadoxDrugAdminEfficacy_k557g8.svg" alt="" width="375"><figcaption></figcaption></figure>

The Target Node, Outcome, is defined by Gender and Efficacy. In this context, "not recovered" means that the patient died — hence the grim illustration attached to the icon.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691180496/AugmentedSimpsonGenderEfficacyOutcome_jrxhqg.svg" alt="" width="375"><figcaption></figcaption></figure>

Finally, half of the families of those patients who took the treatment and died are pursuing litigation. More specifically, these families are suing the pharmaceutical company that provided the treatment.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691180835/AugmentedSimpsonDrugAdminOutcomeLitigation_dbgtzz.svg" alt="" width="375"><figcaption></figcaption></figure>

### Path Analysis <a href="#h4__1137334463" id="h4__1137334463"></a>

We now list the paths between each variable and the target variable Outcome by using `Main Menu > Analysis > Visual > Graph > Influence Paths to Target`.&#x20;

The causal paths are highlighted in blue (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg)), and the non-causal paths (i.e., paths with at least one "backward" arrow ←) are shown in pink (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg)):

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691161991/Augmented-Simpson-Paradox-Path-List_s4511c.svg" alt="" width="563"><figcaption></figcaption></figure>

Recall the [Adjustment Criterion](causal-identification-and-estimation/graphical-identification-criteria.md#h3\_676963991), which stipulates that we must keep all of a variable's causal paths to the target variable open and simultaneously block all its non-causal paths for estimating its causal effect. &#x20;

### Graph Surgery <a href="#h3__1253194919" id="h3__1253194919"></a>

To illustrate BayesiaLab's Total and Direct Effects functions with [Graph Surgery](causal-identification-and-estimation/effect-estimation/graph-surgery.md), we set all nodes but Outcome to Intervention Mode.\


<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691181424/ASP-GS-All-Intervention_khd6yo.svg" alt="" width="188"><figcaption></figcaption></figure>

Notice the arrow symbols (→) in the badges of the nodes that are set to Intervention Mode.

#### Average Causal Effect <a href="#h4_1875415581" id="h4_1875415581"></a>

Before using BayesiaLab's automated tools for computing causal effects, we manually estimated the causal effect of our main variable of interest, Drug Administration, by using the Monitors.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/AugmentedSimpsonMonitors1.svg) ![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/AugmentedSimpsonMonitors2.svg)

Setting a piece of Evidence in Intervention Mode simulates an intervention on Drug Administration and mutilates the graph, as shown below, which meets the Adjustment Criterion by blocking the non-causal path (cf. [Path Analysis](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h4\_\_1137334463), #6).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691181643/ASP-GS-All-Intervention2_yyb74m.svg" alt="" width="188"><figcaption></figcaption></figure>

The Average Causal Effect of Drug Administration on Outcome, mediated by Efficacy, is -0.08.&#x20;

#### Total Effects <a href="#h4_337859533" id="h4_337859533"></a>

We have seen in [Chapter 8](../chapter-8-probabilistic-structural-equation-models-for-key-driver-analysis/) that BayesiaLab estimates Total Effects as the derivatives of Total Effect Curves. These curves are based on the Posterior Mean Values of the Target Node given Mean Values from the interval of the variable under study. While the variables are in Intervention Mode, the Posterior Mean Values are computed based on the mutilated graph.

We can plot these curves with `Main Menu > Analysis > Visual > Target > Target's Posterior > Curves > Total Effects`.&#x20;

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/ASP%20GS%20Total%20Effect%20Curve.png)

For generating this graph, we can set a number of options:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/ASP%20GS%20Total%20Effect%20Curve%20Param.png)

The x-axis, Variable Delta Means, represents the difference between the Mean Value generated for the analysis (here, Hard Evidence/Intervention on the states of the variable under study) and its Prior Mean Value. The y-axis represents the difference between the PosteriorMean Value of Outcome and its PriorMean Value.&#x20;

{% hint style="info" %}
If we do not specifically associate numerical values with symbolic states, BayesiaLab uses the state index. In our example,&#x20;

* False is 0, and True is 1.
* Male is 0, and Female is 1.
* Not Recovered is 0, and Recovered is 1.&#x20;
{% endhint %}

We see that Side Effects is the only variable with a positive causal effect. We also notice that Litigation has no causal effect.&#x20;

Given that all variables are binary, the corresponding curves are linear. Therefore, the curves' derivatives will be perfect summaries of the Total Effect Curves: `Main Menu > Analysis > Report > Target > Total Effects on Target`:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Total%20Effects.png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
The [Total Effect](../../key-concepts/total-effect.md) is the derivative computed at (0, 0) in the previous Target Mean Analysis graph, i.e., the slope of the curve.\
The [Standardized Total Effect](../../key-concepts/total-effect.md#standardized-total-effect) is the Total Effect times the ratio between the standard deviation of the variable and the standard deviation of the Target Node.
{% endhint %}

The arrow symbols (→) in the results table indicate that Intervention Mode was active on all nodes, triggering Graph Surgery upon each observation/intervention during the estimation of the effects.

Gender is the variable with the strongest Total Effect. It is negative because of the index values of the states. Females (1) are recovering at a lower rate than Males (0).

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/AGS%20TE%20Gender.svg" alt=""><figcaption></figcaption></figure>

Note that there are two paths from Gender to Outcome (paths #1 and #2 illustrated in the [previous section](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h4\_\_1137334463)), and they are both causal. Gender is indeed a root node, i.e., it has no parents, meaning the Adjustment Criterion is fulfilled by default.

The Total Effect measures the effects of these two causal paths: the direct path (#1) and the indirect path (#2), represented by the dashed blue arcs below.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691181969/AGS-Paths-Gender-TE_q6yvxe.svg" alt="" width="188"><figcaption></figcaption></figure>

#### Direct Effects <a href="#h4__556073690" id="h4__556073690"></a>

Now suppose we are interested in estimating the effect of the direct paths only. This would require blocking not only the non-causal paths but also the indirect causal paths. This is the role of BayesiaLab's Direct Effect functions. The only difference between Direct and Total Effect functions is that, by default, all other nodes are held constant during the estimation of the variable's Direct Effect.&#x20;

We generate the Direct Effect Curves with `Main Menu > Analysis > Visual > Target > Target's Posterior > Curves > Direct Effects`, using the same parameters as those previously used for Total Effects:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/ASP%20GS%20Direct%20Effect%20Curve.png)

Given that all nodes are in Intervention Mode, the only variables with Direct Effects are the Parents of Outcome. Indeed, intervening on all nodes to hold them constant triggers Graph Surgery and generates the mutilated graph below:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691182069/ASP-GS-All-Intervention-Gender_led6hd.svg" alt="" width="188"><figcaption></figcaption></figure>

The function `Main Menu > Analysis > Report > Target > Direct Effects on Target` allows us to compute the Direct Effects, the single-point estimates of these curves:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Direct%20Effects.png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
* The Direct Effect is the slope of the Direct Effect Curve between the endpoints of the variable interval.
* The Standardized Direct Effect is the Direct Effect times the ratio between the standard deviation of the variables and the standard deviation of the Target Node.
* The Elasticity is the Direct Effect times the ratio between the range of the variable and the range of the Target Node.
* The Contribution is the Standardized Direct Effect divided by the total sum of Standardized Direct Effects.
{% endhint %}

**Non-Confounders**

By default, BayesiaLab's Direct Effect functions measure a variable's effect by holding all other variables constant. However, we can use the predefined class Non\_Confounder to define the nodes we _do not_ want to control.&#x20;

In our example, the main variable of interest, Drug Administration, has no direct effect. The post-treatment variable Efficacy mediates its causal effect, and the Direct Effect analysis blocks the path.  We must therefore use the predefined class Non\_Confounder (Efficacy's `Contextual Menu > Properties > Classes > Add > Predefined Class > Non_Confounders`) to prevent BayesiaLab from holding Efficacy constant and allow the estimation of the mediated causal effect. The new mutilated graph below is then used for estimating the Direct Effects:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691182194/ASP-GS-All-Intervention-Genderb_x1yfhf.svg" alt="" width="188"><figcaption></figcaption></figure>

\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Direct%20Effects2a.png" alt="" width="563"><figcaption></figcaption></figure>

Drug Administration's Direct Effect now equals the Average Causal Effect we manually computed with the Monitors. You can also note that we no longer analyze the effect of the Non-ConfounderEfficacy.

### Likelihood Matching <a href="#h3_972833961" id="h3_972833961"></a>

Now suppose we want to use Likelihood Matching instead of Graph Surgery. We first set back all nodes in Observation Mode via the monitors' Contextual Menus.

#### Nodes of Interest: Treatments/Drivers <a href="#h4__997675126" id="h4__997675126"></a>

The nodes of interest are the nodes for which we want to estimate the causal effect on the Target Node. We call them Treatments or Drivers.

In the previous section, we assumed that all nodes were of interest and set them in Intervention Mode. With Likelihood Matching, the workflow is less straightforward. For each Driver, we need to analyze the paths to the Target (_cf._ [Path Anlaysis](example-augmented-simpsons-paradox.md#h4\_\_1137334463)) to define the set of nodes that need to be controlled for to block the non-causal paths and let the causal paths open. Note that these nodes' sets may differ for each Driver, requiring us to perform multiple Total Effect analyses to avoid conflicting adjustments.&#x20;

The first step is then to define our nodes of interest. In the Augmented Simpson Paradox, the main variable of interest is obviously Drug Administration, but for illustrative purposes, let's consider Gender as well.

#### Total Effects <a href="#h4__997675126" id="h4__997675126"></a>

We have seen in the Path Analysis section that there are two paths between Gender and Outcome, both causal (#1 and #2). Thus, there is no variable to adjust for to estimate the Total Effect.

The [Path Analysis](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h4\_\_1137334463) indicates that there are also two paths between Drug Administration and Outcome, one causal (#7) and one non-causal (#6): Drug Administration ← Side Effects ← Gender → Outcome. So we need to adjust for Side Effects, or for Gender, to block this path. This is in contradiction to the analysis of Gender's effect. We cannot estimate the Total Effects of Gender and Drug Administration in the same analysis with Likelihood Matching!

So let's start with Gender. We select the node, go to `Main Menu > Analysis > Report > Target > Total Effects on Target`, and confirm that we want to perform the analysis on the selected node only:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Total%20Effects%20LM.png" alt="" width="563"><figcaption></figcaption></figure>

For Drug Administration, let's suppose we choose to adjust for Side Effects. We right-click on its associated Monitor and select Fix Probabilities from its Contextual Menu.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/AGS%20MonitorSE.svg" alt=""><figcaption></figcaption></figure>

Then, we select the node Drug Administration, go to Analysis > Report > Target > Total Effects on Target, and confirm that we want to perform the analysis on the selected node only:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Total%20Effects2.png" alt="" width="563"><figcaption></figcaption></figure>

#### Direct Effects <a href="#h3_337859533" id="h3_337859533"></a>

Now let's look at the workflow for estimating Direct Effects with Likelihood Matching, i.e., how to assess the effects of the direct paths only. Remember that, by default, BayesiaLab's Direct Effect functions measure a variable's effect by holding all variables constant except those associated with the predefined class Non\_Confounder.&#x20;

Holding a variable constant with Graph Surgery implies the deletion of its entering arcs. Thus, there is no risk of biasing the estimation of Direct Effects. In the Likelihood Matching case, this risk exists because we set evidence on the variable to adjust for it. Indeed, controlling for descendants of the Target Node (e.g., Litigation) automatically biases the estimate.

While we previously added Efficacy to the Non\_Confounder class to let it mediate the effect of Drug Administration, we must also add Litigation to prevent its adjustment.

Notice that there is no conflict in this analysis:

* Gender
  * Controlling for Side Effects, Drug Administration allows to cut the indirect causal path (#2);
  * Controlling for _Treatment Availability_ has no impact;
  * Not controlling for Efficacy has no effect as path #2 is already blocked;
  * Not controlling for Litigation prevents to bias the estimation of the effect;
* Drug Administration
  * Controlling for Side Effects, Gender allows to cut the non-causal path (#4);
  * Controlling for _Treatment Availability_ has no impact;
  * Not controlling for Efficacy allows to let the information flows from Drug Administration to Outcome;
  * Not controlling for Litigation prevents to bias the estimation of the effect.

We can, therefore, select our two nodes of interest, use Analysis > Report > Target > Direct Effects on Target, and confirm that we want to perform the analysis on the selected nodes only:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20GS%20Direct%20Effects2%20LM.png" alt="" width="563"><figcaption></figcaption></figure>

### Graph Surgery versus Likelihood Matching <a href="#h2_1052108448" id="h2_1052108448"></a>

Before concluding this chapter, let's summarize the main characteristics of Graph Surgery and Likelihood Matching:

* Graph Surgery
  * requires a fully specified Causal Bayesian Network;
  * uses the mutilated Causal Bayesian Network for causal inference;
* Likelihood Matching
  * requires the causal analysis of the domain to define the variables that need to be adjusted for to block the non-causal paths and let the causal paths open;
  * uses the Bayesian network to carry out probabilistic inference with the adjusted variables. Note that this network does not have to be causal! It just needs to represent the Joint Probability Distribution of the domain.

This last point is especially important. It is indeed sometimes challenging, if not impossible, to design the fully specified Causal Bayesian Network. However, BayesiaLab offers a wide range of machine-learning algorithms that we can use to induce a network that represents the Joint Probability Distribution. Hence, we only need to have a limited amount of causal knowledge to define the variables that have to be adjusted for.

For example, suppose we machine-learned the network below with `Main Menu > Learning > Supervised Learning > Augmented Naive Bayes`:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691182362/ASP-ANB_xtvc5f.svg" alt="" width="375"><figcaption></figcaption></figure>

The main architecture of the network is Naïve, _i.e._, the Target Node is the parent of all nodes. Therefore, this Bayesian network is clearly not causal. If we were to use Graph Surgery, we would not find any total or direct effects (see the corresponding mutilated graph below when estimating the Direct Effects with Efficacy and Litigation defined as Non\_Confounder).

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691182457/ASP-ANB-Mutilated_irwey2.svg" alt="" width="375"><figcaption></figcaption></figure>

\
However, Likelihood Matching returns the correct estimations for the Total Effects with two separate analyses.

One analysis for Gender, without adjusting for any variables:

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20ANB.%20DE%20LM2.png" alt="" width="563"><figcaption></figcaption></figure>

And one analysis for Drug Administration, by holding constant Side Effects:

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal\_Inference-web-resources/image/AGS%20MonitorSE.svg)

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20ANB.%20TE%20LM.png" alt="" width="563"><figcaption></figcaption></figure>

As for Direct Effects, the analysis can be carried out for both variables with the current definition of Non\_Confounders.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causal_Inference-web-resources/image/ASP%20ANB.%20DE%20LM.png" alt="" width="563"><figcaption></figcaption></figure>

### Conclusion <a href="#h2__1653368424" id="h2__1653368424"></a>

This chapter highlights how much effort is required to derive causal effect estimates from observational data. Simpson’s Paradox illustrates how much can go wrong even in simple circumstances. Given such potentially serious consequences, it is a must for policy analysts to examine all aspects of causality formally. To paraphrase Judea Pearl, we must not leave causal considerations to the mercy of intuition and good judgment. Fortunately, causality has emerged from its pariah status in recent decades, which has allowed tremendous progress in theoretical research and practical tools: “\[…] practical problems relying on casual information that long were regarded as either metaphysical or unmanageable can now be solved using elementary mathematics” (Pearl, 1999).&#x20;
