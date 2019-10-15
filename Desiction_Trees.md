---
layout: page
mathjax: true
permalink: /DT/
---

### To Tutorial Page:

<a href="https://talbl.github.io/C096411/HTDT">
Tutorial Desicion Trees
</a>

- [Introduction](#Introduction)
- [Bagging](#Bagging)
- [Random Forest](#RandomForest)
- [K-Nearest Neighbors](#KNN)

<hr />

### Lecture

<hr />

## Desicion trees

<a name='Introduction'></a>

<hr />

### Introduction:

In this classifier the decision in choosen during a process like that for example:
<p align="center">
	<img src="/C096411/image/less7/Capture2.gif" align="middle">
</p>

The tree creation is a black box in this course, according the building algorithm the tree is built - there are diffrent possible trees for the same problem.

#### Classification Tree

The labels are 'Yes' or 'No'.
Leave in this kind of tree is where all the examples in it have the same labels.

For example:
<p align="center">
	<img src="/C096411/image/less7/Capture2.gif" align="middle">
</p>

#### Regression Tree

The classification is a retional number.
Leaf in this kind of tree has examples with diffrent classification.
Leaf value is the average of his examples's classification.

For example:
<p align="center">
	<img src="/C096411/image/less7/Capture3.gif" align="middle">
</p>

#### Overfitting in Decision Trees

The tree creation can lead to tree with full saperation.
With assumption that the training set may has few mistakes or bias.
The full separation is when the tree is too accurate to the training set, will lead that also the tree has this bias.
This is overfitting which can cuase to bias in the test set.
Beacuase of this is needed to know when to stop the tree creation before it is too accurate.


<a name='Bagging'></a>

<hr />

### Bagging:

The algotithm for the overfitting problem.

Definition:
Tb(X) - Random variable for subset of the training set.

Instead of training one tree on the whole training set, The algorithm generates B new training sets Di according to Tb variable.
The algorithm train B trees, each for a subset training set.
When new example comes the algorithm classify it on the B trees and return the average of given classifications.

The Problem with use random variable is his variance.
For minimize it, the algorithm uses with B independence trees.

##### Definition of independence:

<p align="center">
	<img src="/C096411/image/less7/8.svg" align="middle">
</p> are independence where:

- Eatc tree build from subgroup s from S

- For each subgroup <p align="center">
	<img src="/C096411/image/less7/11.svg" align="middle">
</p>

##### Theorem:

<p align="center">
	<img src="/C096411/image/less7/1.svg" align="middle">
</p>


##### Proof:
Marking:
<p align="center">
	<img src="/C096411/image/less7/2.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less7/3.svg" align="middle">
</p>

According variance definition:

<p align="center">
	<img src="/C096411/image/less7/3_1.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less7/4.svg" align="middle">
</p>

Saperaion where b are equals and where they are not:

<p align="center">
	<img src="/C096411/image/less7/5.svg" align="middle">
</p>


In the first bracket: the mean equals to 0 
In the second bracket: the mean equals M

<p align="center">
	<img src="/C096411/image/less7/6.svg" align="middle">
</p>

#### Conclusion:
Algorithm Bagging minimize the variance if the Tb(x) are independence.


<a name='RandomForest'></a>

<hr />

### Random Forest:
The algorithm get as input dependence trees and build forest with smaller correlation between the trees

For each b=1,2,...,B build tree Tb for subgroup Sb belongs to S in the following steps:
	- Choose r indexes random (features) from 1,..,d
	- Choose split in the tree acording the r choosen indexes
	- create 2 vertexes according the split
	
That way creates B trees which are building the forest we want.
(The random choices in the algotithm that what bring the smaller correlation)

##### Theorem:
If the trees dependence:

Marking the correlation between the trees:
</p>
<p align="center">
	<img src="/C096411/image/less7/12.svg" align="middle">
</p>

The variance equals to:
</p>
<p align="center">
	<img src="/C096411/image/less7/13.svg" align="middle">
</p>

Becuase of that when the trees are dependence, it is better to use with Random Forest
That it is put as aim to break the correlation between the trees.

##### Proof:

<p align="center">
	<img src="/C096411/image/less7/18.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less7/18_1.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less7/19.svg" align="middle">
</p>

<a name='KNN'></a>

<hr />

### K - Nearest Neighbors:

#### Nearest Neighbor:

</p>
<p align="center">
	<img src="/C096411/image/less7/Capture.gif" align="middle">
</p>

Input data set of points with labels and unclassified point.
The algorithm determains the classify according the closest point from the input data set.
With this way the learned label given according it's enviroment.

#### K - Nearest Neighbors:

</p>
<p align="center">
	<img src="/C096411/image/less7/Capture1.gif" align="middle">
</p>

It is possible the point will be close to point with diffrent classify from the rest enviroment.
The algorithm determains the classify according the k closest points from the input data set.
In case where the given point close to poiint with diffrent classifications, it will return the average of the classifications.
(Thats why preferable to use with odd number as k)

