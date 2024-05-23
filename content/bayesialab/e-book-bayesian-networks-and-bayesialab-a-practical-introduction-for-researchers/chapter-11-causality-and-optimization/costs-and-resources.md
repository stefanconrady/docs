# Costs and Resources

### Function Nodes <a href="#h3_860129437" id="h3_860129437"></a>

The question of budget brings up another issue. Thus far, all variables are shown on their original, proprietary scale without any cost information. For instance, we have not yet defined how much “one unit” of TV Advertising costs in dollars. Prior to version 6 of BayesiaLab, the Cost property was available to specify the unit cost for each variable. At the time, one could have specified that 1 GRP costs $1,000. However, real-world applications are not as straightforward as having a fixed price per unit. As is the case with most business transactions, volume discounts may apply that need to be considered when optimizing media spend.

With BayesiaLab 6, we introduced the concept of Function Nodes. They facilitate the computation of scalar values based on the distribution and values of the states in nodes. This is best illustrated in the context of our example. We will now use a Function Node to “translate” the original units of TV Advertising into dollar values.

{% hint style="info" %}
A Function Node node calculates values ad hoc. As such, a Function Node does not exist in the original dataset.
{% endhint %}

### **Introducing the Function Node**

* In Modeling Mode, click on the Function Node Creation Mode by clicking on the corresponding icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184143/BayesiaLab\_Icons/function\_rp20fm.svg) on the menu bar.
* Position the node on the Graph Panel. By default, the first Function Node to be introduced has the name F1.
* Go into Arc Creation Mode and draw an arc from TV to F1.

For random nodes, the warning symbol means that the Conditional Probability Table has not been estimated yet. In the context of Function Nodes, it means that an equation has yet to be defined that will determine the value of the Function Node.

* Open the Function Node F1 by double-clicking on it, which brings up the Node Editor.

Note the TV Advertising node listed in the center of the three panels at the bottom of the window. This is where the parent nodes of a Function Node are shown. In our case, TV Advertising is currently the only parent node. This means that TV Advertising is the only variable that can be included in the Equation Tab in the top panel of the window.&#x20;

Whereas a Function Node, such as F1, represents scalar values, "normal" nodes, such as TV Advertising, always represent distributions of states.

This is where the functions in the bottom left panel come into play, in particular the Inference Functions. We can use them to extract a scalar statistic from TV Advertising, which F1 will then represent as a scalar value.

Here, as a first step, we want F1 to represent the mean value of the cost of TV Advertising:

* Double-click on Inference Functions and then double-click on MeanValue(v). This adds the inference function to the Equation Tab. By default, a placeholder variable v is highlighted in the equation
* You can single-click on TV Advertising to bring up the domain range of this variable for your information
* Double-click on TV Advertising to add ?TV Advertising? to the Equation Tab. ?TV Advertising? should automatically assume the position of v if that placeholder was still highlighted. The final syntax will appear as ?F1?=MeanValue(?TV Advertising?)
* Click Validate to check the syntax and have BayesiaLab compute the value of F1.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083803/FunctionNodeIntroduction_ttqzep.mp4" %}

### **Summing Up the Costs**

Where are we going with this? We will now add further parents to F1 so that we can calculate the cumulative cost of all Confounders. We simply draw arcs from all the Confounders to F1.

* Select the Arc Creation Mode and draw arcs from all Confounders to F1.
* Hold `L` to remain in the Arc Creation Mode so you can keep adding arcs without having to go back to the toolbar.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083801/ConnectF1toConfounders_avjyk4.mp4" %}

Recall that we did not draw any arcs from Weekday, Month, Quarter, and End-of-Month Indicator to F1. The reason is that these calendar-related variables are beyond the control of ACME. Therefore, ACME couldn't buy more Saturdays or pay for a longer fourth quarter. Also, we won't draw arcs from the Non-Confounders to F1 as ACME cannot directly control them through their budget either.

The Function Node F1 can now serve as a "summary node" for all Confounders. If all Confounders were recorded on the same scale and had the same cost of $1/unit, you could sum up the mean values of all the Confounders:

