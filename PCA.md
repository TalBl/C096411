---
layout: page
permalink: /PCA/
---

- [Introduction](#Introduction)
- [Optimal Problem's Solution](#Solution)
- [Optimal Vector U](#Vector)
- [Optimal Vector V](#VVector)


## PCA

<a name='Introduction'></a>

<hr />

### Introduction:

When the input data set is from a high dimension, for visual reasons or flexible calculations - there is a need to lower the dimension.

#### For example
data set in 2 dimensions:
<p align="center">
	<img src="/C096411/image/less9/Capture.JPG" align="middle">
</p>

After removing one dimension, the set will look like:
<p align="center">
	<img src="/C096411/image/less9/Capture1.JPG" align="middle">
</p>

#### Formally:
For a given data set: <img src="/C096411/image/less9/6.svg" align="middle" width="109.698pt" height="14.4258pt"/> we want to transform it to: <img src="/C096411/image/less9/7.svg" align="middle" width="91.2574pt" height="11.8887pt"/> with maximal variance (information)

#### solve the optimization problem:
<p align="center">
	<img src="/C096411/image/less9/8.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less9/9.svg" align="middle">
</p>

<a name='Solution'></a>

<hr />

### Optimization Problem's Solution:

#### Marking:
<p align="center">
	<img src="/C096411/image/less9/11.svg" align="middle">
</p>

Assuming that the average of <img src="/C096411/image/less9/10.svg" align="middle" width="34.5905pt" height="11.2905pt"/>

For this case to occur, we need to add the assumption: <img src="/C096411/image/less9/13.svg" align="middle" width="76.04pt" height="27.0794pt"/>

The optimization problem searches for vector U such that: <img src="/C096411/image/less9/14.svg" align="middle" width="80.4241pt" height="11.8139pt"/> with maximal variance.

* When we reduce dimensions, there is information loss. With maximal variance there is minimal information loss.
* The assumption is that X1,..,Xm are samples from the Y1,...,Ym probability spaces where the X's are m samples of random variables while attempting to maximize the variance of Y.

Assignment according to the assumptions:

<p align="center">
	<img src="/C096411/image/less9/17.svg" align="middle">
</p>

Where : <img src="/C096411/image/less9/18.svg" align="middle" width="81.9934pt" height="38.7534pt"/>

<p align="center">
	<img src="/C096411/image/less9/19.svg" align="middle">
</p>

* There must be a limit becuase the result includes finite numbers.

With the constraint in the optimization problem, we will use Lagrange multiplier instead:

<p align="center">
	<img src="/C096411/image/less9/20.svg" align="middle">
</p>

To find the vector U, we need to find a derivative. The solution:

<p align="center">
	<img src="/C096411/image/less9/21.svg" align="middle">
</p>

That means: U is an eigenvector of the matrix: <img src="/C096411/image/less9/22.svg" align="middle" width="55.7858pt" height="36.3856pt"/>

<a name='Vector'></a>

<hr />

### Optimal Vector U:

According to the definition of eigenvector: 

<p align="center">
	<img src="/C096411/image/less9/23.svg" align="middle">
</p> 

#### Marking:
We will mark the optimal eigenvector as U with eigenvalue <img src="/C096411/image/less9/24.svg" align="middle" width="7.68736pt" height="9.34643pt"/>

The new optimization problem is:
<p align="center">
	<img src="/C096411/image/less9/25.svg" align="middle">
</p>

Therefor the optimal lambda must be the maximal eigenvalue.

The optimal vector U is the eigenvector of the suitable maximal eigenvalue.

<a name='VVector'></a>

<hr />

### Optimal Vector V:

For a given data set <img src="/C096411/image/less9/27.svg" align="middle" width="87.5006pt" height="14.4258pt"/>, there is need to transform it to <img src="/C096411/image/less9/28.svg" align="middle" width="80.997pt" height="13.9772pt"/>.

#### How to find a vector V which holds maximal information given a vector U?

#### Marking:
<p align="center">
	<img src="/C096411/image/less9/29.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less9/30.svg" align="middle">
</p>

This is a formal description of the need to get maximun information that <img src="/C096411/image/less9/31.svg" align="middle" width="11.1924pt" height="8.41179pt"/> doesn't know.

<p align="center">
	<img src="/C096411/image/less9/32.svg" align="middle">
</p>

According cartesian product's definition:

<p align="center">
	<img src="/C096411/image/less9/33.svg" align="middle">
</p>

With the assumption that U is an eigenvector with lamda as eigenvalue (not equal to 0):

<p align="center">
	<img src="/C096411/image/less9/34.svg" align="middle">
</p>

