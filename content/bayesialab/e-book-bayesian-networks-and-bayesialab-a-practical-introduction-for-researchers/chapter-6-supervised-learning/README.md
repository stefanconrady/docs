# Chapter 6: Supervised Learning

In [Chapter 4,](../chapter-4-knowledge-modeling-and-probabilistic-reasoning.md) we defined the qualitative and quantitative parts of a Bayesian network from existing (human) knowledge. [Chapter 5](../chapter-5-bayesian-networks-and-data/) described how we can define the qualitative part of a Bayesian network manually and then use data to estimate the quantitative part. In this chapter, we use BayesiaLab to generate both the structure and the parameters of a network automatically from data. This means we introduce machine learning for building Bayesian networks. The only guidance (or constraint) we provide is defining the variable of interest, i.e., the target of the machine-learning process. Hence, we speak of Supervised Learning (in [Chapter 7](../chapter-7-unsupervised-learning/), we will remove that constraint as well and perform Unsupervised Learning).

The objective of what we call Supervised Learning is no different from that of predictive modeling. We wish to find regularities (a model) between the target variable and potential predictors from observations (e.g., historical data). Such a model will allow us to infer a distribution of the target variable from new observations. If the target variable is Continuous, the predicted distribution produces an expected value. For a Discrete target variable, we perform classification. The latter will be the objective of the example in this chapter.

### Example: Tumor Classification&#x20;

Given the sheer amount of medical knowledge in existence today, plus advances in artificial intelligence, so-called medical expert systems have emerged, which are meant to support physicians in performing medical diagnoses. In this context, several papers by Wolberg, Street, Heisey, and Managasarian became much-cited examples. For instance, [Street, Wolberg, Mangasarian (1993)](https://doi.org/10.1117/12.148698) proposed an automated method for the classification of Fine-Needle Aspirates (FNA) through imaging processing and machine learning with the objective of achieving greater accuracy in distinguishing between malignant and benign cells for the diagnosis of breast cancer. At the time of their study, the practice of visual inspection of FNA yielded inconsistent diagnostic accuracy. The proposed new approach would increase this accuracy reliably to over 95%. This research was quickly translated into clinical practice and has since been applied with continued success.

As part of their studies in the late 1980s and 1990s, the research team generated what became known as the Wisconsin Breast Cancer Database, which contains measurements of hundreds of FNA samples and the associated diagnoses. Several versions of this database have been extensively studied, even outside the medical field. Statisticians and computer scientists have proposed a wide range of techniques for this classification problem and have continuously raised the benchmark for predictive performance.

The objective of this chapter is to show how Bayesian networks, in conjunction with machine learning, can be used for classification. Furthermore, we wish to illustrate how Bayesian networks can help researchers generate a deeper understanding of the underlying problem domain. Beyond merely producing predictions, we can use Bayesian networks to precisely quantify the importance of individual variables and employ BayesiaLab to help identify the most efficient path towards diagnosis.

To provide further background regarding this example, we quote [Mangasarian et al. (1994)](https://www.jstor.org/stable/171686?seq=1):

“Most breast cancers are detected by the patient as a lump in the breast. The majority of breast lumps are benign, so it is the physician’s responsibility to diagnose breast cancer, that is, to distinguish benign lumps from malignant ones. There are three available methods for diagnosing breast cancer: mammography, FNA with visual interpretation, and surgical biopsy. The reported sensitivity (i.e., ability to correctly diagnose cancer when the disease is present) of mammography varies from 68% to 79%, of FNA with visual interpretation from 65% to 98%, and of surgical biopsy close to 100%.

Therefore mammography lacks sensitivity, FNA sensitivity varies widely, and surgical biopsy, although accurate, is invasive, time-consuming, and costly. The goal of the diagnostic aspect of our research is to develop a relatively objective system that diagnoses FNAs with an accuracy that approaches the best achieved visually.”

### Data&#x20;

The Wisconsin Breast Cancer Database was created through the clinical work of Dr. William H. Wolberg at the University of Wisconsin Hospitals in Madison.

The dataset we are using for this tutorial contains 569 patient records, which contain a diagnosis plus features that were computed from digital images of fine-needle aspirates (FNA) of breast masses. More specifically, these features characterize the cell nuclei contained in the tissue samples.  &#x20;

* ID number
* Diagnosis (M=malignant, B=benign)&#x20;
* radius (mean of distances from center to points on the perimeter)
* texture (standard deviation of gray-scale values)
* perimeter
* area
* smoothness (local variation in radius lengths)
* compactness (perimeter^2 / area - 1.0)
* concavity (severity of concave portions of the contour)
* concave points (number of concave portions of the contour)
* symmetry
* fractal dimension ("coastline approximation" - 1)

For each feature, the mean, standard error, and "worst" or largest (mean of the three largest values) were computed. For this tutorial, however, we only use the mean values as variables.

The diagnosis variable was established via subsequent biopsies or long-term monitoring of the tumor. It consists of two classes: 357 benign cases (62.7%) and 212 malignant cases (37.2%).

You can download this dataset in CSV format via the link below or from [data.world](https://data.world/health/breast-cancer-wisconsin).&#x20;

[WBCD2.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1690824290/WBCD2\_ziifqe.csv)

{% hint style="info" %}
Note that this dataset from the Wisconsin Breast Cancer Database is different from the one we used in the original, printed edition of this book.
{% endhint %}

### Tutorial&#x20;

The following topics explain each step of the Supervised Learning workflow on the basis of this example.

{% content-ref url="data-import-and-discretization.md" %}
[data-import-and-discretization.md](data-import-and-discretization.md)
{% endcontent-ref %}

{% content-ref url="supervised-learning-markov-blanket.md" %}
[supervised-learning-markov-blanket.md](supervised-learning-markov-blanket.md)
{% endcontent-ref %}

{% content-ref url="supervised-learning-structural-coefficient-analysis.md" %}
[supervised-learning-structural-coefficient-analysis.md](supervised-learning-structural-coefficient-analysis.md)
{% endcontent-ref %}

{% content-ref url="inference-automatic-evidence-setting.md" %}
[inference-automatic-evidence-setting.md](inference-automatic-evidence-setting.md)
{% endcontent-ref %}

{% content-ref url="inference-adaptive-questionnaire.md" %}
[inference-adaptive-questionnaire.md](inference-adaptive-questionnaire.md)
{% endcontent-ref %}













[Data Import and Discretization](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/403/bayesialab/e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-6-supervised-learning/data-import-and-discretization)[Supervised Learning: Markov Blanket](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/403/bayesialab/e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-6-supervised-learning/supervised-learning-markov-blanket)[Supervised Learning: Structural Coefficient Analysis](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/403/bayesialab/e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-6-supervised-learning/supervised-learning-structural-coefficient-analysis)[Inference: Automatic Evidence-Setting](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/403/bayesialab/e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-6-supervised-learning/inference-automatic-evidence-setting)[Inference: Adaptive Questionnaire](https://app.gitbook.com/o/uy8P9JV2yeAS4i1oOPyD/s/1hKcv7xZwkBBwCca680v/\~/changes/403/bayesialab/e-book-bayesian-networks-and-bayesialab-a-practical-introduction-for-researchers/chapter-6-supervised-learning/inference-adaptive-questionnaire)

* Data Import and Discretization
* Supervised Learning: Markov Blanket
* Supervised Learning: Augmented Markov Blanket
* Supervised Learning: Structural Coefficient Analysis
* Inference: Automatic Evidence-Setting
* Inference: Adaptive Questionnaire

\
