---
layout: page
mathjax: true
permalink: /ENSEMBLE/
---

<hr />

### To Tutorial Page:
  <div class="materials-item">
      <a href="https://talbl.github.io/C096411/HTENS">
        Tutorial Ensemble
      </a>
    </div>

<hr />

- [Boosting](#Boosting)
- [Ada Boost](#Adaboost)

<hr />

### Lecture

<hr />

## Ensemble

<p align="center">
	<img src="/C096411/image/less6/council-table.jpg" align="middle">
</p>

Until now we learned methods that use single function and try to make it more approximate to the given data set.

Ensemble learning is to pick a set of learning methods (could be the same method or not) and combine their predictions to a single prediction.

With this combination we can achieve a greater diversity approaches due to the use of different learning methods. Furthermore, each prediction which is received is more established than using in only one classifier.

<a name='boosting'></a>

<hr />

### Boosting:

In this method each classifier from the ensemble trains on a diffrent classification from the given data set.

##### For example:

Lets suppose we want to create a classifier which body part of the face is shown in the given picture.

We specify classifiers in the ensemble: one will train on only forehead pictures, one on only ears pictures, one on only eyes pictures, one only on nose pictures etc.

Demonstration for the resulted classifiers in this ensemble: 

<p align="center">
	<img src="/C096411/image/less6/Capture.JPG" align="middle">
</p>

You can see in each filter there are diffrent weights to different areas of the picture, appropriate to his training speification.

Now lets say we get a picture with the following values:

<p align="center">
	<img src="/C096411/image/less6/Capture2.JPG" align="middle">
</p>

In the trained ensemble the filter which presents the forehead will bring the highest accuracy, so we understand that the given picture is a picture of a forehead.

#### Assumption:

Each filter is correct only on 60% of the pictures.

#### Weak Learners:

There is a set of weak learners marked as WL(D,S) where:

D - Distibution in size D1,D2,...Dm

S - Train set S={(X1,y1),...,(Xm,ym)}

So for each Di exists an h that belongs to WL(D,S) that holds:

<p align="center">
	<img src="/C096411/image/less6/Capture3.svg" align="middle">
</p>

In our assumption we get that gamma = 0.1.

For example:

<p align="center">
	<img src="/C096411/image/less6/Capture4.svg" align="middle">
</p>

We get:

<p align="center">
	<img src="/C096411/image/less6/Capture5.svg" align="middle">
</p>

<a name='Adaboost'></a>

<hr />


### Ada Boost Algorithm:

The algorithm trains its classifiers in a way that in iteration t the classifier puts more emphasis where he got wrong in the previous iteration.
The higher the iteration, the wieght for each error is increased. For this reason, it will "work harder" to increase its accuracy. 


<p align="center">
	<img src="/C096411/image/less6/Capture6.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture7.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture8.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture9.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture10.svg" align="middle">
</p>


<p align="center">
	<img src="/C096411/image/less6/Capture11.svg" align="middle">
</p>

#### The definition of alpha in: <img src="/C096411/image/less6/Capture12.svg" align="middle" width="145.452pt" height="14.3337pt"/>

means that:

(1) <img src="/C096411/image/less6/Capture13.svg" align="middle" width="227.80761465pt" height="24.65753399999998pt"/>

(2) <img src="/C096411/image/less6/Capture14.svg" align="middle" width="60.8717pt" height="36.3856pt"/>

Therefor it results to: <img src="/C096411/image/less6/Capture15.svg" align="middle" width="143.796pt" height="31.0197pt"/>

#### Iteration example:

<img src="/C096411/image/less6/Capture16.svg" align="middle" width="97.3075pt" height="15.672pt"/>

<img src="/C096411/image/less6/Capture17.svg" align="middle" width="236.445pt" height="17.0963pt"/>

Assumption:   <img src="/C096411/image/less6/Capture44.svg" align="middle" width="39.1119pt" height="10.6999pt"/>

After assignment:   <img src="/C096411/image/less6/Capture45.svg" align="middle" width="222.762pt" height="16.9771pt"/>

If the classifier is right:  <img src="/C096411/image/less6/Capture18.svg" align="middle" width="227.80761465pt" height="13.4589pt"/>

If the classifier is wrong:  <img src="/C096411/image/less6/Capture19.svg" align="middle" width="227.80761465pt" height="13.4589pt"/>

At the end of the iteration:  <img src="/C096411/image/less6/Capture20.svg" align="middle" width="94.3731pt" height="27.0794pt"/>

Where 1/e is where h(x) is right and e is where h(x) is wrong.

#### Ada boost loss function sentence:

For a given data set S and an AdaBoost algorithm that keeps the WL condition:  <img src="/C096411/image/less6/Capture21.svg" align="middle" width="155.506pt" height="32.3016pt"/>

then the loss function of h is:  <img src="/C096411/image/less6/Capture22.svg" align="middle" width="210.863pt" height="36.3856pt"/>

#### Proof:

What we need to prove is: <img src="/C096411/image/less6/Capture30.svg" align="middle" width="201.897pt" height="36.3856pt"/>

In the following graph:
<p align="center">
	<img src="/C096411/image/less6/Capture3.JPG" align="middle">
</p>

Each point in the graph holds that:
<p align="center">
	<img src="/C096411/image/less6/Capture31.svg" align="middle">
</p>

Therefor it holds also for their average.

That means the inequality exist.

<b> Now left to prove: </b>
<p align="center">
	<img src="/C096411/image/less6/Capture32.svg" align="middle">
</p>

Becuase of the structure of the series:   <img src="/C096411/image/less6/Capture32_1.svg" align="middle" width="154.477pt" height="30.5639pt"/>

Firstly we prove:   <img src="/C096411/image/less6/Capture33.svg" align="middle" width="38.7116pt" height="11.2233pt"/>

<p align="center">
	<img src="/C096411/image/less6/Capture34.svg" align="middle">
</p>

from here:

<p align="center">
	<img src="/C096411/image/less6/Capture35.svg" align="middle">
</p>
(becuase of the conclusion)


#### Lemma 1:

When: <img src="/C096411/image/less6/Capture23.svg" align="middle" width="53.9259pt" height="13.4589pt"/> and <img src="/C096411/image/less6/Capture24.svg" align="middle" width="113.277pt" height="39.6861pt"/>

then: <img src="/C096411/image/less6/Capture25.svg" align="middle" width="97.3169pt" height="12.3073pt"/>

#### Proof:

<b> The base case: </b> <img src="/C096411/image/less6/Capture46.svg" align="middle" width="219.273pt" height="32.3016pt"/>

<b> Induction assumption: </b> <img src="/C096411/image/less6/Capture47.svg" align="middle" width="101.722pt" height="14.3337pt"/>

<b> Inductive step: </b>

<img src="/C096411/image/less6/Capture48.svg" align="middle" width="285.762pt" height="14.3337pt"/>

<img src="/C096411/image/less6/Capture49.svg" align="middle" width="187.351pt" height="12.3073pt"/>

#### Lemma 2:

When: <img src="/C096411/image/less6/Capture26.svg" align="middle" width="113.428pt" height="36.3856pt"/>

then: <img src="/C096411/image/less6/Capture27.svg" align="middle" width="220.635pt" height="29.6292pt"/>

#### Proof:

Becuase of the definition and addition rule of fractions:

<p align="center">
	<img src="/C096411/image/less6/Capture36.svg" align="middle">
</p>

by definition of Ft+1(x) and according to lemma 1:
<p align="center">
	<img src="/C096411/image/less6/Capture37.svg" align="middle">
</p>

* Marking: <img src="/C096411/image/less6/Capture38.svg" align="middle" width="188.999pt" height="36.3856pt"/> 

we split the sum where <img src="/C096411/image/less6/Capture39.svg" align="middle" width="183.428pt" height="13.4589pt"/>

This results to:
<p align="center">
	<img src="/C096411/image/less6/Capture40.svg" align="middle">
</p>

following:

<p align="center">
	<img src="/C096411/image/less6/Capture41.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture41_1.svg" align="middle">
</p>


#### Conclusion:

If <img src="/C096411/image/less6/Capture28.svg" align="middle" width="116.311pt" height="29.1058pt"/>

then <img src="/C096411/image/less6/Capture29.svg" align="middle" width="72.4675pt" height="29.6292pt"/>

#### Proof:

In the definition: <img src="/C096411/image/less6/Capture50.svg" align="middle" width="228.396pt" height="21.7313pt"/>

It brings: <img src="/C096411/image/less6/Capture51.svg" align="middle" width="285.624pt" height="16.1528pt"/>

And with the fact that: <img src="/C096411/image/less6/Capture43.svg" align="middle" width="73.7416pt" height="27.0794pt"/>

Together it proves our conclusion.
