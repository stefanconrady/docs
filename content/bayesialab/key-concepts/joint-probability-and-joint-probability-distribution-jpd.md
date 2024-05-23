# Joint Probability & Joint Probability Distribution (JPD)

### Definition

* A Joint Probability Distribution is the distribution of Joint Probabilities.
* A Joint Probability is the probability of specific values of variables jointly occurring in a domain.

### Example

* We observe the variables Hair Color and Eye Color in a population of college students.
* Joint Probability refers to the probability of specific values for Hair Color and Eye Color jointly occurring in this population.
* For instance,&#x20;
  * P(Eye Color=Blue, Hair Color=Blond)=15.86% means that the probability of a student having blue eyes and blond hair in the given population is 15.86%.
  * P(Eye Color=Green, Hair Color=Black)=0.85% means that the probability of having green eyes and black hair in that population is only 0.85%.&#x20;
* We can now look across all possible combinations of Hair Color and Eye Color, compute all Joint Probabilities and list them in a  Joint Probability Table, with one row for each combination of the states of the variables.
* In this example, the size of the Joint Probability Table is manageable: Number of States (Hair Color) × Number of States (Eye Color)  = 4 × 4 = 16&#x20;
*   This Joint Probability Table is a direct and complete representation of the Joint Probability Distribution for the variables Hair Color and Eye Color:\


    | Hair Color | Eye Color | Joint Probability |
    | ---------- | --------- | ----------------: |
    | Black      | Brown     |            11.49% |
    | Brown      | Brown     |            20.10% |
    | Red        | Brown     |             4.39% |
    | Blond      | Brown     |             1.18% |
    | Black      | Blue      |             3.38% |
    | Brown      | Blue      |            14.19% |
    | Red        | Blue      |             2.87% |
    | Blond      | Blue      |            15.88% |
    | Black      | Hazel     |             2.53% |
    | Brown      | Hazel     |             9.12% |
    | Red        | Hazel     |             2.36% |
    | Blond      | Hazel     |             1.69% |
    | Black      | Green     |             0.84% |
    | Brown      | Green     |             4.90% |
    | Red        | Green     |             2.36% |
    | Blond      | Green     |             2.70% |
    |            | **Sum**   |       **100.00%** |

### Relevance

* As the Joint Probability Distribution covers all possible combinations, it represents all regularities and patterns (or the lack thereof) within a domain.
* Knowing the Joint Probability Distribution is required for performing two key operations for data analysis and inference:
  * Marginalization, which is calculating the marginal probability of a variable, e.g., P(Hair Color=Black)=18.25%.
  * Conditioning, which refers to inferring the values of a variable, given a specific value of another variable, e.g., P(Hair Color=Blond | Eye Color=Blue)=43.7%.

### Challenge

* In high-dimensional domains, however, calculating and listing the Joint Probabilities in a Joint Probability Table can become intractable.
* The size of a Joint Probability Table grows exponentially with the number of variables. For example, if we had 20 variables with 4 states each, the size of the corresponding Joint Probability Table would exceed 1 trillion rows.
* While the arithmetic is straightforward, the sheer number of calculations can easily exceed the available computational power, both for generating the Joint Probability Table as well as for performing Marginalization and Conditioning.
* "The only way to deal with such large distributions is to constrain the nature of the variable interactions in some manner, both to render specification and ultimately inference in such systems tractable. The key idea is to specify which variables are independent of others, leading to a structured factorisation of the joint probability distribution. \[Bayesian] Belief Networks are a convenient framework for representing such factorisations into local conditional distributions." (Barber, 2012)
* This means that Bayesian networks are extremely practical for approximating Joint Probability Distributions in complex, high-dimensional problem domains.

### References&#x20;

* Barber, D. (2012). Bayesian Reasoning and Machine Learning. Cambridge: Cambridge University Press. doi:10.1017/CBO9780511804779
