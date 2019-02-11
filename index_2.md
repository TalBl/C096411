#### Stochastic gradient descent vs batch gradient descent

The question is how ofen <img src="/tex/387d53b5c707db0c552f64f83202eca2.svg?invert_in_darkmode&sanitize=true" align=middle width=127.91468744999999pt height=24.65753399999998pt/> is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

##### Why to differ one over the other:  

In very large data sets saving X and <img src="/tex/32902e719b16dec67b28c9943762cd89.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> vectors or matrix can occupy large junk of your allocation memory. In addition Stochastic gradient descent(SGD) widely use for online learning. on the other hand, batch gradient descent optimization rule is much smoother. usually today the combination of the two is used taking batches equal to <img src="/tex/f8f25e4580c418a51dc556db0d8d2b93.svg?invert_in_darkmode&sanitize=true" align=middle width=16.34523329999999pt height=21.839370299999988pt/> samples.
 
##### perceptron vs SVM

Perceptron is a private solution of SVM. 
SVM using: SGD, hindge loss, L2 regularization, <img src="/tex/03eacc2fd045b3303fea4e4a58943bcc.svg?invert_in_darkmode&sanitize=true" align=middle width=81.43845929999999pt height=22.831056599999986pt/>, <img src="/tex/687cbffb26975762f46a31184ed6be3d.svg?invert_in_darkmode&sanitize=true" align=middle width=38.88877739999999pt height=21.18721440000001pt/> is eqvivalent to perceptron.

In this case:
- J= <img src="/tex/6da055cd64665ef6d4f58f751dda63b1.svg?invert_in_darkmode&sanitize=true" align=middle width=239.25002640000002pt height=26.76175259999998pt/>)
- for <img src="/tex/cecada05f154a8e1b1a749ba3f7bc016.svg?invert_in_darkmode&sanitize=true" align=middle width=111.36770534999998pt height=21.18721440000001pt/> : 
 * <img src="/tex/d217234ff5b0d59f59aab252421f6363.svg?invert_in_darkmode&sanitize=true" align=middle width=124.8951759pt height=24.657735299999988pt/>
 * <img src="/tex/08385b3c304b93a5119411d63a320d1e.svg?invert_in_darkmode&sanitize=true" align=middle width=170.09681039999998pt height=24.657735299999988pt/>

### SVM convergence Proof for GD mode:

There are many proofs that convex function can be optmized to global minimum. We also proofed convergence in perceptron and showed the maximum number of steps to convergence is <img src="/tex/7c7d3a7854511a059790770fab7c4198.svg?invert_in_darkmode&sanitize=true" align=middle width=45.239853449999984pt height=26.76175259999998pt/> which is eqvivalent to SGD with hindge loss and L2 regularization.
In this section we want to find the number of steps to conveges in general case.

#### Assumption:

- f is convex.
- ||<img src="/tex/251346e82e5a886dc502d813ef819f93.svg?invert_in_darkmode&sanitize=true" align=middle width=63.06504764999998pt height=24.65753399999998pt/>    # caled lipschitz law
- <img src="/tex/b069971bf103a572e24d468693101029.svg?invert_in_darkmode&sanitize=true" align=middle width=235.20055845pt height=24.65753399999998pt/>
- <img src="/tex/7075eeb392adcb405376e19ae28b8eda.svg?invert_in_darkmode&sanitize=true" align=middle width=47.743431449999996pt height=21.18721440000001pt/>
##### notations:

<img src="/tex/2467296285aa56007da10826480803c4.svg?invert_in_darkmode&sanitize=true" align=middle width=60.49556699999999pt height=22.831056599999986pt/> -update step in step i.

#### Goal:

We want to show that after T steps of gradient descent with <img src="/tex/156ddf585ee9cbf653f553060bc5681c.svg?invert_in_darkmode&sanitize=true" align=middle width=72.96881129999998pt height=30.648287999999997pt/>:

<img src="/tex/af898eed760c68efc31a943c0b7a07a8.svg?invert_in_darkmode&sanitize=true" align=middle width=159.37675874999996pt height=30.648287999999997pt/>

