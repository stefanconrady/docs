# Graphical Identification Criteria

### Graphical Identification Criteria <a href="#h2__601832208" id="h2__601832208"></a>

It is self-evident that causal arcs have implications in terms of causation. However, as we pointed out earlier in this chapter (see [Structures Within a DAG](causal-dags.md#h3\_818976540)), there are also implications regarding the association of variables. This will perhaps become clearer as we introduce the concepts of “causal path” and “non-causal path.”

### Causal and Non-Causal Paths <a href="#h4__1482406793" id="h4__1482406793"></a>

In a DAG, a path is a sequence of non-intersecting, adjacent arcs, regardless of their direction.

* A causal path can be any path from cause to effect, in which all arcs are directed away from the cause and pointed toward the effect.
* A non-causal path can be any path between cause and effect in which at least one of the arcs is oriented from effect to cause.

Our example contains both types of paths:

Non-Causal Path: X ← Z → Y (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg))

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710189060/Simpson_CDAG2_o4zzsw.svg" alt="" width="188"><figcaption></figcaption></figure>

Causal Path: X → Y (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg))

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710189130/Simpson_CDAG3_cjgm4k.svg" alt="" width="188"><figcaption></figcaption></figure>

This distinction between causal and non-causal paths is critically important for identification.

### Adjustment Criterion and Identification <a href="#h3_676963991" id="h3_676963991"></a>

The Adjustment Criterion (Shpitser et al., 2010) is perhaps the most intuitive among several graphical identification criteria. The Adjustment Criterion states that a causal effect is identified if we can adjust for a set of variables such that:

* All non-causal paths (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg)) between treatment and outcome are “blocked” (non-causal relationships prevented).
* All causal paths (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg)) from treatment to outcome remain “open” (causal relationships preserved).

What does “adjust for” mean in practice? “Adjusting for a variable” can stand for any of the following operations, which all introduce information on a variable:

* Controlling
* Conditioning
* Stratifying
* Matching

At this point, the adjustment technique is irrelevant. Rather, we only need to determine which variables, if any, need to be adjusted in order to block the non-causal paths while keeping the causal paths open. Revisiting both paths in our CDAG, we can now examine which ones are open or blocked:

* First, we look at the non-causal path (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096326/Pink-Non-Causal-Arc\_nzhjm9.svg)) in our CDAG: X ← Z → Y. This implies that there is an indirect association between X and Y via Z that has to be blocked by adjusting for Z.
* Next is the causal path (![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691096153/Blue-Causal-Arc\_hqudas.svg)) in our CDAG: X → Y. It consists of a single arc from X to Y, which is open by default and cannot be blocked.

In this example, the Adjustment Criterion can be met by blocking the non-causal path X ← Z → Y by means of adjusting for Z. In other words, adjusting for Z allows identifying the causal effect from X to Y. From now on, we will often refer to such variables Z as Confounders.

Readers may be familiar with the expression “controlling for confounders.” What is important to bear in mind is that not all covariates in a system are Confounders! Recall Judea Pearl’s warning about ignorability and the risk of treating every covariate as a Confounder (see [Ignorability](../sources-of-causal-information.md#h3\_974053683)).

### **Unobserved Confounders**

Thus far, we have assumed that our example has no unobserved (also called hidden or latent) variables. However, if we had reason to believe that there is another variable, U, which appears to be relevant on theoretical grounds but was not recorded in the dataset, identification could no longer be possible. Why? Let us assume U is a hidden common cause of X and Y. By adding this unobserved variable U, a new non-causal path appears between X and Y via U.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1710189679/Simpson_CDAG4_wwgmvq.svg" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="danger" %}
Given that U is hidden, there is no way to adjust for it, and, therefore, we have an open, non-causal path that cannot be blocked. Hence, the causal effect is no longer identifiable, and thus, it can no longer be estimated without bias.

This highlights how easily identification can be “ruined.” Once again, we can only justify the absence of unobserved variables on theoretical grounds.
{% endhint %}

