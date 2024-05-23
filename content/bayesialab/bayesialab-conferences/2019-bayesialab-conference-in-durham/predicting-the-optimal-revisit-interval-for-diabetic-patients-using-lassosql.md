---
description: Annie M. Lasway, MPH, PMP, CPC, MITRE Corporation, McLean, VA, USA
---

# 🇺🇸 Predicting the Optimal Revisit Interval for Diabetic Patients using LASSOSql

Presented at the [7th Annual BayesiaLab Conference](./) at the North Carolina Biotechnology Center.

### Abstract&#x20;

#### Introduction&#x20;

Feature selection is a crucial and challenging task in statistical and probabilistic modeling, there are many studies that try to optimize and standardize this process for various types of data. To build and interpret a model that takes into consideration all variables is difficult. Historically, feature selection has been made based on provider knowledge and experience. As Judea Pearl noted in his book on causality, ‘leaving causality in the hands of intuition and judgment is an impediment in research’. Advancements in Bayesian Network research is tied closely to causality and the seminal work of Judea Pearl. Methods such as Directed Cyclic Graphs and Bayesian Networks provide techniques that enable the establishment of causation from association when working with non-experimental data. Variable selection is even more important in high-dimensional datasets and it is often difficult to determine which variables are relevant. In high dimensional observational data, the causal impact of treatment. can be optimized and achieved through blocking Back-Door paths in order to identify the Markov Blanket. By holding comorbidities ceterus paribus, we can isolate the treatment effect. The observed differences are then identified as the treatment effect. The Markov blanket of treatment is a group of covariates that blocks the effect of other covariates on treatment. Markov blankets include direct causes that are the parents and co-parents, as well as the effects which are the children. Parents in the Markov Blanket (pMB) can be determined by analyzing independent variables that occur before treatment, this removes covariates in the causal path from treatment to outcome which tends to be the complications associated with treatment. The pMB in this study is determined using likelihood ratios (LR). LR is the ratio of two conditional probabilities. It is a probability concept that can be used to develop predictive data algorithms. In probability theory, LR are used to indicate how useful one element is in predicting the occurrence of an event. LR measure the association between each predictor and an outcome variable. To demonstrate the efficiency of LASSOSql, the model will be applied to real data. This study will use causal methods to predict the optimal Revisit Intervals (RVI) for patients with diabetes using claims data from the Centers for Medicare and Medicaid Services (CMS). Currently, revisits are scheduled by providers based on heuristics and experience, with large variability and little empirical evidence. Yet, evidence suggests that RVI can be safely lengthened for many patients without decrements in quality or outcomes. Longer RVI for diabetic patients who need to be seen sooner can lead to complications related to high blood sugar which can affect various cells and organs in the body. Complications may include kidney and eye damage, which could result in blindness, or an increased risk for heart disease or stroke. The proposed methodology uses LR to assess the chances that a patient would have kidney disease given a RVI based and also based on patient comorbidities.

#### Data&#x20;

The dataset contains data from the CMS Limited Dataset from 2016.

#### Methodology&#x20;

The average RVI is calculated across the entire sample. Long RVI is defined as the RVI that is 1 standard deviation above the average. Short RVI is defined as 1 standard deviation below the average. Using standard deviations instead of values below and above the cut-off point increases the sensitivity of the model. The LR are calculated as the prevalence of the risk factor in the presence of a positive outcome over the prevalence of the same risk factor in the absence of the outcome. A sensitivity analysis is then conducted. Conditional probabilities are used to reduce the number of comorbidities needed in the predictive analysis.

#### Results&#x20;

LASSOSql is an effective methodology of predicting optimal RVI for chronic conditions.

#### Assumptions & Limitations&#x20;

We assume that the data points are independent of each other between and within groups.

#### Conclusion&#x20;

This study focuses on determining the pMB for the impact of RVI and every comorbidity on Kidney Disease in order to optimize routine RVI for primary care. The results of which, could help maximize access to care for diabetic patients and therefore inform and influence practice management and policy standards related to RVI.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1703889834/Annie_Lasway__Predicting_the_Optimal_Revisit_Interval_for_Diabetic_Patients_using_LASSOSql_knln98.mp4" %}

### About the Presenters&#x20;

Annie M. Lasway, MPH, PMP, CPC, MITRE Corporation, McLean, VA, USA

Farrokh Alemi, PhD, George Mason University (GMU), Fairfax, VA, USA

Annie Lasway is a Senior Health Systems Analyst at the MITRE Corporation supporting Public Sector Healthcare Research. Before joining MITRE, Ms. Lasway worked at Altarum Institute and the National Institutes of Health. Annie holds a bachelor’s degree in Community Health from the University of Maryland College Park and a Master of Public Health with a concentration in Global and Community Health from George Mason University (GMU). She is a certified Project Management Professional (PMP) and a Certified Professional Coder (CPC). She is currently pursuing her Doctoral Degree in Health Services Research with a concentration in Informatics at GMU.\