<img src="/tex/27f17a2cd67e0c90f1a733600367450d.svg?invert_in_darkmode&sanitize=true" align=middle width=84.24727739999999pt height=27.77565449999998pt/>

We look on <img src="/tex/9b137c49035e9c7eb366cabcde2075e8.svg?invert_in_darkmode&sanitize=true" align=middle width=87.88422884999999pt height=22.831056599999986pt/> will almost never achive minimum <img src="/tex/419cf1413615ba72a339141ffa96a44a.svg?invert_in_darkmode&sanitize=true" align=middle width=19.041115499999986pt height=15.296829900000011pt/> but will bounce around the minimum dependent on size of <img src="/tex/1d0496971a2775f4887d1df25cea4f7e.svg?invert_in_darkmode&sanitize=true" align=middle width=8.751954749999989pt height=14.15524440000002pt/>.

#### Proof:

<p align="center">
	<img src="./Lesson_5/Capture.PNG" align="middle">
</p>

##### step 1:

Using the 2 propertie of convex functions(orange line(g) always bellow the convex function):

- <img src="/tex/13f33a37c9e8ae8d2fa4bf388dadbdc4.svg?invert_in_darkmode&sanitize=true" align=middle width=241.14722444999998pt height=24.65753399999998pt/>
- <img src="/tex/c574cd758052c67ae7c0e003f42c4267.svg?invert_in_darkmode&sanitize=true" align=middle width=304.70881814999996pt height=24.65753399999998pt/>
- <img src="/tex/085d6d898985182d0db5a3428d2f2012.svg?invert_in_darkmode&sanitize=true" align=middle width=267.19169564999993pt height=24.65753399999998pt/>
- <img src="/tex/0301a31089ccf7197ac60f94f3cbe340.svg?invert_in_darkmode&sanitize=true" align=middle width=204.97022204999996pt height=27.77565449999998pt/>
  
 ##### step 2:
 Using the 1 propertie of convex functions(black line always above the convex function):
 
- <img src="/tex/de3f03a0491a97df7c3872bf69e69b5f.svg?invert_in_darkmode&sanitize=true" align=middle width=376.70629095pt height=36.460254599999985pt/>
 
 ##### step1+ step 2:
   
- (step 1) <img src="/tex/3f099c973e8b1fe10d2702eff6f452e1.svg?invert_in_darkmode&sanitize=true" align=middle width=307.66424369999993pt height=29.168957400000025pt/>
- (step 2) <img src="/tex/882b6f81022f6439bf554439d91e5131.svg?invert_in_darkmode&sanitize=true" align=middle width=154.74538364999998pt height=36.460254599999985pt/>  
- (lipschitz law) <img src="/tex/a6e9f477e3f2ff3b87971a7ba98651ac.svg?invert_in_darkmode&sanitize=true" align=middle width=146.42334135pt height=35.18167619999999pt/>


   
### SVM convergence Proof for SGD mode:

In SGD we choose a sample randomly(<img src="/tex/efdc72463ea6b450188e7ffa32fb40d9.svg?invert_in_darkmode&sanitize=true" align=middle width=157.70991224999997pt height=24.65753399999998pt/>) from our training set (S). 

#### Defining the problem as stochastic optimization:

- <img src="/tex/3dc50708fbbd2c3b3e0f5757b153dbe4.svg?invert_in_darkmode&sanitize=true" align=middle width=92.05857539999998pt height=24.65753399999998pt/>
- <img src="/tex/e94be2a050e026e333a20deb8f78152a.svg?invert_in_darkmode&sanitize=true" align=middle width=249.4951404pt height=27.77565449999998pt/>

#### Goal:

<img src="/tex/d027de1b6a42e973851d886afec66718.svg?invert_in_darkmode&sanitize=true" align=middle width=185.24436974999998pt height=30.648287999999997pt/>
 
#### Proof:
The proof is similar to GD.

