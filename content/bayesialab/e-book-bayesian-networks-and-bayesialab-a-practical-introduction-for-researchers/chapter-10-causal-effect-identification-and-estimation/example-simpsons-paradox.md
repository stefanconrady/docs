# Example: Simpson's Paradox

### Introduction <a href="#h2__1296687178" id="h2__1296687178"></a>

Simpson’s Paradox illustrates the implications of falsely assuming ignorability. This will lead us to abandon the idea of ignorability and, along with it, the potential outcomes framework and replace it with a formal identification and estimation process that relies on graphical models.

We will use an example that appears trivial on the surface but which has produced countless instances of false inference throughout the history of science. Due to its counterintuitive nature, this example has become widely known as Simpson’s Paradox ([Wall Street Journal, Dec. 2, 2009](https://www.wsj.com/articles/SB125970744553071829)).

This is an important exercise as it illustrates how an incorrect interpretation of an association can produce bias. The word “bias” may not necessarily strike fear into our hearts. In our common understanding, “bias” implies “inclination” and “tendency,” and it is perhaps not a particularly forceful expression. Hence, we may not be overly troubled by a warning about bias. However, Simpson’s Paradox shows how bias can lead to catastrophically wrong estimates.

### Does the Treatment Kill Patients? <a href="#h2__1377386151" id="h2__1377386151"></a>

A hypothetical disease equally affects men and women. An observational study finds that a certain treatment is linked to an increase in the recovery rate among all treated patients from 40 to 50%. Based on the study, this new treatment is widely recognized as beneficial and subsequently promoted as a new therapy.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691099110/SimpsonTreatmentRecovered_izbrne.svg" alt="" width="375"><figcaption></figcaption></figure>

We can imagine a headline along the lines of “New Therapy Increases Recovery Rate by 10%.” However, when examining patient records by gender, the recovery rate for male patients—upon treatment—decreases from 70% to 60%; for female patients, the recovery rate declines from 30% to 20%. Men are, therefore, more likely to recover than women, with or without treatment.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691099418/SimpsonGenderTreatmentRecovered_plaxug.svg" alt="" width="375"><figcaption></figcaption></figure>

So, is this new treatment effective overall or not? This puzzle can be resolved by realizing that, in this observed population, there was an unequal application of the treatment to men and women, i.e., some type of self-selection occurred. More specifically, 75% of male patients and only 25% of female patients received the treatment. Although the reason for this imbalance is irrelevant for inference, one could imagine that the side effects of this treatment are much more severe for females, who thus seek alternative therapies. As a result, there is a greater share of men among treated patients. Given that men have a better a priori recovery prospect with this type of disease, the recovery rate of all treated patients increases. So, what is the true causal effect of this treatment?

### Synthetic Data <a href="#h2__1566336405" id="h2__1566336405"></a>

Our particular manifestation of Simpson’s Paradox is not very far-fetched, but it is still fictional. Therefore, we must rely on synthetic data to make this problem domain tangible for our study efforts. We generate 1,200 observations by sampling from the joint probability distribution of the original Data-Generating Process (DGP). Needless to say, for this dataset to be a suitable example for non-experimental observations like we would find in them under real-world conditions, the true DGP is not known but merely an assumption.

Our synthetic dataset consists of three variables with two discrete states each:

* X (Treatment): Yes (1)/No (0)
* Y (Outcome): Recovered (1)/Not Recovered (0)
* Z (Gender): Male (1)/Female (0)

The following table shows a preview of the first ten rows of the dataset:

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1691108327/SimpsonsParadoxData_qx9qrj.svg" alt="" width="375"><figcaption></figcaption></figure>

### Data Download

[![](https://res.cloudinary.com/dvr3obmlj/image/upload/v1691109035/csv\_v1imah.svg) Simpson.csv](https://res.cloudinary.com/dvr3obmlj/raw/upload/v1691108395/Simpson\_a0gagj.csv)\
