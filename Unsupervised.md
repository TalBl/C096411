---
layout: page
permalink: /EM1/
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


## Unsupervided Learning:

<a name='Introduction'></a>

<hr />

### Introduction:

This kind of learning: in the input data set not given labels with it.

The goal is to learn also the labels or the distributions: one or more possible.

### Examples for diffrence between the supevised and unsupervised:

<a name='disgroup'></a>

<hr />

#### (1) Measurement of Discrete Group - Measurement of Coin's Distrubution:

Input: the results of m random coin's throwings.
The results of the throwings are known - That's why it is supervised.

##### Marking:

Result of one throwing:
<p align="center">
	<img src="/C096411/image/less8/36.svg" align="middle">
</p>

The probability to get Head in throwing:
<p align="center">
	<img src="/C096411/image/less8/37.svg" align="middle">
</p>

Numbers of head or Tale as result from the m:
<p align="center">
	<img src="/C096411/image/less8/41.svg" align="middle">
</p>

##### Aim: Find the propreate q that describe the coin's distribution the best

<p align="center">
	<img src="/C096411/image/less8/39.svg" align="middle">
</p>

According maximum likelihood estimation:

<p align="center">
	<img src="/C096411/image/less8/108.svg" align="middle">
</p>

With the assumption the m throwings are independence:
<p align="center">
	<img src="/C096411/image/less8/109.svg" align="middle">
</p>

Calculate maximum of products is hard task, instead it is popular to use with Maximum log-likelihood estimation:
	Logarithm is monotonically increasing so the value which max the log-likelihood, will max also the original likelihood.
	
<p align="center">
	<img src="/C096411/image/less8/110.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/111.svg" align="middle">
</p>

Need to search derivative:

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

##### Inclusion to General Discrete Varibles:

Marking:

<p align="center">
	<img src="/C096411/image/less8/115.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/116.svg" align="middle">
</p>

With the same calculations as in 2 classes case , the solution is:

<p align="center">
	<img src="/C096411/image/less8/117.svg" align="middle">
</p>

<a name='congroup'></a>

<hr />

#### (2) Measurement of Continuous Group - Measurement Average of Class' Height:

Input is results of m random students' height.

<p align="center">
	<img src="/C096411/image/less8/45.svg" align="middle">
</p>

The heights are known - That's why it is supervised.

##### Assumption:
The height of the children in class are from Normal distribution with:
- Mean: <p align="center">
	<img src="/C096411/image/less8/46.svg" align="middle">
</p>
- Variance = 1

##### Aim: Find the miu that describe the mean's distribution the best

The Normal Distrubution with variance = 1:

<p align="center">
	<img src="/C096411/image/less8/47.svg" align="middle">
</p>

The target is:

<p align="center">
	<img src="/C096411/image/less8/48.svg" align="middle">
</p>

As like the calculations from last example:

According maximum log - likelihood estimation:

<p align="center">
	<img src="/C096411/image/less8/49.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/50.svg" align="middle">
</p>

Need to search derivative, and the solution is:

<p align="center">
	<img src="/C096411/image/less8/51.svg" align="middle">
</p>

<a name='disandcongroup'></a>

<hr />

#### (3) Measurement of Discrete Group and Continuous Group - Measurement Average of Class' Height by their Gender:

The data set composed of:
- Xi parameter- the height of student i (continuous parameter)
- Zi parameter- the gender of student i (discrete parameter)

The classifier needs now to learn 2 diffrent of normal distributions and the probability between the genders.
- Becuase in the input the classifier is given the persons' gender - this is also a supervised learning.

Example for data set:
<p align="center">
	<img src="/C096411/image/less8/desmos-graph.png" align="middle">
</p>

In formula, the classifier needs to learn the probability:

<p align="center">
	<img src="/C096411/image/less8/54.svg" align="middle">
</p>

According Bayes rule:

<p align="center">
	<img src="/C096411/image/less8/118.svg" align="middle">
</p>

##### Find the Estimation of Parameters:

<p align="center">
	<img src="/C096411/image/less8/119.svg" align="middle">
</p>

Also here we use the maximum log-likelihood estimation:

<p align="center">
	<img src="/C096411/image/less8/120.svg" align="middle">
</p>

When parameters <p align="center">
	<img src="/C096411/image/less8/121.svg" align="middle">
</p> allready known from the input data set.

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

#### (4) Measurement of Discrete Group and Continuous Group Without Discrete Information- Measurement Average of Class' Height:

The data set composed of only the Xi parameter- the height of student i (continuous parameter)
<p align="center">
	<img src="/C096411/image/less8/64.svg" align="middle">
</p>

Now the classifier doesn't know that there are 2 diffrent sub-group in the data set which present 2 diffrent normal distributions.
The classifier needs not only to calculate the probability for given height, it needs also tp calculate the discrete distribution.

Becuase the discrete distribution doesn't given - this is unsupervised learning.

According to law of total probability:
<p align="center">
	<img src="/C096411/image/less8/126.svg" align="middle">
</p>

With assumption of normal distribution:

<p align="center">
	<img src="/C096411/image/less8/127.svg" align="middle">
</p>

Now as previous examples, we want to use maximum likelihood estimation:

