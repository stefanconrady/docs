# Target Optimization

### **Summary of Node Roles**

#### Target Node:

* Sales

#### Confounders:

* TV Advertising
* Internet Advertising
* Print Advertising
* Direct Marketing
* Incentives (i.e., price discounts)

#### Confounders and Not Observable:

* Quarter
* Weekday
* Month
* End-of-Month Indicator

#### Non-Confounders:&#x20;

* Co-Op Promotions
* Competitive Incentives
* Web Traffic
* Showroom Traffic
* Test Drives

{% hint style="danger" %}
As we proceed, we furthermore assume that there are no unobserved Confounders. Such an assumption can only be justified on theoretical grounds. Given that this example represents a fictional domain, there is no purpose in debating the validity of the assumption.
{% endhint %}

### Target Optimization <a href="#h3__974403248" id="h3__974403248"></a>

Now we are ready to set the parameters of the Target Optimization.

* Select `Main Menu > Analysis > Target Optimization > Genetic`.
* Set Profile Search Criterion to Mean.
* Set Criterion Optimization to Maximization.
* Check Take Into Account the Resources.&#x20;

This means that for each to-be-tested scenario, BayesiaLab computes the value of the Class Resource, i.e., the value of the Function Node F1. Furthermore, you need to specify a range of acceptable values.&#x20;

* Check Target Resources and set this value to the available budget. By default, the value is set to the current value of F1. In our case, it is the sum of the means of the marginal distributions of the Confounders.
* Do not check Take Into Account the Joint Probability, as it does not apply to this example.

It would be applicable to models based on disaggregated data, e.g., with cross-sectional data representing the behavior of individuals.

* Some optimization tasks may require a trade-off between constraints and target achievement. The Weighting option allows us to prioritize specific optimization criteria. Set Resources to 10 to ensure that the search algorithm stays as close as possible to the specified Target Resources.
* Search Method depends on the problem domain. We discussed a similar set of options in the context of Target Dynamic Profile.&#x20;
* Set Numerical Evidence Proportional to: Mean.
* Set Distribution Estimation Method to Binary.&#x20;

Here, the optimization algorithm needs to modify the mean of each variable by setting Binary evidence (see Chapter 7, Binary Evidence). This is important because we are trying to determine which specific values—not distributions—achieve the maximum level of Sales. From a theoretical viewpoint, we could certainly search for the optimal distribution, but that is presumably not practical. Marketing budgets get approved and allocated on the basis of single-point dollar values, not distributions. &#x20;

* Clicking the Edit Variations button brings up the Variation Editor.

We already discussed the Variation Editor in the context of the [Target Dynamic Profile](https://bayesia.clickhelp.co/articles/bayesialab/8-probabilistic-structural-equation-models-key-driver-analysis/a/h4\_921701935). Here, we can further constrain individual variables in addition to the overall constraint determined by the specified Target Resource. A typical reason could be that some marketing expenditures may be locked into long-term contracts, which cannot be changed,&#x20;

* Set Intermediate Points to 10.

This setting refers to the number of points to test for each variable. To manage a potentially large computing load, it is good practice to start with a smaller number of Intermediate Points, e.g., 10, and later perform a search with a finer grid.

* Check Direct Effects. As we have emphasized throughout this chapter, we are looking for the causal effects of the driver variables. Otherwise, BayesiaLab would perform an optimization based on the Total Effect and produce meaningless results for our purposes.&#x20;
* Output determines how BayesiaLab stores the solutions found by Target Optimization. In our case, we want to save all new scenarios and overwrite any existing scenarios. Also, as the optimization can carry on for a long time, it is important to know that it can be stopped anytime. In that case, all solutions computed up to that point are saved as Evidence Scenarios.&#x20;
* Set Return the n Best Solutions to 10
* In terms of the Genetic Settings, we recommend keeping the defaults. Computer scientists will be familiar with these algorithm-related options. For the type of problem at hand, however, little can be gained by changing the defaults.
* By definition, genetic search algorithms continue mutating scenarios endlessly in order to find better solutions. Such an algorithm will never come to a natural conclusion. Hence, the Genetic Stop Settings are a practical way to stop the algorithm when no improvement has been observed after a certain number of iterations.
* Clicking OK starts the optimization, and we can monitor the activity in the status line at the bottom of the screen.​
* Once the Genetic Stop Criterion is met or when you manually terminate the optimization, BayesiaLab delivers the Optimization Report for the Target NodeSales.

Note that there is no progress bar, as no predetermined endpoint exists for a genetic optimization algorithm. We can, however, monitor the score to see the development of solutions.

Additionally, we need to take note of any warning symbols appearing in the bottom right corner of the main window. As Likelihood Matching is performed repeatedly throughout the optimization, there is the possibility of the Likelihood Matching algorithm—not the Target Optimization algorithm—being unable to converge. A yellow warning triangle icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184064/BayesiaLab\_Icons/warning-icon\_plawf9.svg) indicates this particular condition. Further details can be retrieved from the Console.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691087978/TargetOptimization_glinhy.mp4" %}

