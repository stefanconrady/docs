# 🇫🇷 A Bayesian Network Model to Predict Outcomes in Acute Myocarditis Patients

Presented at the [9th Annual BayesiaLab Conference](./) on October 13, 2021.

### Abstract&#x20;

#### Background&#x20;

Acute myocarditis is an inflammation of the myocardium. It can occur at any age and has no typical presentation. Myocarditis is also an important cause of morbidity and mortality. Moreover, there is no current prognosis score existing.

#### Purpose&#x20;

The objective of this research was to predict and quantify the risk of cardiovascular events defined by extracorporeal membrane oxygenation (ECMO), heart transplant, or death in acute myocarditis patients.

#### Methods&#x20;

Using the AMPHIBIA registry, we developed a Bayesian network model to create a prognostic score. This Score quantifies the probability for a patient to reach our composite endpoint. We decided to exclusively retain baseline data while excluding all further data to predict early detection of the event. With the Bayesian theorem, we can draw a representation of our variables' dependencies, namely a Bayesian network. More precisely, a Bayesian network is a directed acyclic graph representing variables by a node and their conditional dependencies by a direct link. To create our predictive model, we first needed to discretize our continuous variables as the Bayesian networks require. Then, we used a supervised learning algorithm: the Markov Blanket. After defining our target variable, the Market Blanket only keeps strongly related variables (p-value << 0.01 in our model), excluding all other variables for the prediction of the event.

#### Results&#x20;

Our model shows good performances using only 6 variables from our dataset with an area under the curve of 91% for predicting whether or not the patient will reach the endpoint. With the cross-validation method, the model also performs well, with an area under the curve of 90%. The clinician can directly use the prediction output to classify the patients at their entrance to consider low, medium, and high-risk patients and send them to the appropriate hospital department: standard or intensive care unit. Finally, looking at the posterior probabilities, the patients who will most likely reach the endpoint are women with pre-cardiogenic shock, high NTprobnp, high creatinine, low TP, and no chest pain. Conversely, the patients who won’t reach the endpoint are more often men with chest pain, no cardiogenic shock, high TP, low NT pro-BNP, and low creatinine.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1695083312/2021-10-13-Conference-Gatien-Hubert_blgkjs.mp4" %}

### About the Presenter

My name is Gatien Hubert, and I am a fourth-year medical student at Sorbonne University, France.

At the same time, I have also followed statistics courses, still at Sorbonne University. As part of this course, I have done an internship in the INSERM Department of Cardiology at La Pitié Salpêtrière Hospital, where I enjoyed using Bayesialab to develop my models.

### Presentation Slides

{% embed url="https://res.cloudinary.com/dvr3obmlj/image/upload/v1695083321/Gatien_Hubert_Diaporama_final_fyyt8e.pdf" %}