* Double-click F1 to open the Node Editor.
* Enter this expression into the Equation Tab: `MeanValue(?TV?)+MeanValue(?Print?)+MeanValue(?Online?)+MeanValue(?Incentives?)+MeanValue(?Direct Marketing?)`
* Instead of typing the entire syntax, you can also add the inference function MeanValue() and all listed Confounders by double-clicking on the respective items in the lower panels of the Node Editor.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083804/AddInferenceFunctionInNodeEditor_h2uown.mp4" %}

Needless to say, assuming a cost of $1/unit for each type of advertising is entirely unrealistic. And the purpose of having a Function Node is that we can enter any arbitrary cost function for each advertising channel. A typical example would be entering a quantity discount in the form of an if/then statement:

`?F1?=IF(MeanValue(?Print Advertising?)>=10, 0.9*MeanValue(?Print Advertising?),MeanValue(?Print Advertising?))`

This statement would discount the cost of Print Advertising by 10% once 10 units are reached. This way, you can define even complex pricing and discount structures. Why is this so important? The optimization algorithm that BayesiaLab employs can take advantage of any such additional nonlinearities.

However, given that our model is based on synthetic data that already features plenty of nonlinearities, it serves no educational purpose to add further artifacts to our problem domain. Hence, we stick with a fictional cost of $1/unit for each advertising channel.

### Resources <a href="#h3_191819257" id="h3_191819257"></a>

A Function Node is a highly flexible element in BayesiaLab and can play many different roles. Here, we justified its use by our need to calculate the cumulative cost of all advertising efforts.

However, not only do we need to know the total cost, but we also need to constrain it in the subsequent optimization. If cost were no object, we could simply read the optima from the Target Mean Analysis plot by taking the x-levels that correspond to the maximum y-levels for each driver. Alas, budget constraints do apply in the real world.

In BayesiaLab, we can formalize the "budget" role of F1 by adding it to the pre-defined Class Resource.&#x20;

* Right-click on F1.
* From the Contextual Menu, select Properties > Classes > Add.
* Then, check Predefined Class and select Resource from the drop-down menu.
* Click Yes to conclude the step.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083801/AddToClassResource_rpdpev.mp4" %}

Note that we could add additional Function Nodes to this Class. This way, the Class Resource can represent the sum of multiple Function Nodes.

### Not-Observable Nodes <a href="#h3__1995761378" id="h3__1995761378"></a>

We previously pointed out that Quarter, Weekday, Month, and End-of-Month Indicator neither have any monetary cost. The positive effect of Weekday=Saturday on Sales is a "free" benefit to ACME. And the absence of arcs going into F1 already prevents these nodes from being included in the monetary cost summary in F1.

However, as we prepare for optimization, we must also encode formally that these variables cannot be modified or influenced by anyone. In other words, ACME cannot manipulate them. Thus, Quarter, Weekday, Month, and End-of-Month Indicator require a special designation so that BayesiaLab _includes_ them in the Likelihood Matching of the Confounders but excludes them from active manipulation during optimization.

Unfortunately, the BayesiaLab jargon will now become a bit convoluted. The “do-not-manipulate” assignment of variables is done via their Cost attribute. This Cost is not to be confused with the monetary cost in terms of dollars, which is computed by F1. In general, the Cost attribute of a variable quantifies the effort required to observe a variable (see the Diagnosis example in Chapter 6). A special case is Cost=0, which makes a variable Not Observable in BayesiaLab. In the context of the calendar variables in our example, this nomenclature is counterintuitive as we would think that the dates in the calendar are certainly observable.&#x20;

However, it goes beyond the scope of this chapter to present the rationale of this terminology. For the purposes of this example, we set Cost=0 to exclude the calendar variables from being manipulated during the optimization.

### **Assigning the Observation Cost**

* Select the calendar variables and then right-click on any one of them.
* From the Contextual Menu, select `Properties > Cost`
* Uncheck the box Cost or enter 0 in the Edit Cost window.
* Click OK

The Not Observable status of the variables is now reflected in the light purple color of the calendar nodes.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083803/SetCostToZero_fbgngw.mp4" %}
