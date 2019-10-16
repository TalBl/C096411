---
layout: page
mathjax: true
permalink: /DT/
---

<hr />

### To Tutorial Page:
  <div class="materials-item">
      <a href="https://talbl.github.io/C096411/HTDT">
        Tutorial Desicion Trees
      </a>
    </div>

<hr />

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

In this classifier the classification is determined based on the result of a process similar to the one below:
<p align="center">
	<img src="/C096411/image/less7/Capture2.gif" align="middle">
</p>

The tree creation is a black box in this course, the tree is built according to the building algorithm.

There are diffrent possible trees for the same problem.

#### Classification Tree

The possible classifications are 'Yes' or 'No'.
A leaf in this kind of tree holds examples with the same label.

For example:
<p align="center">
	<img src="/C096411/image/less7/Capture2.gif" align="middle">
</p>

#### Regression Tree

The classification is a rational number.
A leaf in this kind of tree holds examples with the diffrent labels.
The Leaf's value is the average of it's examples's classifications.

For example:
<p align="center">
	<img src="/C096411/image/less7/Capture3.gif" align="middle">
</p>

#### Overfitting in Decision Trees

The tree creation can lead to a tree with full separation.
With the assumption that the training set may have several mistakes, or in another word, bias.
Full separation is when the tree is too accurate on the training set, which will lead to a tree with bias.
This is called overfitting, which can cuase bias in the test set.
To prevent overfitting, it is needed to know when to stop the tree creation before it is too accurate.


<a name='Bagging'></a>

<hr />

### Bagging:

This algorithm tries to solve the overfitting problem.

Definition:
Tb(X) - Random variable for a subset of the training set.

Instead of training one tree on the whole training set, the algorithm generates B new training sets (training set i is marked Di) according to the Tb variable.
The algorithm trains B trees, for each Di.
When classifying a new example, the algorithm classifies it on the B trees and returns the average of the given classifications.

The problem with using a random variable (Tb) is it's variance.
To minimize it, the algorithm uses B independent trees.

#### Definition of independence: <img src="/C096411/image/less7/8.svg" align="middle" width="87.3035pt" height="13.4589pt"/>

- Each tree is built from subset s from dataset S.

- Each pair of subsets hold: <img src="/C096411/image/less7/11.svg" align="middle" width="64.4434pt" height="13.8652pt"/>

#### Theorem: <img src="/C096411/image/less7/1.svg" align="middle" width="464.909pt" height="39.6042pt"/>

#### Proof:

Marking: <img src="/C096411/image/less7/2.svg" align="middle" width="71.6905pt" height="14.4388pt"/>

<p align="center">
	<img src="/C096411/image/less7/3.svg" align="middle">
</p>

According the variance definition:

<p align="center">
	<img src="/C096411/image/less7/3_1.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less7/4.svg" align="middle">
</p>

Separating where pairs of b are equals and where they are not:

<p align="center">
	<img src="/C096411/image/less7/5.svg" align="middle">
</p>


In the first bracket: the mean equals 0.

In the second bracket: the mean equals mu.

<p align="center">
	<img src="/C096411/image/less7/6.svg" align="middle">
</p>

#### Conclusion:
The Bagging algorithm minimizes the variance if the trees are independent.


<a name='RandomForest'></a>

<hr />

### Random Forest:
This algorithm gets as input dependent trees and builds a forest with smaller correlation between the trees.

For each b=1,2,...,B build tree Tb for subset Sb that belongs to S in the following steps:
	- Choose r random indexes (features) from 1,..,d
	- Choose a random split in the tree according the r chosen indexes
	- Create 2 vertexes according the split
	
That way it creates B trees which consists the forest we want.
(The random choices in the algorithm is what reduces the correlation)

#### Theorem:
If the trees are dependent:

Marking the correlation between the trees: <img src="/C096411/image/less7/12.svg" align="middle" width="194.083pt" height="14.7249pt"/>

The variance equals to:

<p align="center">
	<img src="/C096411/image/less7/13.svg" align="middle">
</p>

Becuase of that, when the trees are dependent, it is better to use the Random Forest algorithm.

#### Proof:

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

<p align="center">
	<img src="/C096411/image/less7/Capture.gif" align="middle">
</p>

The input is a data set of points with labels and an unclassified point.
The algorithm determines the classification according the closest point from the input data set.
This way the label is determined according to it's environment.

#### K - Nearest Neighbors:

<p align="center">
	<img src="/C096411/image/less7/Capture1.gif" align="middle">
</p>

It is possible that the point will be close to a single point with a diffrent classification than rest of it's close environment.
The algorithm determines the classification according to the K closest points from the input data set.
In case where the given point is close to points with diffrent classifications, it will return the average of the classifications.
(Thats why it is preferable to define K as an odd number)

