---
title: "Reference - Linear Algebra"
date: 2021-06-27T14:29:01-05:00
draft: true
tags: [
	"python",
	"r",
	"Reference"
]
categories: [
	"Applied Stats"
]
katex: true

---
# Background

This page will likely not be enough for someone to learn linear algebra from scratch. The impetus for this page was a reference for someone who learned linear algebra in the past, but is in need of a refresher. As I am that person in this case, I wanted something to force me to make my notes accessible to some one else in a similar situation. Most of the focus is upon pragmatic ways of performing calculations and less on the background.

This page borrows __very__ heavily from the excellent document [Linear algebra explained in four pages](https://minireference.com/static/tutorials/linear_algebra_in_4_pages.pdf) by Ivan Savov.

## Introduction

Linear algebra is essentially the mathematics of vectors and matrices, so we start with a few definitions.

#### Vector: A vector $\overrightarrow{v} \in R^n$ is an $n$-tuple of real numbers

$$
\overrightarrow{v}=(v_1,v_2,v_3) \in (R, R, R) \equiv R^{3}
$$

#### Matrix: A matrix $A \in R^{m \times n}$ is a rectangular array of real numbers with $m$ rows and $n$ columns

$$
A=\begin{bmatrix}
a_{11}&a_{12}\\\\a_{12}&a_{22}\\\\a_{31}&a_{32}
\end{bmatrix}\in
R^{3 \times 2}$$

### Vector Operations

#### Vector Addition: each value is added to corresponding value on the other vector; all the vecotrs are teh same size

$$
\overrightarrow{u}+\overrightarrow{v}= 
\begin{bmatrix}
u_{1}\\\\u_{2}\\\\u_{3}
\end{bmatrix}
+
\begin{bmatrix}
v_{1}\\\\v_{2}\\\\v_{3}
\end{bmatrix}
\=
\begin{bmatrix}
u_{1}+v_{1}\\\\u_{2}+v_{2}\\\\u_{2}+v_{2}
\end{bmatrix}
$$

#### Scalar Multiplications: multiply each 

$$
\overrightarrow{u}+\overrightarrow{v}= 
\begin{bmatrix}
u_{1}\\\\u_{2}\\\\u_{3}
\end{bmatrix}
+
\begin{bmatrix}
v_{1}\\\\v_{2}\\\\v_{3}
\end{bmatrix}
\=
\begin{bmatrix}
u_{1}+v_{1}\\\\u_{2}+v_{2}\\\\u_{2}+v_{2}
\end{bmatrix}
$$

## Dot Product

## Cross Product

# Matrix Operations

## Matrix Addition

## Matrix Subtraction

## Matrix Product

## Transpose

## Inverse

# Matrix-Vector Product

## Gauss-Jordan for Solving Systems of Equations

## Compute Matrix Inverse
