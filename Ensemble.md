---
layout: page
mathjax: true
permalink: /ENSEMBLE/
---

### To Tutorial Page:

<a href="https://talbl.github.io/C096411/HTENS">
Tutorial Ensemble
</a>

- [Boosting](#Boosting)
- [Ada Boost](#Adaboost)

<hr />

### Lecture

<hr />

## Ensemble

<p align="center">
	<img src="/C096411/image/less6/council-table.jpg" align="middle">
</p>

Until now we learned methods that use single function and try to make it more approximate to the one given data set.

Ensemble learning is to pick a set of learning methods (could be the same method or not) and combine their predictions to a single prediction.

With this combination we can achieve a greater diversity approaches due to the use of different learning methods. Furthermore, each prediction which is received is more established than if we use in only one classifier.

<a name='boosting'></a>

<hr />

### Boosting:

In this method each classifier from the ensemble train on diffrent kind from the given data set.

##### For example:

Lets imagine we want to classify a classifier which body part of the face is show in the given picture.

We diverse classifiers in the ensemble: one will train on only forehead pictures, one on only ears pictures, one on only eyes pictures, one only on nose pictures and ect.

dismistration for the resulted classifiers in this ensemble: 

<p align="center">
	<img src="/C096411/image/less6/Capture.JPG" align="middle">
</p>

You can see in each filter there is a diffrent weight to pixel in given picture appropriate for his train.
Now lets say we get picture with those values:

<p align="center">
	<img src="/C096411/image/less6/Capture2.JPG" align="middle">
</p>

In the trained ensemble the filter which present the forehead will bring the highest accuracy, so we will understand that the given picture is picture of forehead.

##### Assumption:

The filters right only on 60% pictures.

##### Weak Learners:

There set of weak learners marked as WL(D,S) where:

D - Distibution in size D1,D2,...Dm

S - Train set S={(X1,y1),...,(Xm,ym)}

So for each Di exist h belongs to WL(D,S) that maintain:

<p align="center">
	<img src="/C096411/image/less6/Capture3.jpg" align="middle">
</p>

In our assumption we get that gamme = 0.1.

For example:

<p align="center">
	<img src="/C096411/image/less6/Capture4.jpg" align="middle">
</p>

We get:

<p align="center">
	<img src="/C096411/image/less6/Capture5.jpg" align="middle">
</p>

<a name='Adaboost'></a>

<hr />


### Ada Boost Algorithm:

The algorithm train his classifiers in way that in iteration t the classifier put more empasize where he got wrong in the previous iteration.
We calculate weight to each wrong we got so we need to work harder for make her right in the next iteration.

#### Input:

<p align="center">
	<img src="/C096411/image/less6/Capture6.svg" align="left">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture7.svg" align="left">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture8.svg" align="left">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture9.svg" align="left">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture10.svg" align="left">
</p>

#### Output:
<p align="center">
	<img src="/C096411/image/less6/Capture11.svg" align="left">
</p>

###### When the sign alpha:
<p align="center">
	<img src="/C096411/image/less6/Capture12.svg" align="middle">
</p>
means that:
1. <p align="center">
	<img src="/C096411/image/less6/Capture13.svg" align="left">
</p>
2. <p align="center">
	<img src="/C096411/image/less6/Capture14.svg" align="left">
</p>

You can see that:
<p align="center">
	<img src="/C096411/image/less6/Capture15.svg" align="left">
</p>

#### Example for iteration:

<p align="center">
	<img src="/C096411/image/less6/Capture16.svg" align="left">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture17.svg" align="left">
</p>

lets assume that:
<p align="center">
	<img src="/C096411/image/less6/Capture18.svg" align="left">
</p>

so we get:
<p align="left">
	<img src="/C096411/image/less6/Capture19.svg" align="left">
</p>

If the classifier's right:
<p align="center">
	<img src="/C096411/image/less6/Capture20.svg" align="left">
</p>

If the classifier's wrong:
<p align="center">
	<img src="/C096411/image/less6/Capture21.svg" align="left">
</p>

And in the end of iteration we get:
<p align="center">
	<img src="/C096411/image/less6/Capture22.svg" align="left">
</p>

Where 1/e is where h(x) is right and e is where h(x) is wrong.

#### Ada boost loss function sentence:

For given data set S and AdaBoost that keeps the WL condition:
<p align="center">
	<img src="/C096411/image/less6/Capture23.svg" align="left">
</p>
so the loss function of h is:
<p align="center">
	<img src="/C096411/image/less6/Capture24.svg" align="left">
</p>

##### Proof:

What we need to prove is:
<p align="center">
	<img src="/C096411/image/less6/Capture25.svg" align="middle">
</p>

Holds that:
<p align="center">
	<img src="/C096411/image/less6/Capture26.svg" align="middle">
</p>
beacuase in the graph:
<p align="center">
	<img src="/C096411/image/less6/Capture27.svg" align="middle">
</p>

That mean the inequality exist.

Now left to see:
<p align="center">
	<img src="/C096411/image/less6/Capture28.svg" align="middle">
</p>

For start we prove: Zo=1:
<p align="center">
	<img src="/C096411/image/less6/Capture29.svg" align="middle">
</p>
 and beacuase that:

<p align="center">
	<img src="/C096411/image/less6/Capture30.svg" align="middle">
</p>
(beacuase of the Conclusion)


##### Lemma 1:
When:
<p align="center">
	<img src="/C096411/image/less6/Capture31.svg" align="middle">
</p>
and 
<p align="center">
	<img src="/C096411/image/less6/Capture32.svg" align="middle">
</p>

so:
<p align="center">
	<img src="/C096411/image/less6/Capture33.svg" align="middle">
</p>
and
<p align="center">
	<img src="/C096411/image/less6/Capture34.svg" align="middle">
</p>

###### Proof:

The base case:
<p align="center">
	<img src="/C096411/image/less6/Capture35.svg" align="middle">
</p>

Induction assumption:
<p align="center">
	<img src="/C096411/image/less6/Capture36.svg" align="middle">
</p>

Inductive step:
<p align="center">
	<img src="/C096411/image/less6/Capture37.svg" align="middle">
</p>
<p align="center">
	<img src="/C096411/image/less6/Capture38.svg" align="middle">
</p>

##### Lemma 2:

When 
<p align="center">
	<img src="/C096411/image/less6/Capture39.svg" align="middle">
</p>
so:
<p align="center">
	<img src="/C096411/image/less6/Capture40.svg" align="middle">
</p>

###### Proof:

beacuase the definition
<p align="center">
	<img src="/C096411/image/less6/Capture41.svg" align="middle">
</p>

by the addition rule of fractions:
<p align="center">
	<img src="/C096411/image/less6/Capture42.svg" align="middle">
</p>

by definition of Ft+1(x):
<p align="center">
	<img src="/C096411/image/less6/Capture43.svg" align="middle">
</p>

according to lemma 1:
<p align="center">
	<img src="/C096411/image/less6/Capture44.svg" align="middle">
</p>

We will mark:
<p align="center">
	<img src="/C096411/image/less6/Capture45.svg" align="middle">
</p>
and saperate to places where <p align="center">
	<img src="/C096411/image/less6/Capture46.svg" align="middle">
</p>
and <p align="center">
	<img src="/C096411/image/less6/Capture47.svg" align="middle">
</p>

Now we get:
<p align="center">
	<img src="/C096411/image/less6/Capture48.svg" align="middle">
</p>

beacuase
<p align="center">
	<img src="/C096411/image/less6/Capture48a.svg" align="middle">
</p>
and
<p align="center">
	<img src="/C096411/image/less6/Capture48b.svg" align="middle">
</p>

we get next:

<p align="center">
	<img src="/C096411/image/less6/Capture49.svg" align="middle">
</p>

<p align="center">
	<img src="/C096411/image/less6/Capture50.svg" align="middle">
</p>


#### Conclusion:

If 
<p align="center">
	<img src="/C096411/image/less6/Capture51.svg" align="middle">
</p>

then:
<p align="center">
	<img src="/C096411/image/less6/Capture52.svg" align="middle">
</p>


##### Proof:

In the definition:
<p align="center">
	<img src="/C096411/image/less6/Capture53.svg" align="middle">
</p>

It brings:
<p align="center">
	<img src="/C096411/image/less6/Capture54.svg" align="middle">
</p>

And with the fact:
<p align="center">
	<img src="/C096411/image/less6/Capture55.svg" align="middle">
</p>

Toghether they bring our conclusion.


#### For more information:



