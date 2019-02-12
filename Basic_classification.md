---
layout: page
mathjax: true
permalink: /classification/
---


- [Introduction:type of learning](#intro)
- [Linear regression-2D-Model](#LR_2D)
  - [2D-Model-Generalization](#LR_G)
- [Linear regression-nD-Model](#LR_nD)
- [Perceptron](#PR)
- [Logistic Regression](#LR)
- [SVM](#SVM)

<div class="fighighlight">
</div>

<a name='intro'></a>
## Quick Intro

This course is an introduction to machine learning basics theory and practice. There are 3 different types of learning:

### Supervised learning
supervised learning is maybe the most common modern way of teaching. In this method a "Teacher" shows you an example
and you are required to repeat the example logic on some other examples.


<p align="center">
	<img src="/C096411/image/less0/Capture.JPG" />
</p>


### Unsupervised learning:

Unsupervised learning is a way to make Decisions based on correlation in the data.


<p align="center">
	<img src="/C096411/image/less0/Image2.PNG" align="middle" >
</p>


### Reinforcement learning:

Reinforcement learning is based on interaction with the environment. The learning is done using Trial and error. 


<p align="center">
	<img src="/C096411/image/less0/Image3.PNG" align="middle">
</p>



<a name='LR'></a>

## Linear regression 


### 2D Basic Model:
<a name='LR_2D'></a>

<div class="fighighlight">
</div>	
	
#### Notations:

In linear regression we assume the connection between X and Y is linear:

$\hat{Y}_i=\omega_1 x_i+\omega_0 ~ $ trying to fit $ \omega_1,\omega_0$ 

in order to achieve the lowest error.(we want $\hat{Y}_i$ to be as close as possible to $Y_i$ )

<p align="center">
	<img src="/C096411/image/less1/Capture1.PNG" align="middle">
</p>


In order to achieve the learning goal($\hat{Y}_i$ to be as close as possible to $Y_i$) we want to minimize the sum of all  error(green line) as much as possible. 

#### Formulation:


	
The goal is to find $\omega_0,\omega_1$ that minimize the error.

##### Finding $\omega_0,\omega_1$ that minimize this equation:

<p align="center">
	<img src="/C096411/image/less1/Capture4.PNG" align="middle">
</p>

<a name='LR_G'></a>
#### Generalization :


Our main goal is to do well on the real world not on our training set S. 
Let’s assume the real world model is not a linear model but it's possible to draw a line such that
$\sum$errors(green lines) would be 0. in this case we can imagine the error as a independent variable with a
variance $\sigma$ and mean=0:

$\hat{Y}-Y=\epsilon$

##### such that:

$E(\hat{Y}-Y)=E(\epsilon)=0 \to E(\hat{Y})=E(Y)$

$E(\hat{\omega_1})=E(\omega_1)=\omega_1$

$E(\hat{\omega_0})=E(\omega_0)=\omega_0$

##### Lets prove the equality for $\hat{\omega_0}$ and $\hat{\omega_1}$ holds:

<div class="fighighlight">
</div>


<a name='LR_nD'></a>
### General case nD Model:


Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :


#### The equation is now:

$$
\arg min {(Y-\hat{Y})}^2={(Y-X_i\omega)}^2 
$$

#### Finding $\omega$ that minimize this equation:

$ \frac{d}{d\omega }=2 X^{T}(Y-X\omega)=0\to \omega =\frac{X^T Y}{X^T X} $

<a name='PR'></a>

<div class="fighighlight">
</div>

## Perceptron


Our main goal is to find a linear separation rule for data that can be separated by a line:
<p align="center">
	<img src="/C096411/image/less2/graph3.PNG" align="middle">
</p>

	

### Geometrical explanation(line point distance):

This section provide short explanation on how to compute distance between point and a line.  

<p align="center">
	<img src="/C096411/image/less2/graph1.PNG" align="middle">
</p> 

#### In general $<X,\hat{\omega}>+\omega_0 $=distance from line with normal  $\hat{\omega}$ and offset $\omega_0$



### Perceptron algorithm:



* Sample m datapoints  $S={{(x_1,y_1),...(x_m,y_m)}}$

* intialize $\omega^{1}={{0,0...0}} $  

* loop time t:

	* loop samples m:

		* if wrong classification   $ y<\omega,x>\leq0 $

			* update            $\omega^{t+1}=\omega^{t}+y_i x_i $
	

	
#### Understanding perceptron update rule:

$ Y_i<\omega^t,x_i>\le 0 $ means wrong classification we updated $\omega^{t+1}=\omega^t+y_ix_i $. 
Lets check how the new $\omega^{t+1}$ is doing on the $x_i,y_i$ example:

<p align="center">
	<img src="/C096411/image/less3/Capture2.PNG" align="middle">
</p> 




#### Optimal soultion:

<table>
	<tr>
		<td>
			<img src="/C096411/image/less2/graph3.PNG" >	
		</td>
		<td>
			<img src="/C096411/image/less2/graph6.PNG" >
		</td>
	</tr>
	
</table>
	
The optimal solution is defined has the solution which produce the highest margin. 
In order to find this optimal solution let's go back to our equation:

distance=$y_i<\hat{\omega},x_i>\to $ distance=$y_i<\frac{\omega}{||\omega||},x_i>$

We can see that the distance is dependent in ||$\omega$||. The lower ||$\omega$|| is the bigger the distance is.
From this we can derive the second perceptron role: argmin ||$\omega$||

	
####  Perceptron converges rule:

##### definitions: 

- B=||$\omega*$||, R=max||$x_i$||

- $ \omega*=\arg min ||\omega|| s.t \, y_i<\hat{\omega},x_i> \geq 1 $

- $ \omega^{1}=0$(intialization to 0)


###### Assumptions:

Lets assume linear seperation is possible.

 ###### goal:
 
 We want to show that perceptron algorithm will stop after $(RB)^2 $ steps.
 
 In order to show that we wil proof that:
 
$\\ 1 \geq \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||||\omega*||} \geq \frac{\sqrt(T)}{BR} $

**It's easy to see that $ \frac {sqrt(T)}{BR} \leq 1 $ is equivalent to $ T \leq RB^2 $
 
##### proof:

left inequality : 

$ \\\\ \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||||\omega*||}=cos(\omega^{T+1},\omega*) \leq 1 $

The right inequality:

##### (1) $ \, {<\omega^{T+1},\omega*>} \geq T $ proof:

- The update term of the perceptron is:

	* $  \,\,\, \omega^{t+1}=\omega^{t}+x_iy_i $

- In general we can write $\omega^{i}$:

	* $ \omega^{i}=\omega^{1}+\sum\nolimits_{2}^{i} X_iy_i $

- This means we can write $\omega^{T+1}$ as:

	* (P.1.1) $ \omega^{T+1}=\omega^{1}+\sum\nolimits_{2}^{T+1} X_iy_i=\sum\nolimits_{2}^{T+1} X_iy_i $

- Also by definition because $\omega*$ is the soultion and we assume linear seperation:

	* (P.1.2) $ <X_iy_i,\omega*> \geq 1 $

- Using both (P.1.1)+(P.1.2) 

	* $ \,\,\, {<\omega^{T+1},\omega*>} =<\sum\nolimits_{2}^{T+1} X_iy_i,\omega*> \geq T $
 
#####  (2)  $ ||\omega^{T+1}||^2 \leq TR^2 $ proof:


  - $ ||\omega^{T+1}||^2=||\omega^{T}+xiy_i||^2 \leq ||\omega^{T}||^2 +||xiy_i||^2 (**Triangle-inequ) $
  
  	$ ||\omega^{T}||^2 +||xi||^2 \leq ||\omega^{T}||^2 +R^2 $
  
  - now we can do the same repeatedly for $||\omega^{T}||^2 $ until we get:
  
	* $ ||\omega^{T+1}||^2 \leq TR^2 $
  
#### (1)/(2):

* $ \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||} \leq \frac{T}{\sqrt(T)R}$   | devide-by  $ ||\omega*||=B $ 

* $ \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||||\omega*||} \geq \frac{\sqrt(T)}{BR}$
 
<a name='LR'></a>


<div class="fighighlight">
</div>

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

</div>

