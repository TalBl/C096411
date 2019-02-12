---
layout: page
mathjax: true
permalink: /Perceptron/
---

<hr />
	
- [Linear regression-2D-Model](#LR_2D)
  - [2D-Model-Generalization](#LR_G)
- [Linear regression-nD-Model](#LR_nD)
- [Perceptron](#PR)

<hr />

## Perceptron


Our main goal is to find a linear separation rule for data that can be separated by a line:
<p align="center">
	<img src="/C096411/image/less2/graph3.PNG" align="middle">
</p>

	
<hr />

### Geometrical explanation(line point distance):

This section provide short explanation on how to compute distance between point and a line.  

<p align="center">
	<img src="/C096411/image/less2/graph1.PNG" align="middle">
</p> 

##### In general $<X,\hat{\omega}>+\omega_0 $ = distance from line with normal  $\hat{\omega}$ and offset $\omega_0$


<hr />

### Perceptron algorithm:



* Sample m datapoints  $S={{(x_1,y_1),...(x_m,y_m)}}$

* intialize $\omega^{1}={{0,0...0}} $  

* loop time t:

	* loop samples m:

		* if wrong classification   $ y<\omega,x>\leq0 $

			* update            $\omega^{t+1}=\omega^{t}+y_i x_i $
	

<hr />

#### Understanding perceptron update rule:

$ Y_i<\omega^t,x_i>\le 0 $ means wrong classification we updated $\omega^{t+1}=\omega^t+y_ix_i $. 
Lets check how the new $\omega^{t+1}$ is doing on the $x_i,y_i$ example:

<p align="center">
	<img src="/C096411/image/less3/Capture2.PNG" align="middle">
</p> 



<hr />

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
	
The optimal solution he highest margin. is defined has the solution which produce t
In order to find this optimal solution let's go back to our equation:

$$
distance=y_i<\hat{\omega},x_i>\to distance=y_i<\frac{\omega}{||\omega||},x_i>
$$

We can see that the distance is dependent on $\sum \omega_i^2 $. The lower  $\sum \omega_i^2 $ is the bigger the distance is.
From this we can derive the ** second perceptron role: **

$$ 
 \arg min ||\omega||  
 $$

<hr />

####  Perceptron converges rule:

##### definitions: 

##### B=||$\omega^*$||, R=max||$x_i$|| 

##### $\omega^*=\arg min ||\omega|| s.t ~~ y_i<\hat{\omega},x_i> \geq 1 $

##### $\omega^{1}=0$(intialization to 0) 


#### Assumptions:

linear seperation is possible.

#### goal:
 
 We want to show that perceptron algorithm will stop after $(RB)^2 $ steps.
 
 In order to show that we wil proof that:
$$
1 \geq \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}|| ||\omega*||} \geq \frac{\sqrt(T)}{BR} 
$$

It's easy to see that $ \frac {\sqrt(T)}{BR} \leq 1 \to T \leq RB^2 $
 
#### proof:

left inequality : 
$$
\frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||||\omega*||}=cos(\omega^{T+1},\omega*) \leq 1 
 $$

The right inequality:

##### (1) $ \, {<\omega^{T+1},\omega*>} \geq T $ proof:

<hr />

The update term of the perceptron is: $ \omega^{t+1}=\omega^{t}+x_iy_i$

In general we can write $\omega^{i}$:

##### $ \omega^{i}=\omega^{1}+\sum\nolimits_{2}^{i} X_iy_i$

This means we can write $\omega^{T+1}$ as:

##### (P.1.1) $ \omega^{T+1}=\omega^{1}+\sum\nolimits_{2}^{T+1} X_iy_i=\sum\nolimits_{2}^{T+1} X_iy_i $

Also by definition because $\omega*$ is the soultion and we assume linear seperation:

##### (P.1.2) $ <X_iy_i,\omega*> \geq 1 $

Using both (P.1.1)+(P.1.2) : 

$$ 
<\omega^{T+1},\omega*> =<\sum\nolimits_{2}^{T+1} X_i y_i,\omega*> \geq T 
$$


#####  (2)  $ ||\omega^{T+1}||^2 \leq TR^2 $ proof:

<hr />

$$ ||\omega^{T+1}||^2=||\omega^{T}+xiy_i||^2 \leq ||\omega^{T}||^2 +||xiy_i||^2 (**Triangle-inequ) \\
  
\to ||\omega^{T}||^2 +||xi||^2 \leq ||\omega^{T}||^2 +R^2  $$
  
 
###### now we can do the same repeatedly for $||\omega^{T}||^2 $ until we get:
  
###### $$ ||\omega^{T+1}||^2 \leq TR^2 $$

#### (1)/(2):

<hr />

##### $$ \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||} \leq \frac{T}{\sqrt{T}R} | \frac{1}{||\omega*||=B }$$

##### $$ \frac{<\omega^{T+1},\omega*>}{||\omega^{T+1}||||\omega*||} \geq \frac{\sqrt(T)}{BR} $$
 
<a name='LR'></a>


<hr />
