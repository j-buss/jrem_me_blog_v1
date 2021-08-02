---
title: "Chapter 4 - Model Adequacy Checking"
date: 2021-08-01T11:19:17-05:00
draft: true
tags: [
	"linear regression",
	"R"
]
categories: [
	"Applied Stats",
	"Regression Analysis",
	"Introduction to Linear Regression Analysis - Montgomery/Peck/Vining"
]
katex: true
---
Example Text

## Residuals (as defined from Montgomery/Peck/Vining)

| Name | Formula | r Function |
|---|---|---|
|residual| $e_i = y_i - \hat{y_i}$| resid(_object_) or _object_$residuals|
|standardized residual| $d_i = {e_i \over \sqrt{MS_{res}}}$| resid(_object_) / sqrt(anova(_object_)[[3]][3])|
|studentized residual| $r_i = {e_i \over \sqrt{MS_{res} (1-h_{ii})}}$| 
|hat matrix diagonal| $h_{ii}$| 
|PRESS residual (deleted residuals)| $e_{(i)} = {e_i \over (1-h_{ii})}$| 
|R-student (externally studentized residual)| $$\begin{align*}t_i&= {e_i \over \sqrt{S_{(i)}^{2} (1-h_{ii})}}\\\\\text{\scriptsize where...}\\\\\scriptsize {S_{(i)}^2}&\scriptsize{= { (n-p)MS_{Res}-e_{i}^2 / (i-h_{ii}) \over n-p-1}}\end{align*}$$|...|
|PRESS residual squared| $[{e_i \over (1-h_{ii})}]^2$| 
