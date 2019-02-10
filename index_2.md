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

### SVM convergence Proof:

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

- <img src="/tex/9ae0fdb1c1eeefd101130fa66d2b434c.svg?invert_in_darkmode&sanitize=true" align=middle width=241.14729045pt height=24.65753399999998pt/>
- <img src="/tex/f174545e1e58f80fd9af63effe3df62c.svg?invert_in_darkmode&sanitize=true" align=middle width=304.7088825pt height=24.65753399999998pt/>
- <img src="/tex/9c09df6eced4c7577214dee92343bcc3.svg?invert_in_darkmode&sanitize=true" align=middle width=267.19176164999993pt height=24.65753399999998pt/>
  
  ##### step 2:
  
 <img src="/tex/de3f03a0491a97df7c3872bf69e69b5f.svg?invert_in_darkmode&sanitize=true" align=middle width=376.70629095pt height=36.460254599999985pt/>
 
 ##### step1+ step 2:
   
<img src="/tex/7204aa9696f5c8affae8a30617dfb981.svg?invert_in_darkmode&sanitize=true" align=middle width=360.9748263pt height=29.168957400000025pt/>
<img src="/tex/e62220b495a0154dca9e0bebc28bf63b.svg?invert_in_darkmode&sanitize=true" align=middle width=165.8926698pt height=36.460254599999985pt/>  
<img src="/tex/ff7edb8b466f5cae58e2789281402f0d.svg?invert_in_darkmode&sanitize=true" align=middle width=260.3622054pt height=35.18167619999999pt/>


   
