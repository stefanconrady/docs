# 🇦🇺 Implementation of Bayesian Networks for Modelling Stress Corrosion Cracking

Presented at the [9th Annual BayesiaLab Conference](./) on October 13, 2021.

### Abstract&#x20;

In the oil and gas industry, materials employed in upstream operations and pipelines operate at elevated pressures and temperatures, while exposed to substantial concentrations of corrosive agents such as chlorides (Clˉ), carbon dioxide (CO2), and hydrogen sulfide (H2S). Such aggressive conditions give rise to different failure mechanisms associated with environmentally assisted cracking (EAC);  predominately stress corrosion cracking (SCC). This corrosion phenomenon is considered a critical threat for production systems, as it can accelerate the mechanical failure of components due to the combined influence of non-cyclic stresses (i.e., residual, external, or operational), and corrosion-oxidation reactions in a reactive environment.

Due to their high mechanical properties and low corrosion rates, the use of corrosion-resistant alloys (CRAs), such as duplex stainless steel (DSS) alloys, have increasingly been employed to improve the integrity of production equipment and transportation facilities. However, the performance of DSS in the hydrocarbon recovery is not well documented in industry standards, such that the operating limits of DSS are often perceived as overly conservative. Thus, the susceptibility of DSS alloys to SCC is actively being investigated to optimize the material selection processes, and thereby ensure the reliability of hydrocarbon production systems. Nonetheless, despite the numerous investigations devoted to describing the SCC phenomenon, a thorough understanding of SCC mechanisms remains elusive.

Given the stochastic nature of failures by corrosion phenomena and the numerous factors involved in SCC, we focus on the implementation of Bayesian networks (BNs) to establish an explanatory framework for the SCC of DSS in downhole environments. Here, we report the initial stage of a BN model, where we exploit the advantage of BNs to reconcile various sources of information sources (e.g., literature relevant to SCC, results from atomistic simulations, experimental data) within one overall framework.

Additionally, we present the use of machine learning (ML) techniques that assisted in the elucidation of the BN configuration. To treat the uncertainty in our dataset due to unobserved data points, we employ advanced data imputation methods (e.g., tree-based models), together with the expectation and maximization (EM) algorithm, and entropy-based models in BayesiaLab. Future plans will also be detailed for which this BN model is intended to predict both the damage stages of DSS, and safe operating thresholds in downhole environments.

### Presentation Video

{% embed url="https://res.cloudinary.com/dvr3obmlj/video/upload/v1695083561/2021-10-13-Conference-Abraham-Rojas_qrrtw8.mp4" %}

### About the Presenter

Abraham Rojas Zuniga\
M.Phil., Ph.D. Candidate\
Faculty of Science and Engineering\
Western Australian School of Mines and Curtin Corrosion Centre,  Curtin University\
[abraham.rojaszuniga@research.uwa.edu.au](mailto:abraham.rojaszuniga@research.uwa.edu.au)

I am a Petroleum Engineer with five years of industry experience. I am particularly interested in the application of various simulation techniques, from deterministic to data-driven approaches, to study different phenomena associated with material science and risk assessment.

### Presentation Materials

{% embed url="https://res.cloudinary.com/dvr3obmlj/image/upload/v1695083571/Abraham_Rojas_Implementation_of_Bayesian_Networks_for_Modelling_Stress_Corrosion_Cracking_hf7ij3.pdf" %}
