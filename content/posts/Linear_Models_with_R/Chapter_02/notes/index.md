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
$$
\begin{equation}
Y=\beta_0+\beta_1X_1+\beta_2X_2+\beta_3X_3+\epsilon
\end{equation}
$$
Where $\beta_i,i=0,1,2,3$ are unknown parameters

**Linear** refers to the parameters entering linearly; however the predictors do not have to be linear

Sources of models:
1. Physical Theory exp: Hooke's Law
2. Experience with past data
3. No prior, just exploration

### 2.2 Matrix Representation

Matrix Linear Formula:

$$
\begin{equation}
y=X\beta+\epsilon
\end{equation}
$$

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


#### Total Sum of Squares (TSS): "How much variation are we trying to explain?"
Sum of squared differences between observations $y_{i}$ and the mean $\overline{y}$; 

{{< img src="TSS.png" >}}

$$\begin{equation}
TSS=\sum_{i=1}^{n} ({y_i}-\overline{y})^2
\end{equation}$$


#### Explained Sum of Squares (ESS): "How much of the variation is explained by our model?"

Sum of the squared differences between predicted values $\hat{y_i}$ and the mean $\overline{y}$

{{< img src="ESS.png" >}}

$$
\begin{equation}
ESS=\sum_{i=1}^{n} (\hat{y_i}-\overline{y})^2
\end{equation}
$$

#### Residual Sum of Squares (RSS): "How much variation is left-over...that our model can't explain?"

Sum of the squared differences between the predicted values $\hat{y_i}$ and the observed values $y_{i}$

{{< img src="RSS.png" >}}

$$
\begin{equation}
RSS=\sum_{i=1}^{n} ({y_i}-\hat{y_i})^2
\end{equation}
$$

#### Relation among Sum of Squares:

We can piece together the three components as follows:

$$
\begin{equation}
TSS = ESS + RSS
\end{equation}
$$

#### 2.4.1 Deriving the Least Squares

Based on the definitions of the three Sum of Squared values the better fit model would lead us to minimize the "Residual Sum of Squares". Essentially, make the "unexplained" bit the smallest.

In order to minimize the RSS we take the derivative of equation 5 with respect to $\epsilon$ and $\beta$ (or more precisely the "hatted" versions representing our solved version of the equation) and set them equal to 0 and solve. 

$$
\frac{\partial RSS}{\partial \hat{\epsilon}} = 0
$$
$$
\frac{\partial RSS}{\partial \hat{\beta}} = 0
$$

However, the formula does not actually have $\hat{\epsilon}$ nor $\hat{\beta}$. We need to replace the value of $\hat{y_i}$ with our general linear equation: 


$$
RSS=\sum_{i=1}^{n} ({y_i}-\hat{\epsilon}-\hat\beta{x_i})^2
$$


$$
\begin{equation}
\frac{\partial RSS}{\partial \hat{\epsilon}} = -2\sum_{i=1}^{n} ({y_i}-\hat{\epsilon}-\hat\beta{x_i}) = 0
\end{equation}
$$
$$
\begin{equation}
\frac{\partial RSS}{\partial \hat{\beta}} = -2\sum_{i=1}^{n} {x_i}({y_i}-\hat{\epsilon}-\hat\beta{x_i}) = 0
\end{equation}
$$

Before we go further there are a few formulas that will help make quick work of our derivations.
1. The sum of a set of numbers is equal to the average of that set multiplied by the number in the set

$$
\frac{1}{n}\sum_{i=1}^{n} {x_i}={\overline{x}}
$$

$$
\begin{equation}
\sum_{i=1}^{n} {x_i}=n{\overline{x}}
\end{equation}
$$

$$
\frac{1}{n}\sum_{i=1}^{n} {y_i}={\overline{y}} 
$$

$$
\begin{equation} 
\sum_{i=1}^{n} {y_i}=n{\overline{y}} 
\end{equation}
$$

2. Foil with sums and averages

$$
\begin{equation}
\sum_{i=1}^n({x_i}-\overline{x})({y_i}-\overline{y})=\sum_{i=1}^n{x_i}({y_i}-\overline{y})=\sum_{i=1}^n{y_i}({x_i}-\overline{x})
\end{equation}
$$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Let's start with the left side and show that it equals the first term  

$$
\sum_{i=1}^n({x_i}-\overline{x})({y_i}-\overline{y})
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Expand the terms by performing the "FOIL"
$$
\sum_{i=1}^n({x_i}{y_i} - {x_i}\overline{y} - \overline{x}{y_i} + \overline{x}\overline{y})
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Essentially "distribute" the sum
$$
\sum_{i=1}^{n}{x_i}{y_i} - \overline{y}\sum_{i=1}^n{x_i} - \overline{x}\sum_{i=1}^n{y_i} + \overline{x}\overline{y}\sum_{i=1}^n1
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Substitute the "sums and averages" from equations (9) and (10) 
$$
\sum_{i=1}^{n}{x_i}{y_i} - n\overline{y}\overline{x} - n\overline{y}\overline{x} + n\overline{y}\overline{x}
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Remove the opposite terms
$$
\sum_{i=1}^{n}{x_i}{y_i} - n\overline{y}\overline{x}
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Substitute the "sums and averages" from equation (10) into the second term
$$
\sum_{i=1}^{n}{x_i}{y_i} - \overline{x}\sum_{i=1}^n{y_i}
$$
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"Pull out" the sum and we see that it matches the last 
$$
\sum_{i=1}^{n}{x_i}{y_i} - \overline{x}\sum_{i=1}^n{y_i}
$$




Reference:
1. [Sum of squares](https://www.youtube.com/watch?v=I8cRj0wefi8) 
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
