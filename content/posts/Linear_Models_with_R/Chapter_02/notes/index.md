---
title: "Chapter 2 - Estimation"
date: 2021-05-31T14:19:06-05:00
description: 
draft: true
tags: [
	"R",
	"linear regression"
	]
categories: [
	"Applied Stats",
	"Regression Analysis",
	"Linear Models with R - Julian J. Faraway"
	]
image: "estimation.jpg"
katex: true

---
### 2.1 Linear Model
Generic Linear Model: 
$$Y=\beta_0+\beta_1X_1+\beta_2X_2+\beta_3X_3+\epsilon$$
Where $\beta_i,i=0,1,2,3$ are unknown parameters

**Linear** refers to the parameters entering linearly; however the predictors do not have to be linear

Sources of models:
1. Physical Theory exp: Hooke's Law
2. Experience with past data
3. No prior, just exploration

### 2.2 Matrix Representation

Matrix Linear Formula:

$y=X\beta+\epsilon$

where $y=(y_1,\ldots,y_n)^T,\epsilon=(\epsilon_1,\ldots,\epsilon_n)^T,\beta=(\beta_1,\ldots,\beta_n)^T$ and:

$$X=\left( \begin{array}{cccc}
1&x_{11}&x_{12}&x_{13}\\\\ 1&x_{21}&x_{22}&x_{23}\\\\\cdots&\cdots&\cdots&\cdots\\\\1&x_{n1}&x_{n2}&x_{n3}
\end{array} \right)$$

### 2.3 Estimating $\beta$

- Find $\beta$ so that $X\beta$ is as close to $Y$ as possible, let's call it $\widehat{\beta}$ 
- The response predicted by the model is $\widehat{y}=X\widehat{\beta}$
- predicted values (or fitted values): $\widehat{y}$ 
- residual: $\widehat{\epsilon}$


> "The conceptual purpose of the model is to represent, as accurately as possible, something complex, $y$, whici is $n$-dimensional, in terms of something much simpler, the model, which is $p$-dimensional. Thus if our model is successful, the structure in the data should be captured in those $p$ dimension, leaving just random variation in the residuals which lie in an $(n-p)$-dimensional space" - Julian J. Faraway

### 2.4 Least Squares Estimation

**Total Sum of Squares (TSS):** Sum over all squared differences between observations and the overall mean $\overline{y}$

$$TSS=\sum_{n=1}^{n} ({y_i}-\overline{y})^2$$
$y_{i}=$value in a sample; $\overline{y}=$mean value of a sample

__Explained Sum of Squares (ESS):__ Sum of the squares of the deviations of the predicted values from the mean value of a response variable; "how much of the variation is explained by our model?"

$$ESS=\sum_{n=1}^{n} (\hat{y_i}-\overline{y})^2$$
$$y_{i}=value in sample$$
$$\overline{y}=mean value of a sample$$

**Residual Sum of Squares (RSS):** Sum of the squares of the deviations of the predicted values from the true values of the response variable
$$RSS=\sum_{n=1}^{n} ({y_i}-\hat{y_i})^2$$
$$y_{i}=value in sample$$
$$\hat{y_i}=predicted value of a sample$$

Total Sum of Squares (TSS) = Explained Sum of Squares (ESS) + Residual Sum of Squares (RSS)

[Sum of squares](https://www.youtube.com/watch?v=I8cRj0wefi8)

#### 2.4.1 Least Squares Derivation

Reference:
1. [Deriving Least Squares Estimators - part 1](https://www.youtube.com/watch?v=Hi5EJnBHFB4)
2. [Deriving Least Squares Estimators - part 2](https://www.youtube.com/watch?v=hGv9fnmlYaU)
3. [Deriving Least Squares Estimators - part 3](https://www.youtube.com/watch?v=jF3_s2wqPGQ)
4. [Deriving Least Squares Estimators - part 4](https://www.youtube.com/watch?v=AIjuYfjU9dc)
5. [Deriving Least Squares Estimators - part 5](https://www.youtube.com/watch?v=JC0Tm9j-k80)

#### 2.4.2 Lease Squares Derivation - Matrix

### 2.5 Examples of Calculating $\widehat\beta$

### 2.6 Example

### 2.7 QR Decomposition
### 2.8 Gauss-Markov Theorem
### 2.9 Goodness of Fit
### 2.10 Identifiability
### 2.11 Orthogonality