<p align="center">
	<img src="/C096411/image/less8/128.svg" align="middle">
</p>

The problem: parameter Zi is not known, that means the input data set is lack of information.
So the method is not possible.

<a name='clustering'></a>

<hr />

## Clustering:

The described problem above is solved with clustering algorithm.
Those kind algorithm's target: grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar to each other than to those in other groups (clusters).

Like in the example is given - find the gender split between the students.

This issue differ to 2 types:

- Hard Clustering: each object can belong to only 1 cluster.
	Example: K - Means.
	
- Soft Clustering: each object can belong to some clusters, there are diffrent kind of certain degrees.
	Example: Estimation Maximization and Mixture of Gaussian .

<a name='kmeans'></a>

<hr />

## K-means

The algorithm's target to separate the objects to k clusters.
Each object belong to cluster with the nearest mean.

The algorithm build from 2 steps:
- E step: 
	For each cluster: calculate the mean of the objects that belong to this cluster.
	
-M step:
	For each object find the nearest mean's cluster and belong it to it.
	
Those steps keep runnning until convergence.

In the end of the algorithm each object has only one cluster.
That's why this algorithm is hard clustering.

* k is parameter for the algorithm.

<a name='gmm'></a>

<hr />

## Mixture of Gaussian:

The algorithm's assume that there are k gaussian distributions in the data set.
It calculates the probability for given x according Bayes rule:

<p align="center">
	<img src="/C096411/image/less8/54.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/57.svg" align="middle">
</p>

Where:
- P(z) is discrete distribution - which cluster x belongs?
- P(x|z) is gaussian distribution - in the z cluster, what the probability get x?

Where the parameters are:

<p align="center">
	<img src="/C096411/image/less8/58.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/59.svg" align="middle">
</p>

When the data set is <p align="center">
	<img src="/C096411/image/less8/64.svg" align="middle">
</p> from unsupervised kind, the algorithm needs to search:

<p align="center">
	<img src="/C096411/image/less8/65.svg" align="middle">
</p>

<a name='em'></a>

<hr />

## Expectation Maximization

The algorithm works in iterative method to find maximum likelihood estimations of parameters.

The iteration depends on 2 steps:

- E step: which creates a function for the expectation of the log likelihood estimations using the current
	      estimate for the parameters.
		  
<p align="center">
	<img src="/C096411/image/less8/66.svg" align="middle">
</p>

In formal writing:

<p align="center">
	<img src="/C096411/image/less8/88.svg" align="middle">
</p>

- M step: which computes parameters maximizing the expected log-likelihood found on the E step.

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
	- for i=1,2,...,m and j=1,2,...,m
		- (E step) <p align="center">
	<img src="/C096411/image/less8/129.svg" align="middle">
</p>
	- for j=1,2,...,m: (M step)
		- <p align="center">
	<img src="/C096411/image/less8/130.svg" align="middle">
</p>
		- <p align="center">
	<img src="/C096411/image/less8/131.svg" align="middle">
</p>

### How to calculate the E step?

<p align="center">
	<img src="/C096411/image/less8/69.svg" align="middle">
</p>

(According the Conditional probability and Law of total probability)

### Sentence:

<p align="center">
	<img src="/C096411/image/less8/98.svg" align="middle">
</p>
For each distribution 0 <= q(z|x)

And there is equality where <p align="center">
	<img src="/C096411/image/less8/99.svg" align="middle">
</p>

Becuase:
<p align="center">
	<img src="/C096411/image/less8/105.svg" align="middle">
</p>

* For example in example 4:
<p align="center">
	<img src="/C096411/image/less8/100.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/101.svg" align="middle">
</p>

The purpose of the sentence is to prove algorithm EM converge and it maximizes <p align="center">
	<img src="/C096411/image/less8/102.svg" align="middle">
</p>

### Why algorithm EM maximize <p align="center">
	<img src="/C096411/image/less8/87.svg" align="middle">
</p> ?

The prove based on Jensen inequality:

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

instead:

<p align="center">
	<img src="/C096411/image/less8/106.svg" align="middle">
</p>

The sentence shows:

<p align="center">
	<img src="/C096411/image/less8/107.svg" align="middle">
</p>

Where the optimal q fullfill <p align="center">
	<img src="/C096411/image/less8/86.svg" align="middle">
</p>

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

The Wij is constant that doesnt influence on the argmax

<p align="center">
	<img src="/C096411/image/less8/94.svg" align="middle">
</p>

For assume normal distribution

<p align="center">
	<img src="/C096411/image/less8/95.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less8/96.svg" align="middle">
</p>

The second sum doesnt influence the argmax

<p align="center">
	<img src="/C096411/image/less8/132.svg" align="middle">
</p>

#### Marking:

<p align="center">
	<img src="/C096411/image/less8/133.svg" align="middle">
</p>

E step creates aux function which be stuck to l(theta) in theta(t)

M step finds the maximum of <p align="center">
	<img src="/C096411/image/less8/134.svg" align="middle">
</p>

As it seen in the graph:

<p align="center">
	<img src="/C096411/image/less8/Capture1.JPG" align="middle">
</p>

Thats why we want to maximize the buttom obstruction.


