---
layout: page
permalink: /SVM/
mathjax: true
---

- [Convex properties](#conv_prop)
- [Loss functions convexity proof](#Con_pr)
- [Non linear SVM](#non_svm)
- [Regularization term](#rg_term)
- [SVM final form-loss+regularization](#SVM_f)
- [SVM vs Perceptron](#SVM_pre)
- [SVM convergence](#SVM_conv)
- [SVM generalization](#SVM_conv)
  - [example generalization hindge loss](#SVM_gen_hin)


## SVM:

SVM concept is much closer to optimization approach:

- build a convex function with parameter W

- minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...)

- find optimal solution


<a name='conv_prop'></a>
### convex functions properies:

<p align="center">
	<img src="/C096411/image/less4/Capture.PNG" align="middle">
</p>

(1) line connects two points on the function will always be above the function(black line).

(2) points on the tangent Line are below the function(orange line). 

#### Conditions written mathematically:

black line = <img src="/C096411/tex/bebc3b72468407f542fc7a0cefed1bc1.svg" align="middle" width="239.0527623pt" height="24.65753399999998pt"/>

(1) <img src="/C096411/tex/c6c8611dbe712f795e13ca6bb676f8fb.svg" align="middle" width="227.80761465pt" height="24.65753399999998pt"/>

orange line = <img src="/C096411/tex/32bf8f68debb51bf5317c45bb506c645.svg" align="middle" width="224.9973891pt" height="24.7161288pt"/>

(2) <img src="/C096411/tex/304ce02a15f93b71ed1bb09c85f501b8.svg" align="middle" width="254.44775564999998pt" height="24.65753399999998pt"/>

### convex loss functions:

<p align="center">
	<img src="/C096411/image/less4/Capture2.PNG" align="middle">
</p>
We already saw some of the functions:

- 0-1 loss if <img src="/C096411/tex/10ed5b1ec98c30a601121c417f908b99.svg" align="middle" width="220.94645265000003pt" height="22.831056599999986pt"/>

- perceptron loss:  <img src="/C096411/tex/a8bc73e0215ba3cfa94b823bb346ddf7.svg" align="middle" width="141.15191474999997pt" height="24.65753399999998pt"/>

- Hindge loss(percept"ron with 1 as margin):  <img src="/C096411/tex/cd2c95460ec787c2c9c6cefb1bfb03eb.svg" align="middle" width="169.46231444999998pt" height="24.65753399999998pt"/>

- log loss(percept"ron with 1 as margin):  <img src="/C096411/tex/939d2ba2ed58cd7272bf9603fd6d331a.svg" align="middle" width="145.54749329999999pt" height="27.91243950000002pt"/>

<a name='Con_pr'></a>
### convexity proof:

#### Hindge loss and percept"ron:

both percept"ron and the hindge loss are sum of two linear functions one with zero slope and one with a slope off 1. 
a linear function is by definition convex and a sum of convex functions is convex.

#### Log loss convexity:

if <img src="/C096411/tex/446d7724bc30a4c0df9d95c85d20977d.svg" align="middle" width="70.53650669999999pt" height="24.7161288pt"/> then function is convex.

<img src="/C096411/tex/b7e932675e72003546f4d9235479c2dd.svg" align="middle" width="153.83515289999997pt" height="38.19539789999999pt"/>

<a name='non_svm'></a>
### Non linear seperation SVM:

We can create nun linear lines easily by just choosing the right features(x) to work with. 

example:

<p align="center">
	<img src="/C096411/image/less4/Capture3.PNG" align="middle">
</p>

We want to seperate the +/- and our features is x1=x,x2=y easy to see that linear classification 
in a form of <img src="/C096411/tex/dfbb92691f48a6c68ef9e61bb2a2ddaf.svg" align="middle" width="125.71913804999998pt" height="19.1781018pt"/> will do poorly.
from the picture it's easy to see that a circle with radius 1 is the best solution:
<img src="/C096411/tex/b611c9eb2d86c650d01c1af1ddbf9d56.svg" align="middle" width="83.76692609999998pt" height="26.76175259999998pt"/> or in classification role <img src="/C096411/tex/7eb45dbaa3e9bf356017a106b4fb6422.svg" align="middle" width="219.47248454999996pt" height="26.76175259999998pt"/> .

In order to solve this problem lets choose new features <img src="/C096411/tex/3f895053a05fde4ba8e506d1f4e42b82.svg" align="middle" width="118.34074064999999pt" height="26.76175259999998pt"/> 

now we have a linear classification problem:

 <img src="/C096411/tex/b807f67cad74895cd56bc1c3571b8c6a.svg" align="middle" width="248.3290359pt" height="24.65753399999998pt"/>

We can generlize this to any elipse  <img src="/C096411/tex/454a15e1bf2bdb84826aa779105ea5ad.svg" align="middle" width="295.0184127pt" height="26.76175259999998pt"/> 

We can generlize it to any polynomial <img src="/C096411/tex/18866f54e78ba8402fe636c30a4254e7.svg" align="middle" width="189.8398062pt" height="26.76175259999998pt"/> 

The feature selection is called the kernal of the system.

<a name='rg_term'></a>
### Regularization term:

We have seen regularization term before minimize <img src="/C096411/tex/5c6c894b142bc1232b0e11057a63a2dc.svg" align="middle" width="29.08680224999999pt" height="24.65753399999998pt"/>. We have also prooved that in the percept"ron
role this condition increase the margin to optimal solution. 

In general: The more features the more our equation is complex, we simply cannot comprehensively sample all the possible combinations, leaving vast regions of feature space in the dark. This problem is called the curse dimensionality.
The regularization term goal is to cancell unnecessary or correlated features leaving us with smaller region to search.

<p align="center">
	<img src="/C096411/image/less4/Capture4.PNG" align="middle">
</p>

#### <a href="https://medium.freecodecamp.org/the-curse-of-dimensionality-how-we-can-save-big-data-from-itself-d9fa0f872335/">further reading</a> 

#### L1 and L2 Regularization terms:

- L1(Lasso regression): <img src="/C096411/tex/383e0268a36bd3b2c13c70aaa75dfea9.svg" align="middle" width="58.71103424999998pt" height="24.657735299999988pt"/>

- L2(Lasso regression): <img src="/C096411/tex/a23dffeff9bb98d5a8f93a5d0299231c.svg" align="middle" width="49.79450519999999pt" height="26.76175259999998pt"/>


comparison:

<p align="center">
	<img src="/C096411/image/less4/Capture5.PNG" align="middle">
</p>

The green line (L2-norm) is the unique shortest path, while the red, blue, yellow (L1-norm) are all same length (=12) for the same route. Generalizing this to n-dimensions. This is why L2-norm has unique solutions while L1-norm does not.

#### Notes:

##### Sparsity:

L2 minimization will minimize all <img src="/C096411/tex/ae4fb5973f393577570881fc24fc2054.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/> while L1 will create realy small-zero <img src="/C096411/tex/ae4fb5973f393577570881fc24fc2054.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/>  and very large <img src="/C096411/tex/ae4fb5973f393577570881fc24fc2054.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/> .

example:

L2-  <img src="/C096411/tex/67d5f4fea6ff00721aa61fda16aada72.svg" align="middle" width="73.82632784999998pt" height="27.77565449999998pt"/>---better solution then---- <img src="/C096411/tex/18ba3af0453ffa85c5f4167de85e3a36.svg" align="middle" width="69.26927204999998pt" height="24.65753399999998pt"/>

L1-  <img src="/C096411/tex/67d5f4fea6ff00721aa61fda16aada72.svg" align="middle" width="73.82632784999998pt" height="27.77565449999998pt"/>--------equally good-------- <img src="/C096411/tex/18ba3af0453ffa85c5f4167de85e3a36.svg" align="middle" width="69.26927204999998pt" height="24.65753399999998pt"/> 

#### <a href="http://www.chioka.in/differences-between-l1-and-l2-as-loss-function-and-regularization/">further reading</a> 

<a name='SVM_f'></a>
### SVM final form Loss+regularization

#### build a convex function with parameter W

We already showed convexity to the log-loss,hindge-loss and perceptron. The L1(linear function),L2(quadratic function) Regularization terms are also convex. By definition(derivation is a linear operator) some of two convex function is also convex. We can write an optimization rule subjected to equality constraints(Lagrange multiplier):

L(<img src="/C096411/tex/b79d1105b6900ffc883e3e210ab7d3a6.svg" align="middle" width="27.71687159999999pt" height="22.831056599999986pt"/>)=loss(<img src="/C096411/tex/ae4fb5973f393577570881fc24fc2054.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/>)+<img src="/C096411/tex/fd8be73b54f5436a5cd2e73ba9b6bfa9.svg" align="middle" width="9.58908224999999pt" height="22.831056599999986pt"/>XRegularization

J(<img src="/C096411/tex/cd20f0f2cfe649409e738e7cddc63861.svg" align="middle" width="170.03706885pt" height="27.77565449999998pt"/> 

#####  minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...) :

Our goal is to find <img src="/C096411/tex/ae4fb5973f393577570881fc24fc2054.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/> that minimize J(<img src="/C096411/tex/6a25f78a4f9ee1ae0226f75622040d97.svg" align="middle" width="34.10958869999999pt" height="24.65753399999998pt"/>. There are variety of optimization technics finding optimal solution

for convex functions here are a list of some commun used in the field of ML:

##### Gradient descent:

<img src="/C096411/tex/04911b65e01a92bc1a3e6c65c1611f93.svg" align="middle" width="123.83933264999999pt" height="22.465723500000017pt"/>

##### Newton method:

<img src="/C096411/tex/985111ab1284fb4d7e9c15ee99731f2c.svg" align="middle" width="186.04270574999998pt" height="26.76175259999998pt"/>

##### conjugate gradient method:



<p align="center"><img src="/C096411/tex/35013eece0f7e0a914379ea65fa6bfdc.svg" align="middle" width="171.69148259999997pt" height="143.2484295pt"/></p>



##### Other methods and futer reading:

momentum,Rms prop and adam(combination of momentum and Rms) are versions of gradient descent widely used today.

##### <a href="https://blog.paperspace.com/intro-to-optimization-momentum-rmsprop-adam/">further reading</a> 

#### Stochastic gradient descent vs batch gradient descent

The question is how ofen <img src="/C096411/tex/387d53b5c707db0c552f64f83202eca2.svg" align="middle" width="127.91468744999999pt" height="24.65753399999998pt"/> is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

##### Why to differ one over the other:  

In very large data sets saving X and <img src="/C096411/tex/32902e719b16dec67b28c9943762cd89.svg" align="middle" width="10.82192594999999pt" height="14.15524440000002pt"/> vectors or matrix can occupy large junk of your allocation memory. In addition Stochastic gradient descent(SGD) widely use for online learning. on the other hand, batch gradient descent optimization rule is much smoother. usually today the combination of the two is used taking batches equal to <img src="/C096411/tex/f8f25e4580c418a51dc556db0d8d2b93.svg" align="middle" width="16.34523329999999pt" height="21.839370299999988pt"/> samples.

<a name='SVM_pre'></a>
##### perceptron vs SVM

Perceptron is a private solution of SVM. 
SVM using: SGD, hindge loss, L2 regularization, <img src="/C096411/tex/03eacc2fd045b3303fea4e4a58943bcc.svg" align="middle" width="81.43845929999999pt" height="22.831056599999986pt"/>, <img src="/C096411/tex/687cbffb26975762f46a31184ed6be3d.svg" align="middle" width="38.88877739999999pt" height="21.18721440000001pt"/> is eqvivalent to percept"ron.

In this case:
- J= <img src="/C096411/tex/6da055cd64665ef6d4f58f751dda63b1.svg" align="middle" width="239.25002640000002pt" height="26.76175259999998pt"/>)
- for <img src="/C096411/tex/cecada05f154a8e1b1a749ba3f7bc016.svg" align="middle" width="111.36770534999998pt" height="21.18721440000001pt"/> : 
 * <img src="/C096411/tex/d217234ff5b0d59f59aab252421f6363.svg" align="middle" width="124.8951759pt" height="24.657735299999988pt"/>
 * <img src="/C096411/tex/08385b3c304b93a5119411d63a320d1e.svg" align="middle" width="170.09681039999998pt" height="24.657735299999988pt"/>

<a name='SVM_conv'></a>

### SVM convergence Proof for GD mode:

There are many proofs that convex function can be optmized to global minimum. We also proofed convergence in percept"ron and showed the maximum number of steps to convergence is <img src="/C096411/tex/7c7d3a7854511a059790770fab7c4198.svg" align="middle" width="45.239853449999984pt" height="26.76175259999998pt"/> which is eqvivalent to SGD with hindge loss and L2 regularization.
In this section we want to find the number of steps to conveges in general case.

#### Assumption:

- f is convex.
- <img src="/C096411/tex/251346e82e5a886dc502d813ef819f93.svg" align="middle" width="63.06504764999998pt" height="24.65753399999998pt"/>     (lipschitz law)
- <img src="/C096411/tex/b069971bf103a572e24d468693101029.svg" align="middle" width="235.20055845pt" height="24.65753399999998pt"/>
- <img src="/C096411/tex/7075eeb392adcb405376e19ae28b8eda.svg" align="middle" width="47.743431449999996pt" height="21.18721440000001pt"/>


#### notations:

<img src="/C096411/tex/2467296285aa56007da10826480803c4.svg" align="middle" width="60.49556699999999pt" height="22.831056599999986pt"/> -update step in step i.

#### Goal:

We want to show that after T steps of gradient descent with <img src="/C096411/tex/156ddf585ee9cbf653f553060bc5681c.svg" align="middle" width="72.96881129999998pt" height="30.648287999999997pt"/>:

<img src="/C096411/tex/af898eed760c68efc31a943c0b7a07a8.svg" align="middle" width="159.37675874999996pt" height="30.648287999999997pt"/>

<img src="/C096411/tex/27f17a2cd67e0c90f1a733600367450d.svg" align="middle" width="84.24727739999999pt" height="27.77565449999998pt"/>

We look on <img src="/C096411/tex/9b137c49035e9c7eb366cabcde2075e8.svg" align="middle" width="87.88422884999999pt" height="22.831056599999986pt"/> will almost never achive minimum <img src="/C096411/tex/419cf1413615ba72a339141ffa96a44a.svg" align="middle" width="19.041115499999986pt" height="15.296829900000011pt"/> but will bounce around the minimum dependent on size of <img src="/C096411/tex/1d0496971a2775f4887d1df25cea4f7e.svg" align="middle" width="8.751954749999989pt" height="14.15524440000002pt"/>.

#### Proof:

<p align="center">
	<img src="/C096411/image/less5/Capture.PNG" align="middle">
</p>

##### step 1:

Using the 2 propertie of convex functions(orange line(g) always bellow the convex function):

- <img src="/C096411/tex/13f33a37c9e8ae8d2fa4bf388dadbdc4.svg" align="middle" width="241.14722444999998pt" height="24.65753399999998pt"/>
- <img src="/C096411/tex/c574cd758052c67ae7c0e003f42c4267.svg" align="middle" width="304.70881814999996pt" height="24.65753399999998pt"/>
- <img src="/C096411/tex/085d6d898985182d0db5a3428d2f2012.svg" align="middle" width="267.19169564999993pt" height="24.65753399999998pt"/>
- <img src="/C096411/tex/0301a31089ccf7197ac60f94f3cbe340.svg" align="middle" width="204.97022204999996pt" height="27.77565449999998pt"/>
  
 ##### step 2:
 Using the 1 propertie of convex functions(black line always above the convex function):
 
- <img src="/C096411/tex/de3f03a0491a97df7c3872bf69e69b5f.svg" align="middle" width="376.70629095pt" height="36.460254599999985pt"/>
 
 ##### step1+ step 2:
   
- (step 1) <img src="/C096411/tex/3f099c973e8b1fe10d2702eff6f452e1.svg" align="middle" width="307.66424369999993pt" height="29.168957400000025pt"/>
- (step 2) <img src="/C096411/tex/882b6f81022f6439bf554439d91e5131.svg" align="middle" width="154.74538364999998pt" height="36.460254599999985pt"/>  
- (lipschitz law) <img src="/C096411/tex/a6e9f477e3f2ff3b87971a7ba98651ac.svg" align="middle" width="146.42334135pt" height="35.18167619999999pt"/>

   
### SVM convergence Proof for SGD mode:

In SGD we choose a sample randomly(<img src="/C096411/tex/efdc72463ea6b450188e7ffa32fb40d9.svg" align="middle" width="157.70991224999997pt" height="24.65753399999998pt"/>) from our training set (S). 

#### Defining the problem as stochastic optimization:

- <img src="/C096411/tex/3dc50708fbbd2c3b3e0f5757b153dbe4.svg" align="middle" width="92.05857539999998pt" height="24.65753399999998pt"/>
- <img src="/C096411/tex/e94be2a050e026e333a20deb8f78152a.svg" align="middle" width="249.4951404pt" height="27.77565449999998pt"/>

#### Goal:

<img src="/C096411/tex/d027de1b6a42e973851d886afec66718.svg" align="middle" width="185.24436974999998pt" height="30.648287999999997pt"/>
 
#### Proof:

The proof is similar to GD.

<a name='SVM_gen'></a>
### SVM SGD generalization:

 training set:  <img src="/C096411/tex/fe9a944280dc3d01376f733806503f06.svg" align="middle" width="168.76348829999998pt" height="24.65753399999998pt"/> presampling m samples from some distribution D.
 
 test set: <img src="/C096411/tex/6717f3028e91eea6a2eb7ad7fa22f857.svg" align="middle" width="82.29827099999999pt" height="24.65753399999998pt"/> stochastic sampling from some distribution D. E(T)=mean of the distribution.
 
 Modified training set <img src="/C096411/tex/197dbc3d662993e8a57c95b4b6dc6d49.svg" align="middle" width="221.86669229999995pt" height="24.7161288pt"/> combination of training and test set. 

#### Objective :
<p align="center"><img src="/C096411/tex/6c52b8e33c34aee0c74f40eef3c6d064.svg" align="middle" width="484.2532018499999pt" height="43.11594705pt"/></p>

#### Proof :
<p align="center"><img src="/C096411/tex/39fce556def3c658b48b4949ea357209.svg" align="middle" width="555.31062015pt" height="94.45104405pt"/></p>

##### mean on both sides:

<p align="center"><img src="/C096411/tex/9aa74212477a268fa369c1d3f048bc58.svg" align="middle" width="664.9844008499999pt" height="18.312383099999998pt"/></p>


#### bound and understanding stability:

##### Notation :
Loss training set: sample m+1 times from our distribution D and use m samples to minimize J getting-<img src="/C096411/tex/45b070fe62295df8726e95928aca4a3b.svg" align="middle" width="21.89698169999999pt" height="22.831056599999986pt"/>
Loss test set: us the samples from the training set but now use m+1 samples to minimize J getting-<img src="/C096411/tex/6dab9fecea3a01cf93f51d6d0b460fe2.svg" align="middle" width="38.54090129999999pt" height="22.831056599999986pt"/>

Stability=E[Loss test set-Loss training set] 

Our goal is to have 0 stability , which means the test set and the training set accuracy of the model is similar.

##### Finding bound :

###### step 1:
<p align="center"><img src="/C096411/tex/b50e445c6807836dd58ba5ed68982364.svg" align="middle" width="524.40460545pt" height="18.31054665pt"/></p>

###### step 2-using <img src="/C096411/tex/6dec54c48a0438a5fcde6053bdb9d712.svg" align="middle" width="8.49888434999999pt" height="14.15524440000002pt"/> lipschitz :

<p align="center"><img src="/C096411/tex/8e0c364ab94cd79e48d5f2135e0382c1.svg" align="middle" width="561.2699268pt" height="65.20022025pt"/></p>

###### step 3:

<p align="center"><img src="/C096411/tex/0282b2739e9558ffe954f5cb6b6f5b69.svg" align="middle" width="835.80987105pt" height="144.02271015pt"/></p>

###### step 1+2+3:

<p align="center"><img src="/C096411/tex/31c3260f1eb0d1910a71a00067a18c90.svg" align="middle" width="561.2699268pt" height="65.00407815pt"/></p>
<a name='SVM_gen_hin'></a>
#### Example hindge loss:
<p align="center"><img src="/C096411/tex/dd01362a29c1cf8c147c87247bb62a8a.svg" align="middle" width="253.52025765pt" height="128.36764545pt"/></p>

We want g to be as small as possible. lets find <img src="/C096411/tex/fd8be73b54f5436a5cd2e73ba9b6bfa9.svg" align="middle" width="9.58908224999999pt" height="22.831056599999986pt"/> that minimize g:

<p align="center"><img src="/C096411/tex/7d8564d9386d88a8be31df3fb7c63015.svg" align="middle" width="292.46280194999997pt" height="41.2104693pt"/></p>
