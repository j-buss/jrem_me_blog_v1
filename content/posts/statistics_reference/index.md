---
title: "Reference - Statistics and Probability"
date: 2021-07-03T21:21:32-05:00
draft: false
tags: [
	"Reference"
]
categories: [
	"Applied Stats"
]
katex: true
---
CHANGES

## Background
This page is a refresher. Someone, may have studied statistics long ago and is in need of a reference.

This page borrows quite heavily from the [MIT Statistics Cheat Sheet](https://web.mit.edu/~csvoss/Public/usabo/stats_handout.pdf)

---

- **Population:** The entire group one desires information about
- **Sample:** A subset of the population taken because the entire population is usually too large to analyze; Its characteristics are taken to be representative of the population
- **Mean:** (average); The sum of all values in the sample divided by the number of values in the sample; 
	- $\mu$ = population mean 
	- $\overline{x}$ = sample mean
- **Median:** the value separating the higher half of a sample/population from lower half 
	- It is the middle value when all values arranged lowest to highest (or avg of middle two if even number of items)
- **IQR:** the middle 50%, calculated as Q3 - Q1
- **1.5 * IQR Outlier:** identification of outliers
	- Q1 - 1.5 IQR
	- Q3 + 1.5 IQR
- **Variance:** Measures dispersion around the mean; squared units  
	- Of population:
$$
\sigma^{2}={\sum (x-\mu)^2 \over n}
\hspace7ex 
or
\hspace7ex 
\sigma^{2}={\sum x^2 \over n} - \mu^{2}
$$
	- Of sample:
$$
s^{2}={\sum (x-\overline{x})^2 \over n-1}
\hspace7ex 
or
\hspace7ex 
s^{2}={\sum x^2 - {\small{(\sum x )^2 \over n}} \over n-1}
$$
- **Standard Deviation:** square root of variance; measure of dispersion around the mean, same units as values
	- $\sigma$ = population standard deviation
$$
\sigma=\sqrt{{\sum (x-\mu)^2 \over n}}
\hspace7ex 
or
\hspace7ex 
\sigma=\sqrt{{\sum x^2 \over n} - \mu^{2}}
$$
	- $s$ = sample standard deviation
$$
s=\sqrt{{\sum (x-\overline{x})^2 \over n-1}}
\hspace7ex 
or
\hspace7ex 
s=\sqrt{{\sum x^2 - {\small{(\sum x )^2 \over n}} \over n-1}}
$$
- **Standard Error:** an estimate of standard deviation of sampling distribution; the set of all samples of size $n$ that can be taken from a population; Reflects the extent to which a statistic changes from sample to sample
	- For mean - Exact Value:
$$
\sigma_{\overline{x}} = {\sigma \over \sqrt{n}}
$$
	- For mean - Estimate:
$$
\sigma_{\overline{x}} \approx {\sigma_{x} \over \sqrt{n}}
\hspace7ex 
or
\hspace7ex 
\widehat{\sigma_{\overline{x}}} = {\sigma_{x} \over \sqrt{n}}
\hspace7ex 
or
\hspace7ex 
s_{\overline{x}} = {s \over \sqrt{n}}
$$

	- Note: Confusion exists between the similar values:
		- $\sigma$ = standard deviation of the population
		- $\sigma_{x}$ = standard deviation of the sample
		- $\sigma_{\overline{x}}$ = standard deviation of the mean
		- $\widehat{\sigma_{\overline{x}}}$ = estimator of the standard deviation of the mean (standard error)
- **Normal Distribution (aka Gaussian Distribution):** A type of continuous probability distribution for real-valued random variables
	- Generalized probability density function (pdf)
$$
f(x) = {1 \over {\sigma \sqrt{2 \pi}} } \hspace1ex e^{{-1 \over 2}{\left({x - \mu} \over \sigma \right)^2}}
$$
	- X is a normally distributed random variable with mean $\mu$ and standard deviation $\sigma$
$$
X \sim N(\mu, \sigma^2)
$$
	- To standardize the distribution, or finding the **z-score**, subtract $\mu$ from x and divide it by the standard deviation $\sigma$
$$
Z = {{x - \mu} \over \sigma}
$$
	- Then we say that Z has a standard normal distribution where:
$$
Z \sim N(0, 1)
$$
- **Joint Probability:** the probability of events A and B occurring
	- $P(A \space and \space B) = P(A) \times P(B)$ when events $A$ and $B$ are independent
- **Union of Events:** the probability of either event A or event B occurring
	- $P(A \space or \space B) = P(A) + P(B)$ - P(A \space and \space B)
- **Conditional Probability:** the probability of event A occurring given that event B has occured
$$
P(A \vert B) = {P(A \space and \space B) \over P(B)}
\hspace7ex
or
\hspace7ex
P(A \vert B) = {P(B \vert A) \times P(A) \over P(B)}
$$
- **Pearson's Correlation Coefficient for a sample**
	- $$r_{xy} = {\sum_{i=1}^{n} (x_1 - \overline{x})(y_i = \overline{y}) \over sqrt{ \sum_{i=1}TBD....$$
- **Coefficient of DEtermination** - $r^2$tells us what percent of the variability in the y variable is accounted for by the regression on the x variable.
	- $$r^2 = 1 - {SS_{res} \over SS_{tot}}$$
