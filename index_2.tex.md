## SVM:

SVM concept is much closer to optimization approach:

- build a convex function with parameter $\omegea$

- minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...)

- find optimal solution

<table>
	<tr>
		<td>
- [Convex properties](#conv_prop)
- [Loss functions convexity proof](#Con_pr)
- [Non linear SVM](#non_svm)
- [Regularization term](#rg_term)
- [SVM final form-loss+regularization](#SVM_f)
- [SVM vs Perceptron](#SVM_pre)
- [SVM convergence](#SVM_conv)
- [SVM generalization](#SVM_conv)
  - [example generalization hindge loss](#SVM_gen_hin)
		</td>
	</tr>
	</table>
<a name='conv_prop'></a>
### convex functions properies:

<p align="center">
	<img src="./Lesson_4/Capture.PNG" align="middle">
</p>

(1) line connects two points on the function will always be above the function(black line).

(2) points on the tangent Line are below the function(orange line). 

#### Conditions written mathematically:

black line = $\lambda f(X_b) +(1-\lambda) f(X_a), \lambda=[0,1] $

(1) $f_{convex}(black Line) \leq black Line $

orange line = $ f'_{convex}(A)(x-A)+f_{convex}(A) $

(2) $f_{convex}(orange Line) \geq orange Line $

### convex loss functions:

<p align="center">
	<img src="./Lesson_4/Capture2.PNG" align="middle">
</p>
We already saw some of the functions:

- 0-1 loss if $y_i<\hat{\omega},x_i> \leq 0, 1: 0 otherwise $

- perceptron loss:  $max (0,y_i<\hat{\omega},x>) $

- Hindge loss(perceptron with 1 as margin):  $max (0,1-y_i<\hat{\omega},x>) $

- log loss(perceptron with 1 as margin):  $ log({1+e^{-y_i<\hat{\omega},x_i>})) $

<a name='Con_pr'></a>
### convexity proof:

#### Hindge loss and perceptron:

both perceptron and the hindge loss are sum of two linear functions one with zero slope and one with a slope off 1. 
a linear function is by definition convex and a sum of convex functions is convex.

#### Log loss convexity:

if $f''(x) \geq 0 $ then function is convex.

$f''(x)= \frac {e^(x)}{(e^(x)+1)^2} \geq 0 $

<a name='non_svm'></a>
### Non linear seperation SVM:

We can create nun linear lines easily by just choosing the right features(x) to work with. 

example:

<p align="center">
	<img src="./Lesson_4/Capture3.PNG" align="middle">
</p>

We want to seperate the +/- and our features is x1=x,x2=y easy to see that linear classification 
in a form of $\omega_2 x_1 +\omega_1 x_2 +\omega_0 $ will do poorly.
from the picture it's easy to see that a circle with radius 1 is the best solution:
$x_1^2+x_2^2=1$ or in classification role $ -: x_1^2+x_2^2-1>0 ,/ +: other  $ .

In order to solve this problem lets choose new features $x1=x^2,x2=y^2$ 

now we have a linear classification problem:

 $minmize (max (0,1-y_i<\hat{\omega},x>)) $

We can generlize this to any elipse  $x1=x^2,x2=y^2,x3=xy,x1=x,y4=y$ 

We can generlize it to any polynomial $x1=x,x2=x^2,x3=x^3...$ 

The feature selection is called the kernal of the system.

<a name='rg_term'></a>
### Regularization term:

We have seen regularization term before minimize $ ||\omega ||$. We have also prooved that in the perceptron
role this condition increase the margin to optimal solution. 

In general: The more features the more our equation is complex, we simply cannot comprehensively sample all the possible combinations, leaving vast regions of feature space in the dark. This problem is called the curse dimensionality.
The regularization term goal is to cancell unnecessary or correlated features leaving us with smaller region to search.

<p align="center">
	<img src="./Lesson_4/Capture4.PNG" align="middle">
</p>

#### <a href="https://medium.freecodecamp.org/the-curse-of-dimensionality-how-we-can-save-big-data-from-itself-d9fa0f872335/">further reading</a> 

#### L1 and L2 Regularization terms:

- L1(Lasso regression): $ \lambda \sum |\omega_j| $

- L2(Lasso regression): $ \lambda \sum \omega_j^2 $


comparison:

<p align="center">
	<img src="./Lesson_4/Capture5.PNG" align="middle">
</p>

The green line (L2-norm) is the unique shortest path, while the red, blue, yellow (L1-norm) are all same length (=12) for the same route. Generalizing this to n-dimensions. This is why L2-norm has unique solutions while L1-norm does not.

#### Notes:

##### Sparsity:

L2 minimization will minimize all $\omega$ while L1 will create realy small-zero $\omega$  and very large $\omega$ .

example:

L2-  $\omega =(\frac{3}{2},\frac{3}{2})$---better solution then---- $\omega=(3,0)$

L1-  $\omega =(\frac{3}{2},\frac{3}{2})$--------equally good-------- $\omega=(3,0)$ 

#### <a href="http://www.chioka.in/differences-between-l1-and-l2-as-loss-function-and-regularization/">further reading</a> 

<a name='SVM_f'></a>
### SVM final form Loss+regularization

#### build a convex function with parameter $\omegea$

We already showed convexity to the log-loss,hindge-loss and perceptron. The L1(linear function),L2(quadratic function) Regularization terms are also convex. By definition(derivation is a linear operator) some of two convex function is also convex. We can write an optimization rule subjected to equality constraints(Lagrange multiplier):

L($\omega,\lambda $)=loss($\omega$)+$\lambda$XRegularization

J($\omega,\lambda)=E(L)=\frac{1}{n} \sum \nolimits_{1}^{n}  L $ 

####  minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...) :

Our goal is to find $\omega$ that minimize J($\omega,\lambda)$. There are variety of optimization technics finding optimal solution

for convex functions here are a list of some commun used in the field of ML:

##### Gradient descent:

$\omega_{t+1}=\omega_t-\eta \nabla J $

##### Newton method:

$\omega_{t+1}=\omega_t-\eta (\nabla ^2 J)^{-1} \nabla J $

##### conjugate gradient method:



$$
\[\begin{align}
 & {{\beta }_{t}}=\frac{|\nabla J{{({{\omega }_{t}})}^{2}}|}{|\nabla J{{({{\omega }_{t-1}})}^{2}}|} \\ 
 & {{\alpha }_{t}}=-\nabla J({{\omega }_{t}})+{{\beta }_{t}}{{\alpha }_{t-1}} \\ 
 & {{\omega }_{t+1}}={{\omega }_{t}}+\eta {{\alpha }_{t}} \\ 
 & Finding\,optimal\,\eta : \\ 
 & {{\alpha }_{t}}\nabla J({{\omega }_{t+1}})=0 \\ 
\end{align}\]
$$



##### Other methods and futer reading:

momentum,Rms prop and adam(combination of momentum and Rms) are versions of gradient descent widely used today.

##### <a href="https://blog.paperspace.com/intro-to-optimization-momentum-rmsprop-adam/">further reading</a> 

#### Stochastic gradient descent vs batch gradient descent

The question is how ofen $\omega_(t+1)=\omega_t \eta \nabla J $ is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

##### Why to differ one over the other:  

In very large data sets saving X and $\omega $ vectors or matrix can occupy large junk of your allocation memory. In addition Stochastic gradient descent(SGD) widely use for online learning. on the other hand, batch gradient descent optimization rule is much smoother. usually today the combination of the two is used taking batches equal to $2^n$ samples.

<a name='SVM_pre'></a>
##### perceptron vs SVM

Perceptron is a private solution of SVM. 
SVM using: SGD, hindge loss, L2 regularization, $\lambda=frac{1}{2}$, $\eta =1$ is eqvivalent to perceptron.

In this case:
- J= $\lambda \sum \omega^2+max(0,1-y_i<\omega,x_i>$)
- for $y_i<\omega,x_i> <1 $ : 
 * $ \nabla J =\sum\omega-y_i x_i $
 * $ \omega_{t+1}=\omega_{t}+y_i x_i-\sum \omega $

<a name='SVM_conv'></a>

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

<a name='SVM_gen'></a>
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
\[E({{L}_{D}}(\hat{\omega }))\le E({{L}_{s}}(\omega )+\lambda ||\omega |{{|}^{2}})+E[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })]={{L}_{D}}(\omega )+\lambda ||\omega |{{|}^{2}}+E[{{L}_{D}}(\hat{\omega })-{{L}_{s}}(\hat{\omega })]\]
$$


#### bound and understanding stability:

##### Notation :
Loss training set: sample m+1 times from our distribution D and use m samples to minimize J getting-$\hat{\omega_{m}}$
Loss test set: us the samples from the training set but now use m+1 samples to minimize J getting-$\hat{\omega_{m+1}}$

Stability=E[Loss test set-Loss training set] 

Our goal is to have 0 stability , which means the test set and the training set accuracy of the model is similar.

##### Finding bound :

###### step 1:
$$
\[{{E}_{S\sim{{D}^{m}}}}\left[ {{L}_{D}}\left( {\hat{\omega }} \right)-{{L}_{S}}\left( {\hat{\omega }} \right) \right]={{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right) \right]\]
$$

###### step 2-using $\rho$ lipschitz :

$$
\[\begin{align}
  & \frac{l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right)}{||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||}\le \rho  \\ 
 & {{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right) \right]\le {{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ \rho ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}|| \right] \\ 
\end{align}\]
$$

###### step 3:

$$

\[\begin{align}
  & \frac{2\rho ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||}{m}=\frac{\rho ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||}{m}+\frac{\rho ||{{{\hat{\omega }}}_{m}}-{{{\hat{\omega }}}_{m+1}}||}{m}\ge (step\,1) \\ 
 & \frac{l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right)}{m}+\frac{l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)}{m}\ge {{f}_{s}}({{{\hat{\omega }}}_{m+1}})-{{f}_{s}}({{{\hat{\omega }}}_{m}}) \\ 
 & =\left[ {{L}_{s}}\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-{{L}_{s}}\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right) \right]+\lambda ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||\,\ge (convexity\,property\,1)||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||{{\,}^{2}}\,\ge \lambda ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||{{\,}^{2}} \\ 
 & \lambda ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||{{\,}^{2}}\le \frac{2\rho ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||}{m}\,\to ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}||\,\le \frac{2\rho }{\lambda m} \\ 
\end{align}\]



$$

###### step 1+2+3:

$$

\[\begin{align}
  & {{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ l\left( {{{\hat{\omega }}}_{m+1}},{{x}_{i}},{{y}_{i}} \right)-l\left( {{{\hat{\omega }}}_{m}},{{x}_{i}},{{y}_{i}} \right) \right]\le {{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ \rho ||{{{\hat{\omega }}}_{m+1}}-{{{\hat{\omega }}}_{m}}|| \right] \\ 
 & \le {{E}_{S\sim{{D}^{m+1}},i\simU\left( m \right)}}\left[ \frac{2{{\rho }^{2}}}{\lambda m} \right]=\frac{2{{\rho }^{2}}}{\lambda m} \\ 
\end{align}\]

$$
<a name='SVM_gen_hin'></a>
#### Example hindge loss:
$$
\[\begin{align}
  & E({{L}_{D}}(\hat{\omega }))\le {{L}_{D}}(\omega )+\lambda ||\omega |{{|}^{2}}+\frac{2{{\rho }^{2}}}{\lambda m} \\ 
 & define:||\omega ||\le B \\ 
 & \le {{L}_{D}}(\omega )+\underbrace{\lambda {{B}^{2}}+\frac{2{{\rho }^{2}}}{\lambda m}}_{g} \\ 
\end{align}\]
$$

We want g to be as small as possible. lets find $\lambda$ that minimize g:

$$
\[\frac{dg}{d\lambda }=0\to \lambda *=\frac{\rho }{B}\sqrt{\frac{2}{m}},g(\lambda *)=\rho B\sqrt{\frac{\rho }{m}}\]
$$
