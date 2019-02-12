---
layout: page
mathjax: true
permalink: /Logistic/
---

### To Tutorial Page:


<a href="https://orensp.github.io/C096411/HTlogistic_re/">
Tutorial Logistic Regression
</a>


### Lecture

<hr />
	
- [Classes_probability](#c1)
- [optimal W](#c1)


<hr />

## Logistic regression:

The Perceptron rule <w,x> gave us distance which is between $[-\infty,\infty]$ when $\infty$ is far in the positive side and 
$-\infty$ is in the far in the negetive side. if we think about it the bigger the distance the more likely that
the classification is right when 0 is 50% to each side.

Insted of working in distances space we want to talk about chances or probability to be a part of a class given some x , p(y|x).
to do so we need to change our space from $[-\infty,\infty]$ to [0,1]. A very usefull function to do so is the sigmoid function:

<p align="center">
	<img src="/C096411/image/less3/Capture1.PNG" align="middle">
</p>

The function in $\infty $ is 1(heigh probability) and 0(low probability) in $-\infty $

#### Classes probability:

$$ P(y_i=1|X)=\frac {1}{1+e^{-<\hat{\omega},x_i>}} $$

$$ P(y_i=-1|x_i)=1-P(Y=1|x_i)=\frac {1}{1+e^{<\hat{\omega},x_i>}} $$

So we can say in general that:

$$ P(y_i|x_i)=\frac {1}{1+e^{-y_i<\hat{\omega},x_i>}} $$



#### Finding the optimal $\omega$:

We can use maximum likelihood estimation method to find $\omega$ that will maximize the probability:

$$ P(y_1,y_2...y_m|x_1,x_2...x_,)=\prod\limits_{i=1}^{m} \frac {1}{1+e^{-y_i<\hat{\omega},x_i>}} $$

because log is monotonic increasing function we can maximize log(P(y_1,y_2...y_m|x_1,x_2...x_,))

$$maximize \, \sum\limits_{i=1}^{m} log(\frac {1}{1+e^{-y_i<\hat{\omega},x_i>}}) $$

This is same as:

$$ 
minimize \, \sum\limits_{i=1}^{m} log(1+e^{-y_i<\hat{\omega},x_i>})  
$$

This equation is called log-loss loss function. while we already saw the mean square root loss: 

$$minimize \, \sum\limits_{i=1}^{m} ({y_i-<\hat{\omega},x_i>})^2  $$

This loss gives use the probability result between [0,1]

