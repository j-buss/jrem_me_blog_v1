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

Refer to the values in the matrix as $a_{ij}$ where $i$ is the row number and $j$ is the column number. So $a_{32}$ is the element in the 3rdd row and 2nd column of the matrix.

$$
A=\begin{bmatrix}
a_{11}&a_{12}\\\\a_{21}&a_{22}\\\\a_{31}&a_{32}
\end{bmatrix}\in
R^{3 \times 2}$$

### Vector Operations

#### Vector Addition: 
each value is added to corresponding value on the other vector; all the vecotrs are teh same size

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
u_{1}+v_{1}\\\\u_{2}+v_{2}\\\\u_{3}+v_{3}
\end{bmatrix}
$$

#### Scalar Multiplications: 
multiply each item in the vector by the scalar

$$
\alpha \cdot \overrightarrow{u}= 
\begin{bmatrix}
\alpha \cdot u_{1}\\\\ \alpha \cdot u_{2}\\\\ \alpha \cdot u_{3}
\end{bmatrix}
$$

#### Vector Length: 
determine length of vector using the pythagorean theorem across all dimensions of the vector 

$$
\Vert \overrightarrow{u} \Vert = \sqrt{u_{1}^2+u_{2}^2+u_{3}^2}
$$

#### Dot Product: 
a multiplication step that results in a scalar; calculated 2 ways

##### A. each member of a vector is multipled by the corresponding member of the other vector;

$$
\overrightarrow{u}\cdot\overrightarrow{v}= 
\begin{bmatrix}
u_{1}\\\\u_{2}\\\\u_{3}
\end{bmatrix}
\cdot
\begin{bmatrix}
v_{1}\\\\v_{2}\\\\v_{3}
\end{bmatrix}
\=
u_{1} \cdot v_{1} + u_{2} \cdot v_{2} + u_{3} \cdot v_{3}
$$

##### B. the length of each vector is multiplied together in addition to the cosine of the angle between


$$
\overrightarrow{u}\cdot\overrightarrow{v}= 
\Vert \overrightarrow{u} \Vert \cdot \Vert \overrightarrow{v} \Vert \cdot \cos{\theta}
$$

##### Note: the two vectors are orthogonal if the dot product is 0; 
$$ \overrightarrow{u}\cdot\overrightarrow{v}= \Vert \overrightarrow{u} \Vert \cdot \Vert \overrightarrow{v} \Vert \cdot \cos{90 \degree} = 0 $$

#### Cross Product: a type of multiplication operation that results in a vector

ignoring a horizontal line at a time; cross multiply remaining terms

$$
\overrightarrow{u}\times\overrightarrow{v}= 
\begin{bmatrix}
u_{1}\\\\u_{2}\\\\u_{3}
\end{bmatrix}
\times
\begin{bmatrix}
v_{1}\\\\v_{2}\\\\v_{3}
\end{bmatrix}
\=
\begin{bmatrix}
u_{2}v_{3}-u_{3}v_{2}\\\\u_{3}v_{1}-u_{1}v_{3}\\\\u_{1}v_{2}-u_{2}v_{1}
\end{bmatrix}
$$

##### Cross Product Norm: 

$$
\Vert \overrightarrow{u} \times \overrightarrow{v} \Vert =
\Vert \overrightarrow{u} \Vert \cdot \Vert \overrightarrow{v} \Vert \cdot \sin{\theta}
$$

##### Commutative Property for Cross Product does __NOT__ hold
$$
\overrightarrow{u} \times \overrightarrow{v} \neq \overrightarrow{v} \times \overrightarrow{u}
$$
$$
\overrightarrow{u} \times \overrightarrow{v} = -\overrightarrow{v} \times \overrightarrow{u}
$$

##### Right hand rule: 

{{< imgproc right_hand_rule.png Resize "200x" />}}

### Matrix Operations


#### Matrix Addition

For matrix addition all the matrixes being added must be of the same size. Adding matrices you add each of the corresponding values from the two matricesyou add each of the corresponding values from the two matrices

$$
A + B = 
\begin{bmatrix}
a_{11}&a_{12}\\\\a_{21}&a_{22}
\end{bmatrix}
+
\begin{bmatrix}
b_{11}&b_{12}\\\\b_{21}&b_{22}
\end{bmatrix} = 
\begin{bmatrix}
a_{11}+b_{11}&a_{12}+b_{12}\\\\a_{21}+b_{21}&a_{22}+b_{22}
\end{bmatrix}
$$