#### **Target Optimization Report**

<figure><img src="https://bayesia.clickhelp.co/resources/Storage/bayesialab/10-Causality_and_Optimization-web-resources/image/OptimizationReport.png" alt=""><figcaption></figcaption></figure>

* Initial States: Value/Mean refers to the mean value of the marginal distribution of the Target NodeSales.
* Resources represents the corresponding value of F1.
* Search Methods repeats the options we chose. While this may appear redundant, it is critically important to understand the precise conditions under which the solution was found.
* For the same purpose, the report lists the Not Fixed Nodes, which are the Non-Confounders that we had defined, meaning that they were not included in Likelihood Matching.
* We find the main part of the report in the Synthesis table. Here, we see the Initial State, which lists the mean values of the marginal distributions of the drivers. Best Solution shows the optimal levels of each driver. The values in parentheses indicate the deviation from the Initial State. Thus, we can easily see by what amount the marketing variables need to be changed. For example, the report recommends decreasing the Direct Marketing spend by 5.736 units.
* In the Best Solutions table at the bottom of the report, BayesiaLab lists the top scenarios identified plus the corresponding achievement in terms of the Target NodeSales. This tells us, for instance, that Sales will increase to 310.917 if the marketing variables are set to the specified levels. At the same time, the Resources would amount to 171.364, which is very close to the specified constraint.

If we suspect that we might have missed out on a potentially better solution, we could re-run the optimization using more Intermediate Points or set a different Stop Criterion. The potential extent of the search is ultimately a function of the available computing resources. However, given the size of the search space and the non-exhaustive nature of genetic search algorithms, we can never be certain to have found the optimum.

**It’s Causal!**

At this point, we need not shy away from causal language. All our causal assumptions had been explicitly specified earlier, and on that basis, we performed a causal optimization. If the assumptions can be justified, the effect estimation is causal and does not need to be circumscribed with cautious language. Given our input and applying hard-and-fast identification criteria, we are not in a gray area in terms of the causal interpretation of the results. If the results are to be challenged regarding their causal validity, we need to go straight back to the assumptions. The causal claims stand and fall with the assumptions we make, not with the estimation techniques.

**Evidence Scenarios**

While we may immediately gravitate toward the best solution listed first in the solutions table, we can examine all proposed solutions, which are stored as Evidence Scenarios:

* Right-click on the Evidence Scenario icon ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184135/BayesiaLab\_Icons/evidence-file\_kv36wu.svg).
* Check Include Not Observable to see the complete solution, including the values of the Not-Observable nodes.
* Select the Evidence Set with Index 0., which sets all nodes to the values specified under Best Solution in the Optimization Report.

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1691083803/SetEvidenceScenario_vvizgt.mp4" %}

This simulation confirms what we obtained in the Optimization Report, i.e., we can increase Sales by almost 15 units (per day) with the same budget. As a by-product of retrieving this Evidence Set, we can observe the corresponding values of the Non-Confounders. Similarly, we can evaluate the remaining scenarios for their plausibility. A seemingly inferior scenario could perhaps be more practical to implement.

For reference, all Monitors corresponding to Evidence Set 0 are shown below:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691088456/SetEvidenceScenario2_uzruqk.svg" alt=""><figcaption></figcaption></figure>

### Summary <a href="#h3_421811822" id="h3_421811822"></a>

This chapter presented a comprehensive workflow for optimizing the marketing mix of an organization. The key to this approach was using a machine-learned Bayesian network model in combination with causal assumptions in the form of confounder selection according to the Disjunctive Cause Criterion. BayesiaLab's Likelihood Matching algorithm facilitated the causal effect estimation and the subsequent optimization of marketing drivers.