### SVM SGD generalization:

 training set:  <img src="/tex/fe9a944280dc3d01376f733806503f06.svg?invert_in_darkmode&sanitize=true" align=middle width=168.76348829999998pt height=24.65753399999998pt/> presampling m samples from some distribution D.
 
 test set: <img src="/tex/6717f3028e91eea6a2eb7ad7fa22f857.svg?invert_in_darkmode&sanitize=true" align=middle width=82.29827099999999pt height=24.65753399999998pt/> stochastic sampling from some distribution D. E(T)=mean of the distribution.
 
 Modified training set <img src="/tex/197dbc3d662993e8a57c95b4b6dc6d49.svg?invert_in_darkmode&sanitize=true" align=middle width=221.86669229999995pt height=24.7161288pt/> combination of training and test set. 

#### Objective :
<p align="center"><img src="/tex/6c52b8e33c34aee0c74f40eef3c6d064.svg?invert_in_darkmode&sanitize=true" align=middle width=484.2532018499999pt height=43.11594705pt/></p>

#### Proof :
<p align="center"><img src="/tex/39fce556def3c658b48b4949ea357209.svg?invert_in_darkmode&sanitize=true" align=middle width=555.31062015pt height=94.45104405pt/></p>

##### mean on both sides:

<p align="center"><img src="/tex/9aa74212477a268fa369c1d3f048bc58.svg?invert_in_darkmode&sanitize=true" align=middle width=664.9844008499999pt height=18.312383099999998pt/></p>


#### bound and understanding stability:

##### Notation :
Loss training set: sample m+1 times from our distribution D and use m samples to minimize J getting-<img src="/tex/45b070fe62295df8726e95928aca4a3b.svg?invert_in_darkmode&sanitize=true" align=middle width=21.89698169999999pt height=22.831056599999986pt/>
Loss test set: us the samples from the training set but now use m+1 samples to minimize J getting-<img src="/tex/6dab9fecea3a01cf93f51d6d0b460fe2.svg?invert_in_darkmode&sanitize=true" align=middle width=38.54090129999999pt height=22.831056599999986pt/>

Stability=E[Loss test set-Loss training set] 

Our goal is to have 0 stability , which means the test set and the training set accuracy of the model is similar.

##### Finding bound :

###### step 1:
<p align="center"><img src="/tex/b50e445c6807836dd58ba5ed68982364.svg?invert_in_darkmode&sanitize=true" align=middle width=524.40460545pt height=18.31054665pt/></p>

###### step 2-using <img src="/tex/6dec54c48a0438a5fcde6053bdb9d712.svg?invert_in_darkmode&sanitize=true" align=middle width=8.49888434999999pt height=14.15524440000002pt/> lipschitz :

<p align="center"><img src="/tex/8e0c364ab94cd79e48d5f2135e0382c1.svg?invert_in_darkmode&sanitize=true" align=middle width=561.2699268pt height=65.20022025pt/></p>

###### step 3:

<p align="center"><img src="/tex/0282b2739e9558ffe954f5cb6b6f5b69.svg?invert_in_darkmode&sanitize=true" align=middle width=835.80987105pt height=144.02271015pt/></p>

###### step 1+2+3:

<p align="center"><img src="/tex/31c3260f1eb0d1910a71a00067a18c90.svg?invert_in_darkmode&sanitize=true" align=middle width=561.2699268pt height=65.00407815pt/></p>

#### Example hindge loss:
<p align="center"><img src="/tex/dd01362a29c1cf8c147c87247bb62a8a.svg?invert_in_darkmode&sanitize=true" align=middle width=253.52025765pt height=128.36764545pt/></p>

We want g to be as small as possible. lets find <img src="/tex/fd8be73b54f5436a5cd2e73ba9b6bfa9.svg?invert_in_darkmode&sanitize=true" align=middle width=9.58908224999999pt height=22.831056599999986pt/> that minimize g:

<p align="center"><img src="/tex/7d8564d9386d88a8be31df3fb7c63015.svg?invert_in_darkmode&sanitize=true" align=middle width=292.46280194999997pt height=41.2104693pt/></p>
