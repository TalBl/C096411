#### Stochastic gradient descent vs batch gradient descent

The question is how ofen <img src="/tex/9e0b6d5a22648fc8d4fd2ee24b4d8799.svg?invert_in_darkmode&sanitize=true" align=middle width=152.03932095pt height=24.65753399999998pt/> is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

##### Why to differ one over the other:  

In very large data sets saving X and <img src="/tex/32902e719b16dec67b28c9943762cd89.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> vectors or matrix can occupy large junk of your allocation memory. In addition Stochastic gradient descent(SGD) widely use for online learning. on the other hand, batch gradient descent optimization rule is much smoother. usually today the combination of the two is used taking batches equal to <img src="/tex/f8f25e4580c418a51dc556db0d8d2b93.svg?invert_in_darkmode&sanitize=true" align=middle width=16.34523329999999pt height=21.839370299999988pt/> samples.
 
##### perceptron vs SVM

Perceptron is a private solution of SVM. 
SVM using: SGD, hindge loss, L2 regularization, <img src="/tex/03eacc2fd045b3303fea4e4a58943bcc.svg?invert_in_darkmode&sanitize=true" align=middle width=81.43845929999999pt height=22.831056599999986pt/>, <img src="/tex/687cbffb26975762f46a31184ed6be3d.svg?invert_in_darkmode&sanitize=true" align=middle width=38.88877739999999pt height=21.18721440000001pt/> is eqvivalent to perceptron.

In this case:
J= <img src="/tex/015d5b898f78df0a50e581b296a5efc9.svg?invert_in_darkmode&sanitize=true" align=middle width=49.79450519999999pt height=26.76175259999998pt/>+max(0,1-<img src="/tex/20ecc41c9e7e45d4c83629f5afe5ad50.svg?invert_in_darkmode&sanitize=true" align=middle width=85.79696399999999pt height=17.723762100000005pt/>)
for <img src="/tex/cecada05f154a8e1b1a749ba3f7bc016.svg?invert_in_darkmode&sanitize=true" align=middle width=111.36770534999998pt height=21.18721440000001pt/> : 
<img src="/tex/d217234ff5b0d59f59aab252421f6363.svg?invert_in_darkmode&sanitize=true" align=middle width=124.8951759pt height=24.657735299999988pt/>
<img src="/tex/cb9e97f3afd4ea7d173165dd854cbcb6.svg?invert_in_darkmode&sanitize=true" align=middle width=207.03947879999998pt height=24.657735299999988pt/>

### SVM convergence Proof:

There are many proofs that convex function can be optmized to global minimum. We also proofed convergence in perceptron and showed the maximum number of steps to convergence is <img src="/tex/7c7d3a7854511a059790770fab7c4198.svg?invert_in_darkmode&sanitize=true" align=middle width=45.239853449999984pt height=26.76175259999998pt/> which is eqvivalent to SGD with hindge loss and L2. 