---
layout: page
permalink: /EM/
---

- [Introduction](#Introduction)
- [Measurement of Discrete Group](#disgroup)
- [Measurement of Continuous Group](#congroup)
- [Measurement of Discrete Group and Continuous Group](#disandcongroup)
- [Measurement of Discrete Group and Continuous Group Without Discrete Information](#nodisgroup)
- [Clustering](#clustering)
- [K-means](#kmeans)
- [Mixture of Gaussian](#gmm)
- [Expectation Maximization](#EM)


## Unsupervised Learning:

<a name='Introduction'></a>

<hr />

### Introduction:

This learning method finds previously unknown patterns in a given data set wihtout pre-existing labels.

Besides the standard goal of a learning problem (classification), this method needs to learn the characteristics and structure of the data. 

### Examples for diffrences between the supervised and unsupervised:

<a name='disgroup'></a>

<hr />

#### (1) Measurement of Discrete Group - Measurement of Coin's Distrubution:

Input: the results of m random coin tosses.
The results of the tosses are known - that's why it is supervised.

**Marking:**

Result of one toss:
<p align="center">
	<img src="/C096411/image/less8/36.svg" align="middle">
</p>

The probability to get Head in a toss:
<p align="center">
	<img src="/C096411/image/less8/37.svg" align="middle">
</p>

Number of Head or Tail out of the m tosses:
<p align="center">
	<img src="/C096411/image/less8/41.svg" align="middle">
</p>

**Goal: Find the q that describes the coin's distribution the best**

<p align="center">
	<img src="/C096411/image/less8/39.svg" align="middle">
</p>

According Maximum Likelihood Estimation:

<p align="center">
	<img src="/C096411/image/less8/108.svg" align="middle">
</p>

With the assumption that the m tosses are independent:
<p align="center">
	<img src="/C096411/image/less8/109.svg" align="middle">
</p>

Calculating the maximum of products is a hard task, instead it is popular to use **Maximum Log-Likelihood Estimation**:
	Logarithm is monotonically increasing so the value which maximizes the log-likelihood, will also maximize the original likelihood.
	
<p align="center">
	<img src="/C096411/image/less8/110.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/111.svg" align="middle">
</p>

After finding the derivative:

<p align="center">
	<img src="/C096411/image/less8/112.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/113.svg" align="middle">
</p>

The optimal q is:

<p align="center">
	<img src="/C096411/image/less8/114.svg" align="middle">
</p>

**Inclusion to General Discrete Variables:**

Marking:

<p align="center">
	<img src="/C096411/image/less8/115.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/116.svg" align="middle">
</p>

With the same calculations as in the case of 2 labels (Head and Tail) , the solution is:

<p align="center">
	<img src="/C096411/image/less8/117.svg" align="middle">
</p>

<a name='congroup'></a>

<hr />

#### (2) Measurement of Continuous Group - Measurement Average of Class' Height:

The input is results of m random students' heights.

<p align="center">
	<img src="/C096411/image/less8/45.svg" align="middle">
</p>

The heights are known - that's why it is supervised.

**Assumption:**
The heights of the students in class are normally distributed with:
- Mean: <img src="/C096411/image/less8/46.svg" align="middle" width="7.92882pt" height="8.41179pt"/>
- Variance = 1

**Goal: Find the mu that describes the distribution's mean the best**

Normal Distrubution with variance = 1:

<p align="center">
	<img src="/C096411/image/less8/47.svg" align="middle">
</p>

The goal is: <img src="/C096411/image/less8/48.svg" align="middle" width="116.711pt" height="36.3856pt"/>

Similar calculations as in last example:

According Maximum Log-Likelihood Estimation:

<p align="center">
	<img src="/C096411/image/less8/49.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/50.svg" align="middle">
</p>

Calculate the derivative. The solution is:

<p align="center">
	<img src="/C096411/image/less8/51.svg" align="middle">
</p>

<a name='disandcongroup'></a>

<hr />

#### (3) Measurement of Discrete Group and Continuous Group - Measurement Average of Class' Height by their Gender:

The data set is composed from:
- Xi parameter - the height of student i (continuous parameter)
- Zi parameter - the gender of student i (discrete parameter)

Now the classifier needs to learn the parameters for 2 diffrent normal distributions and the probability between the genders.
- Becuase in the input data set, the persons' gender is known - this is also a supervised learning.

An example of a data set:
<p align="center">
	<img src="/C096411/image/less8/desmos-graph.png" align="middle">
</p>

Formally, the classifier needs to learn the following probability:

<p align="center">
	<img src="/C096411/image/less8/54.svg" align="middle">
</p>

According Bayes rule:

<p align="center">
	<img src="/C096411/image/less8/118.svg" align="middle">
</p>

**Find the estimation of the parameters:** <img src="/C096411/image/less8/119.svg" align="middle" width="112.729pt" height="11.9634pt"/>

Also here we use the Maximum Log-Likelihood Estimation:

<p align="center">
	<img src="/C096411/image/less8/120.svg" align="middle">
</p>

When <img src="/C096411/image/less8/121.svg" align="middle" width="32.936pt" height="11.8139pt"/> are already known from the input data set.

In example 1 we calculated:
(inclusion case)

<p align="center">
	<img src="/C096411/image/less8/122.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/123.svg" align="middle">
</p>

In example 2 we found:

<p align="center">
	<img src="/C096411/image/less8/124.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/125.svg" align="middle">
</p>

<a name='nodisgroup'></a>

<hr />

#### (4) Measurement of Discrete Group and Continuous Group Without Discrete Information - Measurement Average of Class' Heights:

The data set is composed of only the Xi parameter - the height of student i (continuous parameter)
<p align="center">
	<img src="/C096411/image/less8/64.svg" align="middle">
</p>

Now the classifier doesn't know that there are 2 diffrent groups in the data set which represent 2 diffrent normal distributions.
The classifier needs, not only to calculate the probability for a given height, but also to calculate the discrete distribution.

Becuase the discrete distribution doesn't given - this is unsupervised learning.

According to law of total probability:
<p align="center">
	<img src="/C096411/image/less8/126.svg" align="middle">
</p>

With assumption of normal distribution:

<p align="center">
	<img src="/C096411/image/less8/127.svg" align="middle">
</p>

Now as in previous examples, we want to use Maximum Likelihood Estimation:

<p align="center">
	<img src="/C096411/image/less8/128.svg" align="middle">
</p>

The problem: parameter Zi is not known, that means the input data set lacks information.
So this method cannot be used in this case.

<a name='clustering'></a>

<hr />

## Clustering:

The described problem above is solved with Clustering algorithms.
Those kinds of algorithms target: grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar to each other than to those in other groups (clusters).

Like in the last example - separating between the students according to their gender.

This issue differs in to 2 types:

- Hard Clustering: each object can belong to only 1 cluster.
	Example: K - Means.
	
- Soft Clustering: each object can belong to several clusters, there are diffrent kind of certain degrees.
	Example: Estimation Maximization and Mixture of Gaussian.

<a name='kmeans'></a>

<hr />

## K-means

The algorithm's goal is to separate the objects to K clusters.
Each object belongs to the cluster with the nearest mean.

The algorithm consists 2 steps:
- E step: 
	For each cluster: calculate the mean of the objects that belong to this cluster.
	
- M step:
	For each object find the nearest mean's cluster and assign it to it.
	
Those steps keep running until convergence.

In the end of the algorithm each object has only one cluster.
That's why this algorithm is **hard clustering**.

* K is a parameter for the algorithm.

<a name='gmm'></a>

<hr />

## Mixture of Gaussian:

The algorithm assumes that there are K gaussian distributions in the data set.
It calculates the probability for a given X according Bayes rule:

<p align="center">
	<img src="/C096411/image/less8/54.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/57.svg" align="middle">
</p>

Where:
- P(Z) is discrete distribution - which cluster does X belong?
- P(X|Z) is gaussian distribution - in the Z cluster, what is the probability of X?

Where the parameters are:

<p align="center">
	<img src="/C096411/image/less8/58.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/59.svg" align="middle">
</p>

When the data set is <img src="/C096411/image/less8/64.svg" align="middle" width="63.944pt" height="13.4589pt"/> of unsupervised kind, the algorithm needs to calculate:

<p align="center">
	<img src="/C096411/image/less8/65.svg" align="middle">
</p>

<a name='em'></a>

<hr />

## Expectation Maximization

The algorithm works iteratively to find Maximum Likelihood Estimations of distributions parameters.

The iteration depends on 2 steps:

**E step:** creates a function for the expectation of the log likelihood estimations using the current
	      estimations of the parameters.
		  
<p align="center">
	<img src="/C096411/image/less8/66.svg" align="middle">
</p>

In formal writing:

<p align="center">
	<img src="/C096411/image/less8/88.svg" align="middle">
</p>

**M step:** computes parameters maximizing the expected log-likelihood found from the E step.

<p align="center">
	<img src="/C096411/image/less8/67.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/68.svg" align="middle">
</p>

In formal writing:

<p align="center">
	<img src="/C096411/image/less8/89.svg" align="middle">
</p>

### Structure of the algorithm:

- for t=1,2,...
	- for i=1,2,...,m and j=1,2,...,m: (E step) 
		- <img src="/C096411/image/less8/129.svg" align="middle" width="124.1pt" height="13.8652pt"/> 
	- for j=1,2,...,m: (M step)
		- <img src="/C096411/image/less8/130.svg" align="middle" width="85.8337pt" height="36.3856pt"/>
		- <img src="/C096411/image/less8/131.svg" align="middle" width="106.767pt" height="32.8462pt"/>

### How to calculate the E step?

<p align="center">
	<img src="/C096411/image/less8/69.svg" align="middle">
</p>

(According Conditional Probability and Law of Total Probability)

### Theorem:

<p align="center">
	<img src="/C096411/image/less8/98.svg" align="middle">
</p>
For each distribution 0 <= q(z|x)

And there is equality when <img src="/C096411/image/less8/99.svg" align="middle" width="110.887pt" height="13.4589pt"/>

Why there is euquality in this case:
<p align="center">
	<img src="/C096411/image/less8/105.svg" align="middle">
</p>

#### For example in example 4:
<p align="center">
	<img src="/C096411/image/less8/100.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/101.svg" align="middle">
</p>

The purpose of the theorem is to prove the EM algorithm converges and it maximizes <img src="/C096411/image/less8/102.svg" align="middle" width="76.2158pt" height="36.3856pt"/>

### Why EM algorithm maximizes <img src="/C096411/image/less8/87.svg" align="middle" width="187.681pt" height="38.9537pt"/> ?

The proof is based on Jensen inequality:

<p align="center">
	<img src="/C096411/image/less8/104.svg" align="middle">
</p>

and in our case:

<p align="center">
	<img src="/C096411/image/less8/103.svg" align="middle">
</p>

EM algorithm maximizes the function:

<p align="center">
	<img src="/C096411/image/less8/87.svg" align="middle">
</p>

instead of:

<p align="center">
	<img src="/C096411/image/less8/106.svg" align="middle">
</p>

The theorem shows:

<p align="center">
	<img src="/C096411/image/less8/107.svg" align="middle">
</p>

So if the algorithm maximizes the right side of the equation then the left side will be maximized.

Where the optimal q holds <img src="/C096411/image/less8/86.svg" align="middle" width="110.887pt" height="13.4589pt"/>
When the algorithm reaches this q, the iterations stop.

#### Why E step?

<p align="center">
	<img src="/C096411/image/less8/90.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/91.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/92.svg" align="middle">
</p>

#### Why M step?

<p align="center">
	<img src="/C096411/image/less8/93.svg" align="middle">
</p>

The Wij is constant which doesn't influence the argmax

<p align="center">
	<img src="/C096411/image/less8/94.svg" align="middle">
</p>

Assuming normal distribution

<p align="center">
	<img src="/C096411/image/less8/95.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/96.svg" align="middle">
</p>

The second sum doesn't influence the argmax

<p align="center">
	<img src="/C096411/image/less8/132.svg" align="middle">
</p>

#### Marking: <img src="/C096411/image/less8/133.svg" align="middle" width="119.177pt" height="36.3856pt"/>

- E step creates aux function which is "stuck" to l(theta) in theta(t) point.

- M step finds the maximum of <img src="/C096411/image/less8/134.svg" align="middle" width="46.0349pt" height="16.2761pt"/>

As is seen in the graph:

<p align="center">
	<img src="/C096411/image/less8/Capture1.JPG" align="middle">
</p>

Thats why we want to maximize the bottom bound.


