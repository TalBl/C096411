#### Stochastic gradient descent vs batch gradient descent

The question is how ofen $\omega_(t+1)=\omega_t \eta \nabla J $ is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

##### Why to differ one over the other:  

In very large data sets saving X and $\omega $ vectors or matrix can occupy large junk of your allocation memory. In addition Stochastic gradient descent(SGD) widely use for online learning. on the other hand, batch gradient descent optimization rule is much smoother. usually today the combination of the two is used taking batches equal to $2^n$ samples.
 
##### perceptron vs SVM

Perceptron is a private solution of SVM. 
SVM using: SGD, hindge loss, L2 regularization, $\lambda=frac{1}{2}$, $\eta =1$ is eqvivalent to perceptron.

In this case:
- J= $\lambda \sum \omega^2+max(0,1-y_i<\omega,x_i>$)
- for $y_i<\omega,x_i> <1 $ : 
 * $ \nabla J =\sum\omega-y_i x_i $
 * $ \omega_{t+1}=\omega_{t}+y_i x_i-\sum \omega $

### SVM convergence Proof for GD mode:

There are many proofs that convex function can be optmized to global minimum. We also proofed convergence in perceptron and showed the maximum number of steps to convergence is $(RB)^2 $ which is eqvivalent to SGD with hindge loss and L2 regularization.
In this section we want to find the number of steps to conveges in general case.

#### Assumption:

- f is convex.
- ||$\nabla f || \leq \rho $    # caled lipschitz law
- $ \omega * =argmin f(\omega) \,\, s.t \,\, ||\omega * || \leq \beta $
- $\omega_0=0$
##### notations:

$V_i= \nabla f $ -update step in step i.

#### Goal:

We want to show that after T steps of gradient descent with $\eta=\frac{\beta}{\rho \sqrt(T)} $:

$ f(\bar {\omega}) -f(\omega* ) \leq \frac{\beta}{\rho \sqrt(T)} $

$ \bar {\omega} = \frac{1}{T} \sum \omega_t $

We look on $\bar{\omega } \,\, because \,\, \omega$ will almost never achive minimum $ \omega* $ but will bounce around the minimum dependent on size of $\eta$.

#### Proof:

<p align="center">
	<img src="./Lesson_5/Capture.PNG" align="middle">
</p>

##### step 1:

Using the 2 propertie of convex functions(orange line(g) always bellow the convex function):

- $ g(\omega*) = f(\bar{\omega_t})+\nabla f(\bar{\omega_t})(\omega*-\bar{\omega_t}) $
- $ f(\omega*) \geq g(\omega*)= f(\bar{\omega_t})+\nabla f(\bar{\omega_t})(\omega*-\bar{\omega_t}) $
- $ f(\bar{\omega_t})-f(\omega*) \leq <\bar{\omega_t}-\omega*,\nabla f(\bar{\omega_t})> $
- $ \leq \frac {1}{T} \sum <\omega_t-\omega*,\nabla f(\omega_t)> $
  
 ##### step 2:
 Using the 1 propertie of convex functions(black line always above the convex function):
 
- $ \frac {1}{T} \sum <\omega_i-\omega*,\nabla f(\omega_i)> \leq \frac {(||\omega*||)^2}{2\eta}+\frac{\eta}{2}\sum (\nabla f(\omega_i))^2 $
 
 ##### step1+ step 2:
   
- (step 1) $ f(\bar(\omega))-f(\omega*) \leq  \frac {1}{T} \sum <\omega_t-\omega*,\nabla(\omega_t)> $
- (step 2) $\leq \frac {(||\omega*||)^2}{2\eta}+\frac{\eta}{2}\sum (V_i)^2 $  
- (lipschitz law) $\leq \frac{B^2}{2\eta T}+\frac{\eta\rho^2}{2}=\frac{B\rho}{\sqrt(T)} $


   
### SVM convergence Proof for SGD mode:

In SGD we choose a sample randomly($x_i,y_i \,\, i~unifom[[1,m]] $) from our training set (S). 

#### Defining the problem as stochastic optimization:

- $ E(V_t)=\nabla \omega_t $
- $ E(f(\omega_t,x_i,y_i)) = \frac {1}{m} \sum  f(\omega_t,x_i,y_i) $

#### Goal:

$ E(f(\bar {\omega}) -f(\omega* )) \leq \frac{\beta}{\rho \sqrt(T)} $
 
#### Proof:
The proof is similar to GD.

### SVM SGD generalization:

 training set:  $ S={(x_1,y_1),...(x_m,y_m)} $ presampling m samples from some distribution D.
 
 test set: $ T={(x_i,y_i)} $ stochastic sampling from some distribution D. E(T)=mean of the distribution.
 
 Modified training set $ S'={(x_1,y_1),.(x_i,y_i)..(x_m,y_m)} $ combination of training and test set. 

#### Objective :
$$
\[{{E}_{S\sim{{D}^{m}}}}[{{L}_{D}}(\hat{\omega })]\le \underbrace{{{\min }_{\omega }}({{L}_{D}}(\omega )+\lambda ||\omega |{{|}^{2}})}_{best\,result\,possible}+\underbrace{{{E}_{S\sim{{D}^{m}}}}[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })]}_{stability}\]
$$

#### Proof :
$$
\[\begin{align}
 & {{L}_{D}}(\hat{\omega })={{L}_{s}}(\hat{\omega })+{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })\le ({{L}_{s}}(\hat{\omega })+\underbrace{\lambda ||\hat{\omega }|{{|}^{2}}}_{always\,positive})+{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega }) \\ 
& \le (\underbrace{{{L}_{s}}(\omega )+\lambda ||\omega |{{|}^{2}})}_{\hat{\omega }\,is\,the\,optimize\,\omega \,on\,training\,}+[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })] \\ 
\end{align}\]
$$

##### mean on both sides:

$$
\[E({{L}_{D}}(\hat{\omega }))\le E({{L}_{s}}(\omega )+\lambda ||\omega |{{|}^{2}})+E[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })]={{L}_{s}}(\omega )+\lambda ||\omega |{{|}^{2}}+E[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })]\]
$$


#### bound and understanding stability:

Loss training set: sample m+1 times from our distribution D and use m samples to minimize J getting-$\hat{\omega}$
Loss test set: sample m+1 times from our distribution D and use m+1 samples to minimize J getting-$\hat{\omega_i}$

If we loop this prosses the average will be stability which means the how good am i doing on the real world vs training set.

This method is very simillar to cross validation, $\hat{\omega_i}$ will give me the same result in training and test. 


