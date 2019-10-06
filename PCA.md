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

When the input data set is fro high dimension, for visual reasons or flexible calculations - There is a need to lower the dimension.

##### For example
data set in 2 dimension:
<p align="center">
	<img src="/C096411/image/less9/Capture.JPG" align="middle">
</p>

After remove of one dimension, the set will show:
<p align="center">
	<img src="/C096411/image/less9/Capture1.JPG" align="middle">
</p>

##### Formally:
In given data set:
<p align="center">
	<img src="/C096411/image/less9/Capture2.JPG" align="middle">
</p>
we want to transform it to:
<p align="center">
	<img src="/C096411/image/less9/Capture3.JPG" align="middle">
</p>
with maximal variance (information)

solve the optimizal problem:
<p align="center">
	<img src="/C096411/image/less9/Capture4.JPG" align="middle">
</p>

<a name='Solution'></a>

<hr />

### Optimal Problem's Solution:

Marking:
<p align="center">
	<img src="/C096411/image/less9/Capture5.JPG" align="middle">
</p>
assume that average of y = 0

For that case will happend we add assumption: 
<p align="center">
	<img src="/C096411/image/less9/Capture6.JPG" align="middle">
</p>

The optimizal problem searches  for vector U so:
<p align="center">
	<img src="/C096411/image/less9/Capture7.JPG" align="middle">
</p>
with maximal variance.

* When we differ dimension, there is information loss, with maximal variance there is also a save for minimal information loss.
* Assumption that X1,..,Xm are sample from the Y1,...,Ym world where the X are m results of random variable and also trying to maximize the variance of Y.

Place according the assumptions:

<p align="center">
	<img src="/C096411/image/less9/Capture7.JPG" align="middle">
</p>

* There is must to be a limit becuase the result must to be in finite numbers.

With the constraint in the optimal problem, write instaed with Lagrange multiplier:

<p align="center">
	<img src="/C096411/image/less9/Capture8.JPG" align="middle">
</p>

For find the vector U for maximal variance, Need to search derivative:

<p align="center">
	<img src="/C096411/image/less9/Capture9.JPG" align="middle">
</p>

The solution:

<p align="center">
	<img src="/C096411/image/less9/Capture10.JPG" align="middle">
</p>

That means: the optimal U is an eigenvector of the matrix:

<p align="center">
	<img src="/C096411/image/less9/Capture11.JPG" align="middle">
</p> 

<a name='Vector'></a>

<hr />

### Optimal Vector U:

According the definition of eigenvector:
<p align="center">
	<img src="/C096411/image/less9/Capture12.JPG" align="middle">
</p> 

Marking:
Optimal eigenvector is u with eigenvalue lamda.

The new optimal problem is:
<p align="center">
	<img src="/C096411/image/less9/Capture13.JPG" align="middle">
</p>

Thats follow that lamda must be the maximal eigenvalue.

The optimal vector u us the eigenvector of the suitable maximal eigenvalue.

<a name='VVector'></a>

<hr />

### Optimal Vector V:

In given data set X1,...,Xm, There us==is need to transform it to Y1,...,Ym - dimension size 2.

How find vector V which give maximal information with given vector U?

Marking:
<p align="center">
	<img src="/C096411/image/less9/Capture14.JPG" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less9/Capture15.JPG" align="middle">
</p>

Formal way to describe the need to get maximun information that Y1 doesn't see:

<p align="center">
	<img src="/C096411/image/less9/Capture16.JPG" align="middle">
</p>

According definition of covatiance:

<p align="center">
	<img src="/C096411/image/less9/Capture17.JPG" align="middle">
</p>

According the marking:

<p align="center">
	<img src="/C096411/image/less9/Capture18.JPG" align="middle">
</p>

According cartesian product's definition:

<p align="center">
	<img src="/C096411/image/less9/Capture19.JPG" align="middle">
</p>

With the assumption u is an eigenvector with lamda as eigenvalue (not equal to 0):

<p align="center">
	<img src="/C096411/image/less9/Capture20.JPG" align="middle">
</p>