In shorthand this becomes:
$$
C = A + B
\Leftrightarrow
c_{ij} = a_{ij} + b_{ij}
$$ 

#### Matrix Subtraction

Matrix subtraction is the same but with an inverse:

$$ A - B = 
\begin{bmatrix}
a_{11}&a_{12}\\\\a_{21}&a_{22}
\end{bmatrix} -
\begin{bmatrix}
b_{11}&b_{12}\\\\b_{21}&b_{22}
\end{bmatrix} = 
\begin{bmatrix}
a_{11}-b_{11}&a_{12}-b_{12}\\\\a_{21}-b_{21}&a_{22}-b_{22}
\end{bmatrix}
$$

In shorthand this becomes:
$$
C = A - B
\Leftrightarrow
c_{ij} = a_{ij} - b_{ij}
$$ 

#### Matrix Product

If: 
$$
A \in R ^{3 \times 2};\thickspace\thickspace B \in R ^{2 \times 2}; \thickspace\thickspace C \in R ^{3 \times 2}
$$
Then:
$$
AB=C
$$

$$
AB = 
\begin{bmatrix}
a_{11}&a_{12}\\\\a_{21}&a_{22}\\\\a_{31}&a_{32}
\end{bmatrix}
\times
\begin{bmatrix}
b_{11}&b_{12}\\\\b_{21}&b_{22}
\end{bmatrix} = 
\begin{bmatrix}
a_{11}b_{11}+a_{12}b_{21}&a_{11}b_{12}+a_{12}b_{22}\\\\a_{21}b_{11}+a_{22}b_{21}&a_{21}b_{12}+a_{22}b_{22}\\\\a_{31}b_{11}+a_{32}b_{21}&a_{31}b_{12}+a_{32}b_{22}
\end{bmatrix} = C
$$

##### Commutative property for Matrix multiplication does __NOT__ hold

$$
AB \neq BA
$$

#### Transpose
This operation flips a matrix over its diagnoal; that is, it switches the row and column indices of the matrix; the transpose of $A$ is depicted $A^{T}$

$$
A^{T} = 
\begin{bmatrix}
\alpha_{1}&\beta_{1}\\\\\alpha_{2}&\beta_{2}\\\\\alpha_{3}&\beta_{3}
\end{bmatrix}^{T}=
\begin{bmatrix}
\alpha_{1}&\alpha_{2}&\alpha_{3}\\\\\beta_{1}&\beta_{2}&\beta_{3}
\end{bmatrix}
$$

A vector transpose is a special case; essentially as a 1-column matrix

$$
\overrightarrow{u}= 
\begin{bmatrix}
u_{1}\\\\u_{2}\\\\u_{3}
\end{bmatrix};\hspace3ex
\overrightarrow{u}^{T}= 
\begin{bmatrix}
u_{1}&u_{2}&u_{3}
\end{bmatrix}
$$

#### Inverse
The inverse of a matrix $A$ is depicted by $A^{-1}$; 
$$AA^{-1} = I$$ 
Where $I$ is the Identity Matrix
$$
I =
\begin{bmatrix}
1&\hspace2ex&0\\\\\space&\ddots&\space\\\\0&\hspace2ex&1
\end{bmatrix}
$$
Given this property of the inverse it is extremely useful in solving equations to remove a term from one side of an equation. In the following example we "hit" the equation with $A^{-1}$ to remove it from the left side.

$$
\begin{align*}
XA&=B\\\\XAA^{-1}&=BA^{-1}\\\\X&=BA^{-1}
\end{align*}
$$

The steps can be duplicated for multiple variables, but care must be taken to ensure correct ordering and direction:
- $C^{-1}$ from the right
- $A^{-1}$ from the left
- $B^{-1}$ from the left

$$
\begin{align}
ABXC&=D\\\\ABXCC^{-1}&=DC^{-1}\\\\A^{-1}ABX&=A^{-1}DC^{-1}
\end{align}
$$

# Matrix-Vector Product

## Gauss-Jordan for Solving Systems of Equations

## Compute Matrix Inverse
