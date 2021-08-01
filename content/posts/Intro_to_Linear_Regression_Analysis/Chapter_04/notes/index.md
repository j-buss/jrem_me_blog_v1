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

## Residuals

| Name | Formula |
| ---- | ------- |
|residual| $e_i = y_i - \hat{y_i}$| 
|standardized residual| $d_i = {e_i \over \sqrt{MS_{res}}}$| 
|studentized residual| $r_i = {e_i \over \sqrt{MS_{res} (1-h_{ii})}}$| 
|hat matrix diagonal| $h_{ii}$| 
|PRESS residual (deleted residuals)| $e_{(i)} = {e_i \over (1-h_{ii})}$| 
|R-student (externally studentized residual)| $t_i = {e_i \over \sqrt{S_{(i)}^{2} (1-h_{ii})}}$| 
|PRESS residual squared| $[{e_i \over (1-h_{ii})}]^2$| 
