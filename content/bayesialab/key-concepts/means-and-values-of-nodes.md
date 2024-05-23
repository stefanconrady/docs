# Means and Values of Nodes

### Context <a href="#h2__638939938" id="h2__638939938"></a>

* At the top of each Monitor, the items Mean, Dev, and Value are displayed.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/MeansValues.svg" alt=""><figcaption></figcaption></figure>

* Mean refers to the Mean Value m and is only shown in the Monitors of numerical nodes.
* Dev stands for Standard Deviation and is shown alongside Mean.
* Value refers to the Expected Value $$v$$ and is shown in all Monitors, regardless of the node type, i.e., categorical or numerical.

### Examples <a href="#h2__1406500097" id="h2__1406500097"></a>

* The calculations for Expected Value and Mean Value are shown in the context of the following examples:

#### Categorical Node <a href="#h3_1625231731" id="h3_1625231731"></a>

Let's take the discrete node Age with three categorical Node States:

* Child
* Adult
* Senior

#### Categorial Node with Assigned State Values <a href="#h3_1625231731" id="h3_1625231731"></a>

* In the Node Editor, you can assign State Values to the Node States of Age.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/NodeEditorStateValues.png" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/MonitorMarginalDistribution.svg" alt=""><figcaption></figcaption></figure>

For each node, the Expected Value $$v$$ is computed using the assigned State Values and the marginal probability distribution of the Node States:

$$v = \sum_{s \in S} p_s \times V_s$$

where $$p$$ is the marginal probability of state $$s$$ and $$V_s$$ is its associated value.

$$v = 0.23 \times 10 + 0.415 \times 40 + 0.355 \times 70 = 43.750$$

The Monitor shows $$v$$ as the Value of Age.

{% hint style="info" %}
A Monitor of a categorical node does not show a Mean value.
{% endhint %}

#### Discrete Numerical Variable <a href="#h3__1138734949" id="h3__1138734949"></a>

Let's suppose that the node Age has three _numerical_ Node States instead of _categorical_ Node States.\


<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/DiscreteNumericalStates.png" alt="" width="563"><figcaption></figcaption></figure>

In this context, we need to consider two conditions, with and without State Values specified in the Node Editor:&#x20;

**No State Values Specified**

Here, State Values are not specified in the Values tab of the Node Editor. Note the empty Value column below.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/NoStateValues.png)

As a result, BayesiaLab uses the numerical values of the Node States, as they appear in the States tab, as the State Values.

Furthermore, as Age is a numerical node, its Monitor will now display the Mean (Mean) and the Standard Deviation (Dev) in addition to the Expected Value (Value)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/DiscreteNumericalNode.svg)

The Mean m is computed using the numerical values of the Node States and the marginal probability distribution of the Node States:

$$m = \sum_{s \in S} p_s \times c_s$$

where $$c_s$$ is the numerical value of the Node State.

$$m = 0.23 \times 10 + 0.415 \times 40 + 0.355 \times 70 = 43.750$$

{% hint style="info" %}
Note that Mean and Value are _identical_ in this case.
{% endhint %}

**State Values Specified**

However, if State Values are separately specified in the Values tab of the Node Editor, they will be used for the calculation of Value in the Monitor.

To highlight the distinction between the Node States {10, 40, 70} and the State Values, we assign unrelated arbitrary State Values of 0, 1, and 2.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/StateValuesDefined.png)

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/MonitorStateValuesDefined.svg)

The Expected Value $$v$$ is computed now using the assigned State Values {0, 1, 2} and the marginal probability distribution of the Node States:

$$v = \sum_{s \in S} p_s \times V_s$$

where $$p$$ is the marginal probability of state $$s$$ and $$V_s$$ is its associated value.

$$v = 0.23 \times 0 + 0.415 \times 1 + 0.355 \times 2 = 1.125$$

The Monitor shows $$v$$ as the Value of Age.

{% hint style="info" %}
Note that Mean and Value are _not identical_ in this case.
{% endhint %}

#### Continuous Numerical Variable <a href="#h3__840585181" id="h3__840585181"></a>

Let's now consider a continuous variable Age defined in the domain \[0; 99], discretized into three states:

* Child: \[0 ; 18]
* Adult: ]18 ; 65]
* Senior: ]65 ; 99]

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/ContinuousNode.png" alt="" width="563"><figcaption></figcaption></figure>

Given Age is a numerical node, its Monitor shows the Mean (Mean), the Standard Deviation (Dev), plus the Expected Value (Value).

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/ContinuousNodeMonitor.svg" alt=""><figcaption></figcaption></figure>

**No Associated Data**

If no associated data is with the node, both $$c_s$$ and $$V_s$$ are defined as the mid-points of the minimum and maximum values of each Node State. For example, for the Node State Adult ]18; 65], the midpoint is 17.2225.

So, the Mean Value m is computed as follows:

$$m = \sum_{s \in S} p_s \times c_s$$

$$m = 0.23 \times 9 + 0.415 \times 41.5 + 0.355 \times 82 = 48.4025$$

The Expected Value $$v$$ is calculated analogously:

$$v = \sum_{s \in S} p_s \times V_s$$

$$v = 0.23 \times 9 + 0.415 \times 41.5 + 0.355 \times 82 = 48.4025$$\


**Associated Data**

If data is associated with the node, $$c_s$$ is defined as the arithmetic mean of the data points that are associated with each Node State.

Furthermore, clicking on the Generate Values button in the Node Editor sets the values $$Vs$$ to the current arithmetic means of each Node State.

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/GenerateValues.png" alt="" width="563"><figcaption></figcaption></figure>

#### Value Delta <a href="#h3__913273997" id="h3__913273997"></a>

If you set a new piece of evidence on a node that modifies the distribution of the node, the Monitor displays a delta value in parentheses adjacent to Value.

![](https://bayesia.clickhelp.co/resources/Storage/bayesialab/FAQ/Node-Means-Values/DeltaValue.svg)

This delta is the difference between the current Expected Valuev and:

* the Expected Value $$v$$ before setting the modifying evidence, or
* the Expected Value $$v$$ that corresponds to the Reference Probability Distribution, which you can set with the ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184098/BayesiaLab\_Icons/reference-variation\_ztgquf.svg) icon in the toolbar.

#### Special Case: Some Node States Without Values <a href="#h3__1417001553" id="h3__1417001553"></a>

If only some Node States have an associated value, the Expected Value $$v$$ is computed from the subset of Node States $${S^*}$$ that do have an associated value.

$$v = \sum_{s \in S^*} \frac{p_s}{P^*} \times V_s$$

If a node only has a single Node State with an associated value, the corresponding Monitor does not report the Expected Value $$v$$.
