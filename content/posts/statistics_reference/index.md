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
