# Latent Variables, Factors, and Hidden Nodes vs. Manifest Variables

### Context <a href="#h2__1212884521" id="h2__1212884521"></a>

* Latent Variables (or Factors) and Manifest Nodes are central to building many types of models in BayesiaLab, including [Probabilistic Structural Equation Models](https://bayesia.clickhelp.co/articles/bayesialab/8-probabilistic-structural-equation-models-key-driver-analysis).

### Manifest Variables <a href="#h2_1721109018" id="h2_1721109018"></a>

* A Manifest Variable is a variable for which there are recorded observations from a given domain.
* Manifest Variables include variables such as the temperature, speed, or mass of an object, i.e., properties that are generally measurable.
* Furthermore, survey responses are also typical Manifest Variables, as they refer to ratings or assessments directly stated by respondents. In this case, a consumer's opinion is made manifest in the survey response.

{% hint style="info" %}
manifest (adj.), late 14c., "clearly revealed to the eye or the understanding, open to view or comprehension," from Old French manifest "evident, palpable," (12c.), or directly from Latin manifestus "plainly apprehensible, clear, apparent, evident;" of offenses, "proved by direct evidence;" of offenders, "caught in the act."
{% endhint %}

### Latent Variables, Factors, and Hidden Nodes <a href="#h2_494253159" id="h2_494253159"></a>

* A **Latent** variable (or **Factor**), as opposed to a Manifest Variable, is a variable that cannot be directly observed. As a result, such a variable would not be recorded in a dataset collected from the original problem domain.
* Latent typically refers to a theoretical or "hidden" concept or construct that cannot be observed directly, such as safety, health,  freedom, etc.
* Connecting Latent Variables to several Manifest Variables often allows inferring values of the Latent Variables based on the measurements of the Manifest Variables.
* Prior to inferring the values of a newly-created Latent Variable, it would appear as a Hidden Node ![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1686184216/BayesiaLab\_Icons/N8-Hidden\_cpojfy.svg) on BayesiaLab's Graph Panel.
* For instance, values for the Latent VariableHealth could be inferred from a patient's Manifest Variables, such as body mass index, blood pressure, heart rate, lung function, etc.
* The term Factor is entirely equivalent to Latent Variable. In the Bayesia Knowledge Base & Library, we use both terms interchangeably. Occasionally, we also refer to a Latent Factor, which is also the same.&#x20;
* Using Factor expresses intuitively that a Latent Variable can be a hidden cause of Manifest Variables. Consistent with the Latin origin of the word, a Factor can be the "doer" or "maker" behind Manifest Variables.

{% hint style="info" %}
latent (adj.), mid-15c., "concealed, secret," from Latin latentem (nominative latens) "lying hid, concealed, secret, unknown," present participle of latere "lie hidden, lurk, be concealed."
{% endhint %}

{% hint style="info" %}
factor (n.), early 15c., "commercial agent, deputy, one who buys or sells for another," from French facteur "agent, representative" (Old French factor, faitor "doer, author, creator"), from Latin factor "doer, maker, performer," in Medieval Latin, "agent," agent noun from past participle stem of facere "to do."
{% endhint %}

### See Also <a href="#h2__906965808" id="h2__906965808"></a>

* Probabilistic Structural Equation Models
* Webinar: Factor Analysis Reinvented—Probabilistic Latent Factor Induction
* Difference between SEM and PSEM Factors
