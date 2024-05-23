# Chapter 7: Unsupervised Learning

Unsupervised Structural Learning is perhaps the purest form of knowledge discovery, as no hypotheses are constraining the exploration of possible relationships between variables. BayesiaLab offers a wide range of algorithms for that purpose. Making this technology easily accessible can potentially transform how researchers approach high-dimensional problem domains.

{% hint style="info" %}
This chapter was written based on version 5.4 of BayesiaLab running on a Mac. All screenshots reflect that configuration.&#x20;
{% endhint %}

### Example: Stock Market <a href="#h2_814281780" id="h2_814281780"></a>

We find the mass of data available from financial markets to be an ideal proving ground for experimenting with knowledge discovery algorithms that generate Bayesian networks. Comparing machine-learned knowledge with our personal understanding of the stock market can perhaps allow us to validate BayesiaLab’s “discoveries.” For instance, any structure that is discovered by BayesiaLab’s algorithms should be consistent with an equity analyst’s understanding of fundamental relationships between stocks.

In this chapter, we will utilize Unsupervised Learning algorithms to automatically generate Bayesian networks from daily stock returns recorded over a six-year period. We will examine 459 stocks from the S\&P 500 index, for which observations are available over the entire timeframe. We selected the S\&P 500 as the basis for our study, as the companies listed on this index are presumably among the best-known corporations worldwide, so even a casual observer should be able to critically review the machine-learned findings. In other words, we are trying to machine learn the obvious, as any mistakes in this process would automatically become self-evident. Quite often, experts’ reaction to such machine-learned findings is, “Well, we already knew that.” Indeed, that is the very point we want to make, as machine learning can—within seconds—catch up with human expertise accumulated over the years and then rapidly expand beyond what is already known.

The power of such algorithmic learning will be still more apparent in entirely unknown domains. However, if we were to machine learn the structure of a foreign equity market for expository purposes, we would probably not be able to judge the resulting structure as plausible or not.

In addition to generating human-readable and interpretable structures, we want to illustrate how we can immediately use machine-learned Bayesian networks as “computable knowledge” for automated inference and prediction. Our objective is to gain both a qualitative and quantitative understanding of the stock market by using Bayesian networks. In the quantitative context, we will also show how BayesiaLab can carry out inference with multiple pieces of uncertain and even conflicting evidence. The ability of Bayesian networks to perform computations under uncertainty makes them suitable for a wide range of real-world applications.

### Dataset <a href="#h3__128727182" id="h3__128727182"></a>

The S\&P 500 is a free-float capitalization-weighted index of the prices of 500 large-cap common stocks actively traded in the United States, which has been published since 1957. The stocks included in the S\&P 500 are those of large publicly held companies that trade on either of the two largest American stock market exchanges; the New York Stock Exchange and the NASDAQ. For our case study, we have tracked the daily closing prices of all stocks included in the S\&P 500 index from January 3, 2005, through December 30, 2010, only excluding those stocks that were not traded continuously over the entire study period. This leaves a total of 459 stock prices with 1,510 observations each. The top three panels show the S\&P 500 Index, plus the stock prices for Apple Inc. and Yahoo! Inc. Note that the plot of the S\&P 500 Index is only shown for reference; the index will not be included in the analysis.

### Data Preparation and Transformation <a href="#h3_295044639" id="h3_295044639"></a>

Rather than treating the time series in levels, we difference the stock prices and compute the daily returns. More specifically, we will take differences in the logarithms of the levels, which is a good approximation of the daily stock return in percent. After this transformation, 1,509 observations remain. The bottom three panels display the returns.

<figure><img src="https://res.cloudinary.com/dvr3obmlj/image/upload/v1690847163/17_hsw0p7.webp" alt=""><figcaption></figcaption></figure>

### Analysis Workflow <a href="#h3_1029999305" id="h3_1029999305"></a>

{% content-ref url="data-import.md" %}
[data-import.md](data-import.md)
{% endcontent-ref %}

{% content-ref url="unsupervised-learning.md" %}
[unsupervised-learning.md](unsupervised-learning.md)
{% endcontent-ref %}

{% content-ref url="inference.md" %}
[inference.md](inference.md)
{% endcontent-ref %}
