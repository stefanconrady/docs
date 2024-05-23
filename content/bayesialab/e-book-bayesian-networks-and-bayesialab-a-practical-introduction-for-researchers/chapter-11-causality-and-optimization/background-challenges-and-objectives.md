# Background, Challenges, and Objectives

### Background & Challenges <a href="#h3_332801758" id="h3_332801758"></a>

While this chapter’s example is inspired by a real business, we are trying to minimize any resemblance to a particular company or industry. We shall refer to our fictional business as ACME Corp. All of its sales and marketing data are synthetically generated. This allows us to illustrate a variety of effects in a single composite example. With the few publicly available datasets of real marketing and sales data, we might not be able to observe the range of characteristics that we wish to present here. Also, for ease of interpretation, we have magnified some effects, resulting in a somewhat idealized consumer response to the marketing actions of ACME Corp. With artificial data, we also have the luxury of plentiful observations, although that is not necessarily unrealistic.

### Variables <a href="#h3_442277137" id="h3_442277137"></a>

Our fictional business ACME utilizes a variety of marketing and advertising channels. Throughout this chapter, we will also refer to them as "marketing drivers" or just "drivers."

* TV Advertising
* Internet Advertising
* Print Advertising
* Direct Marketing
* Incentives (i.e., price discounts)

These variables are all measured on proprietary scales. For instance, TV Advertising might be measured in GRP (Gross Rating Points), and Print might be recorded in columns-inches. Incentives refer to price promotions and discounts measured in dollars. All these marketing instruments we consider as being under ACME’s control, i.e., we can set them to any desired level within an overall budget constraint.

Furthermore, we have a target variable, Sales, measured in units sold daily, which we hope to improve by optimizing the mix of marketing instruments.

Beyond the variables that are under ACME’s control, there are four calendar variables:

* Quarter
* Weekday
* Month
* End-of-Month Indicator

Finally, we measure a number of variables that are beyond ACME's direct control but still have an influence on the business, including:

* Co-Op Promotions (promotions sponsored by the vehicle manufacturer)
* Competitive Incentives (i.e., price discounts on competitive products)&#x20;
* Web Traffic (organic traffic to ACME's website—not paid-for traffic)
* Showroom Traffic (organic visits to ACME's facilities)
* Test Drives (organic)

While numerous other variables do certainly exist in this domain, we have no further data available. Later, we will need to formalize our assumptions in this regard.

### Objectives <a href="#h3__1301596050" id="h3__1301596050"></a>

For a comprehensive study of marketing mix modeling and optimization, there are numerous questions we should consider, such as:

* Which form of advertising is the strongest driver of ACME's sales?
* How do competitive incentives affect ACME's sales?
* What is the optimum marketing mix overall, given different levels of marketing budget constraints?
* Are there saturation effects of certain marketing channels?
* Are there counterproductive promotions?
* How can we attribute the observed sales volume to marketing initiatives?
* What would be the baseline sales volume without any advertising?
* Are there synergy effects that make some instruments more important jointly than their individual importance?

### Causal Questions <a href="#h3__6811274" id="h3__6811274"></a>

The single most important thing we need to recognize regarding the above questions is that they are all causal questions. This means we are not looking for a prediction of Sales based on the observation of marketing variables. Rather, we wish to simulate the manipulation of all marketing variables in such a way that we maximize Sales. Thus, we are performing an intervention in our domain, which requires causal inference. This is the reason why we can only introduce the marketing mix question after having established foundational causal concepts in [Chapter 10](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation). There, we explained how a causal graph, combined with certain criteria, can tell us precisely what variables we have to adjust to identify a causal effect. We merely had to provide a causal graph, i.e., encode our causal understanding of the domain. With three variables in [Simpson’s Paradox](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h3\_\_1501618340), there were only 25 possible causal structures. A common-sense understanding of the domain allowed us to quickly identify the only reasonable graph in terms of causal directions. In that case, making assumptions about the full causal structure was straightforward. So, we may now feel well-equipped to answer more complex causal questions, such as the given marketing domain.

### **From 25 to 1,439,428,141,044,398,334,941,790,719,839,535,103 Graphs**

Going from three variables in [Simpson’s Paradox](../chapter-10-causal-effect-identification-and-estimation/example-simpsons-paradox.md) to 14 variables in this marketing example, it would be reasonable to expect a substantial increase in the number of possible causal networks. As it turns out, given a set of 14 variables, there are now 1.4×1036 possible causal structures as opposed to 25. Clearly, we can no longer rely on our intuition to pick the correct one out of over one undecillion possible graphs. Furthermore, clever algorithms and fast computers cannot help us with this task either. As it stands, causal directions can generally not be discovered through machine learning.

However, without a causal graph, we cannot use the familiar criteria for confounder selection, such as the [Adjustment Criterion](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h3\_189780361). And, without the ability to select and control for confounders, we cannot employ the usual estimation methods. A commonly used fall-back position is to simply “control for all pretreatment covariates” (Rubin, 2009). However, the example in the previous chapter highlighted the risks of doing that. So, it appears that we have already reached a dead end with our example.

For a comprehensive study of marketing mix modeling and optimization, there are numerous questions we should consider, such as:

* Which form of advertising is the strongest driver of ACME's sales?
* How do competitive incentives affect ACME's sales?
* What is the optimum marketing mix overall, and given different levels of marketing budget constraints?
* Are there saturation effects of certain marketing channels?
* Are there counterproductive promotions?
* How can we attribute the observed sales volume to marketing initiatives?
* What would be the baseline sales volume without any advertising?
* Are there synergy effects that make some instruments more important jointly as opposed to their individual importance?

### Causal Questions <a href="#h3__6811274" id="h3__6811274"></a>

The single most important thing we need to recognize regarding the above questions is that they are all causal questions. This means we are not looking for a prediction of Sales based on the observation of marketing variables. Rather, we wish to simulate the manipulation of all marketing variables in such a way that we maximize Sales. Thus, we are performing an intervention in our domain, which requires causal inference. This is the reason why we can only introduce the marketing mix question after having established foundational causal concepts in [Chapter 10](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation). There, we explained how a causal graph, combined with certain criteria, can tell us precisely what variables we have to adjust for identifying a causal effect. We merely had to provide a causal graph, i.e., encode our causal understanding of the domain. With three variables in [Simpson’s Paradox](https://bayesia.clickhelp.co/articles/bayesialab/10-causal-effect-estimation/a/h3\_\_1501618340), there were only 25 possible causal structures. A common-sense understanding of the domain allowed us to quickly identify the only reasonable graph in terms of causal directions. In that case, making assumptions about the full causal structure was straightforward. So, we may now feel well-equipped to answer more complex causal questions, such as the given marketing domain.

**From 25 to 1,439,428,141,044,398,334,941,790,719,839,535,103 Graphs**

Going from three variables in [Simpson’s Paradox](../chapter-10-causal-effect-identification-and-estimation/example-simpsons-paradox.md) to 14 variables in this marketing example, it would be reasonable to expect a substantial increase in the number of possible causal networks. As it turns out, given a set of 14 variables, there are now 1.4×1036 possible causal structures as opposed to 25. Clearly, we can no longer rely on our intuition to pick the correct one out of over one undecillion possible graphs. Furthermore, clever algorithms and fast computers cannot help us with this task either. As it stands, causal directions can generally not be discovered through machine learning.

However, without a causal graph, we cannot use the familiar criteria for confounder selection, such as the Adjustment Criterion. And, without the ability to select and control for confounders, we cannot employ the usual estimation methods. A commonly used fall-back position is to simply “control for all pretreatment covariates” (Rubin, 2009). However, the example in the previous chapter highlighted the risks of doing that. So, it appears that we have already reached a dead end with our example.

### The Disjunctive Cause Criterion <a href="#h3_1412415481" id="h3_1412415481"></a>

As it turns out, recent research has made significant progress and produced a new criterion for selecting confounders. [VanderWeele and Shpitser (2010)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3166439/) have discovered that it is possible to select confounders without knowing the full causal graph:

> We show that irrespective of the true causal structure is and irrespective of whether there are important unobserved variables if there exists some subset of the observed covariates that suffice to control for confounding, then the set obtained by applying our criterion will also constitute a set that suffices.

This is a profound insight, given that not knowing the causal structure between covariates is not at all unique to our example. We speculate that “causal ignorance” is the prevailing condition in most research projects. VanderWeele and Shpitser have shown that confounders can be found differently:&#x20;

> We propose that control be made for any \[pre-treatment] covariate that is either a cause of treatment or of the outcome or both.

In other words, we now need to ask the common-sense question about each covariate, “is it a cause of the treatment or the outcome or both?” If the answer is yes, the variable in question is a confounder, and we must control for it to estimate the causal effect. With this new approach to confounder selection, we do not need to know—or even consider—the relationships between the covariates.

There are a number of caveats, though. Once again, we have to assume that there are no unobserved confounders. Furthermore, we must also assume that there exists a set of variables Z that would meet one of the formal identification criteria. If this assumption holds, the proposed selection criterion will identify the set of variables Z. We must stress that such an assumption cannot be tested. It can only be justified on theoretical grounds. Nevertheless, it is a much weaker assumption than claiming to know the full causal structure.

### Confounder Selection in Practice <a href="#h3_172116895" id="h3_172116895"></a>

In the context of this marketing example, we consider Sales as the outcome variable. However, unlike a single treatment X in Simpson’s Paradox, we now have many potential treatments, i.e., all the marketing variables. Not only do we have to identify Confounders with regard to one treatment/outcome relationship, but we need to do this for all treatment/outcome pairs. For instance, if we were considering TV Advertising as treatment, we will need to check all covariates as to whether they are causes of TV Advertising, Sales, or both.

In this domain, it is fairly easy to judge that all of ACME’s advertising efforts (TV Advertising, Internet Advertising, Print Advertising, Direct Marketing) and Incentives should be seen as causes of Sales. We also reason that the calendar variables, Quarter, Weekday, Month, and End-of-Month Indicator are also causes of Sales. It is common knowledge, for instance, that Saturday is the main car shopping day in the U.S. Also, the fourth quarter marks the start of a new model year and concludes the calendar year, which makes it the peak selling season.

Five variables remain, i.e., Co-Op Promotions, Competitive Incentives, Web Traffic, Showroom Traffic, and Test Drives. Are they not also causes of Sales? Yes, but we argue that they are not pre-treatment variables. Rather, given our domain knowledge, we believe that these variables “respond” to ACME’s marketing and advertising efforts, meaning that they are "downstream" from the original causes. For example, the original cause Print Advertising drives Showroom Traffic, which subsequently leads to Sales.

Regarding Competitive Incentives being a Non-Confounder, we argue that the competition presumably wants to counteract ACME efforts. If ACME increases incentives as part of a campaign, competitors would presumably follow suit with their own incentives. However, one may object to this line of reasoning and instead suggest that Competitive Incentives come first and that it prompts ACME to react. From that viewpoint, Competitive Incentives would definitely be pre-treatment. However, if we treated Competitive Incentives as Confounder, it would imply that the competition would “hold still” while ACME tries out different marketing spend levels during optimization. Clearly, this would be an unrealistic assumption. Instead, we believe that it is reasonable to think that the competition would react similarly as they have always done historically.

With that, we have specified all explicit assumptions regarding this domain. Furthermore, we have also assumed implicitly that there are no unobserved Confounders, i.e., that no other hidden variables exist that influence our domain. Such a claim is almost as bold as assuming the complete causal structure of this domain. Also, there is no way to test for the existence of hidden Confounders. As outrageous as this may seem, this assumption is made in virtually all models based on observational data, regardless of the modeling technique. The only way we can justify this assumption is on theoretical grounds, i.e., we need to have domain knowledge that allows us to rule out unobserved Confounders.

### Estimation Challenges <a href="#h3__1376158685" id="h3__1376158685"></a>

Now that we have identified the Confounders, we would expect to be able to estimate the causal effects. Theoretically, the Adjustment Formula (i.e., stratification) could serve as our computation method. Why is this not immediately feasible?

The first objection is that our dataset consists of mostly continuous variables rather than discrete states, which was the case in the previous chapter. However, we can overcome this challenge by discretizing all continuous variables, which we have demonstrated repeatedly in this book.

With the discretized dataset of our domain, a new problem looms: assuming that all confounders now have 5 discrete states, we would need to calculate the weighted average of approximately 2 million strata to estimate the effect of one treatment. In other words, we would require the entire joint probability table representing the domain. Even if we could manage the computational task with a computer fast enough and with enough memory to store the joint probability table, we would not have anywhere near enough observations to estimate this table. While we have thousands of daily observations, our joint probability table would consist of millions of rows.

### Summary of Challenges <a href="#h3_1634269429" id="h3_1634269429"></a>

Let us summarize where we stand. We started this chapter with the challenge that we could not encode one true causal graph. Thus, identification using traditional criteria was not possible. The new Disjunctive Cause Criterion by Shiptser and VanderWeele saved us from having to define a full causal graph. Fewer, simpler assumptions will now suffice to select the confounders. But now that we have the Confounders, our straightforward estimation techniques, e.g., stratification, will no longer work. It seems for every step forward, we must take another one back.
