## Quick Intro

This course is an introduction machine learning basics theory and practice. Learning is a general word refers to decision making using previews knowledge. There are 3 different types of learning:

### Supervised learning
supervised learning is maybe the most common modern way of teaching. In this method some "Teacher" shows you an example
and you are required to repeat the example logic on some other examples.

<p align="center">
	<img src="./Lesson_0/image1.PNG" />
</p>
### Unsupervised learning:

Unsupervised learning is a way to make Decisions based on correlation in the data.

<p align="center">
	<img src="./Lesson_0/Image2.PNG" align="middle" >
</p>

### Reinforcement learning:

In this method the Decision is based on interaction with the environment. The learning is done using Trial and error. 

<p align="center">
	<img src="./Lesson_0/Image3.PNG" align="middle">
</p>


## Linear regression 

### Notations:

<p align="center"><img src="/tex/deed5a976bc21a58974765470f762967.svg?invert_in_darkmode&sanitize=true" align=middle width=500.97334319999993pt height=117.56169315pt/></p>



In linear regression we assume the connection between X and Y is linear:
<img src="/tex/0c30b8a45eb9c4b777e0681c018f1f45.svg?invert_in_darkmode&sanitize=true" align=middle width=110.50777649999998pt height=31.141535699999984pt/> trying to fit <img src="/tex/f4661f991f454717a2f55bca1bbb53ea.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> in order to achieve the lowest error.(we want<img src="/tex/39053daaabd24fd4a891b570d0e8b71f.svg?invert_in_darkmode&sanitize=true" align=middle width=14.194299900000003pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>)

<p align="center">
	<img src="./Lesson_1/Capture1.PNG" align="middle">
</p>

In order to achieve the learning goal(<img src="/tex/4be0688c6c52f0fe18ef69ee724c7114.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>) we want to minimize the sum of all  – error as much as possible. 

#### The formulation is:

<img src="/tex/d02322874875d8983fec512aac90f760.svg?invert_in_darkmode&sanitize=true" align=middle width=383.3007585pt height=44.51174640000002pt/>
	
The goal is to find <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/>that minimize the error.

#### Finding <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> that minimize this equation:

<p align="center">
	<img src="./Lesson_1/Capture4.PNG" align="middle">
</p>
### Generalization:

Our main goal is to do well on the real world not on our training set S. 
Let’s assume the real world model is not a linear model but it's possible to draw a line such that
<img src="/tex/a5a3c89b53bed887e7e194b0670abc9a.svg?invert_in_darkmode&sanitize=true" align=middle width=17.35165739999999pt height=24.657735299999988pt/>errors(green lines) would be 0. in this case we can imagine the error as a independent variable with a
variance <img src="/tex/8cda31ed38c6d59d14ebefa440099572.svg?invert_in_darkmode&sanitize=true" align=middle width=9.98290094999999pt height=14.15524440000002pt/> and mean=0:

<img src="/tex/80a688401b2d63aeb61914789c6784da.svg?invert_in_darkmode&sanitize=true" align=middle width=75.07395389999999pt height=31.141535699999984pt/>

#### such that:

<img src="/tex/1ec3912580fb1d17e3ff7a933d340d92.svg?invert_in_darkmode&sanitize=true" align=middle width=315.79105634999996pt height=31.141535699999984pt/>
<img src="/tex/990044b31ea09b9285e605a03b2cbb15.svg?invert_in_darkmode&sanitize=true" align=middle width=147.56832089999997pt height=24.65753399999998pt/>
<img src="/tex/16eace060c1897c05b280e5f00ef4f81.svg?invert_in_darkmode&sanitize=true" align=middle width=147.56832089999997pt height=24.65753399999998pt/>

#### Lets prove the equality for <img src="/tex/20a4327baf8921ad57cf2147ad7baf8d.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=22.831056599999986pt/> and <img src="/tex/c6d01153a10d0697e4ab58473caede07.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=22.831056599999986pt/> holds:

<p align="center"><img src="/tex/3458ec4e9d788b903089ed1dfcc6bc90.svg?invert_in_darkmode&sanitize=true" align=middle width=486.9725916pt height=167.67248684999998pt/></p>

### General case:

Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :
<p align="center"><img src="/tex/b19f2899fc690a170bfb567feb9dd070.svg?invert_in_darkmode&sanitize=true" align=middle width=157.88615865pt height=69.71700614999999pt/></p>

#### The minimization equation is now:
<p align="center"><img src="/tex/6fc422262f6502040f3f70c54e85d136.svg?invert_in_darkmode&sanitize=true" align=middle width=239.41068689999997pt height=32.940961349999995pt/></p>

#### Finding <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that minimize this equation:

<img src="/tex/380e0bd4a705031f0b3ea2ee23979386.svg?invert_in_darkmode&sanitize=true" align=middle width=270.3127812pt height=34.099002299999995pt/>



## Perceptron

Our main goal is to find a linear separation rule for data that can be separated by a line:
<p align="center">
	<img src="./Lesson_2/graph3.PNG" align="middle">
</p>

### Geometrical explanation(line point distance):

This section provide neet explanation on how to compute distance between point and a line.

<p align="center">
	<img src="./Lesson_2/graph1.PNG" align="middle">
</p> 

In general <img src="/tex/c3d34d8a63a41701e5954f9b612f25f9.svg?invert_in_darkmode&sanitize=true" align=middle width=100.96246379999998pt height=22.831056599999986pt/>=distance from line with normal  <img src="/tex/a166e09ebe3a9840702c0d0159854a2d.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=22.831056599999986pt/> and offset <img src="/tex/747fe3195e03356f846880df2514b93e.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=14.15524440000002pt/>

### Perceptron algorithm:
<p align="center"><img src="/tex/7135738a947389929a37bb3299d4ba00.svg?invert_in_darkmode&sanitize=true" align=middle width=282.23711999999995pt height=144.10433565pt/></p>

#### Understanding perceptron update term:

After <img src="/tex/674adff4f45b5ae8d3fae7a9370a1d76.svg?invert_in_darkmode&sanitize=true" align=middle width=118.63936259999998pt height=26.085962100000025pt/>(means wrong classification) we updated <img src="/tex/d5e78f926bd247c412fa80e755e437a1.svg?invert_in_darkmode&sanitize=true" align=middle width=119.45003564999998pt height=26.76175259999998pt/>. 
Lets check how the new <img src="/tex/763aa9768edf29e38a67642e3db1b250.svg?invert_in_darkmode&sanitize=true" align=middle width=32.43161954999999pt height=26.76175259999998pt/> is doing on the <img src="/tex/94c7199511ac0e9502948310ce626c41.svg?invert_in_darkmode&sanitize=true" align=middle width=34.88399804999999pt height=14.15524440000002pt/> example:

<p align="center"><img src="/tex/11d3aa5416cae805ac4e63831a8fdbd1.svg?invert_in_darkmode&sanitize=true" align=middle width=595.2313883999999pt height=42.202701749999996pt/></p>


#### Optimal soultion:

<table>
	<tr>
		<td>
			<img src="./Lesson_2/graph3.PNG" >	
		</td>
		<td>
			<img src="./Lesson_2/graph6.PNG" >
		</td>
	</tr>
	
</table>
	
The optimal solution is defined has the solution which produce the highest margin. 
In order to find this optimal solution let's go back to our equation:

distance=<img src="/tex/e0e69ba5f224cb1653807432f5630929.svg?invert_in_darkmode&sanitize=true" align=middle width=85.79694254999998pt height=22.831056599999986pt/> ->distance=<img src="/tex/1259a31d367c8c38a0b0e64b82c7daf4.svg?invert_in_darkmode&sanitize=true" align=middle width=103.23081614999998pt height=22.853275500000024pt/>

We can see that the distance is dependent in ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>||. The lower ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>|| is the bigger the distance is.
From this we can derive the second perceptron role: argmin ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>||


####  Perceptron converges rule:

##### definitions: 
B=||<img src="/tex/03bf6257eb4b5d50fd63aaa53d700d19.svg?invert_in_darkmode&sanitize=true" align=middle width=19.041115499999986pt height=15.296829900000011pt/>||, R=max||<img src="/tex/9fc20fb1d3825674c6a279cb0d5ca636.svg?invert_in_darkmode&sanitize=true" align=middle width=14.045887349999989pt height=14.15524440000002pt/>||
<img src="/tex/d67f91f473bb05778cc962319ca19cca.svg?invert_in_darkmode&sanitize=true" align=middle width=257.31636315pt height=47.67123239999998pt/>
<img src="/tex/56392274d4668f82d9ad3cae9f29199a.svg?invert_in_darkmode&sanitize=true" align=middle width=48.333205799999995pt height=39.45205439999997pt/>(intialization to 0)

##### proof:

Lets assume linear seperation is possible. We want to show that perceptron algorithm will stop after <img src="/tex/7c7d3a7854511a059790770fab7c4198.svg?invert_in_darkmode&sanitize=true" align=middle width=45.239853449999984pt height=26.76175259999998pt/> steps

In order to show that we wil proof that:
<img src="/tex/b582dfebdac8ce224e0948f8e5ce3ecc.svg?invert_in_darkmode&sanitize=true" align=middle width=169.96601489999998pt height=64.98593639999997pt/>

**It's easy to see that <img src="/tex/e1c295f84039827373d52fb19375e178.svg?invert_in_darkmode&sanitize=true" align=middle width=151.86849809999998pt height=24.65753399999998pt/> is equivalent to <img src="/tex/f23534ae3f27483fe70d757977b736a2.svg?invert_in_darkmode&sanitize=true" align=middle width=66.26136165pt height=26.76175259999998pt/>

The left inequality is simpile cause: 
<img src="/tex/aa2157b190813cfbad2c9d7deec390cc.svg?invert_in_darkmode&sanitize=true" align=middle width=232.25560049999996pt height=96.21901409999997pt/>

The right inequality can be seperated to two inequalities:
##### (1) <img src="/tex/9e2b68896587ef3a6470f22dec1aaa93.svg?invert_in_darkmode&sanitize=true" align=middle width=132.67835295pt height=27.6567522pt/> proof:

- The update term of the perceptron is:

	* <img src="/tex/0c28d3e7419815e882ada9fdea8d7915.svg?invert_in_darkmode&sanitize=true" align=middle width=119.45003564999998pt height=26.76175259999998pt/>

- In general we can write <img src="/tex/43613c3dd9fdff7ce34d1e976e2b2ed3.svg?invert_in_darkmode&sanitize=true" align=middle width=15.472805699999988pt height=27.15900329999998pt/>:

	* <img src="/tex/a23a0f0c54ba707df9925cf074c5eec2.svg?invert_in_darkmode&sanitize=true" align=middle width=135.76753904999998pt height=31.75825949999999pt/>

- This means we can write <img src="/tex/b25a79ea3630f9ea0167e75ed6210c07.svg?invert_in_darkmode&sanitize=true" align=middle width=36.999522449999986pt height=27.6567522pt/> as:

	* (P.1.1) <img src="/tex/734b32c714d73d536ed947528f09ffaa.svg?invert_in_darkmode&sanitize=true" align=middle width=278.55151005pt height=32.256008400000006pt/>

- Also by definition because <img src="/tex/03bf6257eb4b5d50fd63aaa53d700d19.svg?invert_in_darkmode&sanitize=true" align=middle width=19.041115499999986pt height=15.296829900000011pt/> is the soultion and we assume linear seperation:

	* (P.1.2) <img src="/tex/c3df0edc208d80ffd2a4fdc9de096c11.svg?invert_in_darkmode&sanitize=true" align=middle width=119.24458094999999pt height=22.465723500000017pt/>

- Using both (P.1.1)+(P.1.2) 

	* <img src="/tex/7d5d6104b5a3a904557af74bfb1f1c2c.svg?invert_in_darkmode&sanitize=true" align=middle width=286.22843865pt height=32.256008400000006pt/>
 
#####  (2)  <img src="/tex/b404999f17c717e01dfc95a94422cdab.svg?invert_in_darkmode&sanitize=true" align=middle width=116.42872394999998pt height=27.6567522pt/> proof:


  - <img src="/tex/712c82a89d883233d22ae641649fc7d7.svg?invert_in_darkmode&sanitize=true" align=middle width=486.37012379999993pt height=27.6567522pt/>
  
  	<img src="/tex/a5fc0e0e1084e567fef1a0f45c90bc1e.svg?invert_in_darkmode&sanitize=true" align=middle width=215.59230990000003pt height=27.6567522pt/>
  
  - now we can do the same repeatedly for <img src="/tex/8ba23cbb1c4581f0d9d2ad6552458e81.svg?invert_in_darkmode&sanitize=true" align=middle width=45.994941299999994pt height=27.6567522pt/> until we get:
  
	* <img src="/tex/b404999f17c717e01dfc95a94422cdab.svg?invert_in_darkmode&sanitize=true" align=middle width=116.42872394999998pt height=27.6567522pt/>
  
#### (1)/(2):

* <img src="/tex/3e902680172e3442533dfd97bd8c3224.svg?invert_in_darkmode&sanitize=true" align=middle width=141.03762255pt height=35.8209489pt/>   | devide-by  <img src="/tex/ff9a38cd49b9e03e40cd839b823f239e.svg?invert_in_darkmode&sanitize=true" align=middle width=79.82281065pt height=24.65753399999998pt/> 

* <img src="/tex/dafdb732e46ffe718273946f8364d5ea.svg?invert_in_darkmode&sanitize=true" align=middle width=137.856576pt height=43.068399000000014pt/>
 

## Logistic regression:

The Perceptron rule <w,x> gave us distance which is between <img src="/tex/90562dba6bf49f79b1c70b8b77e31ded.svg?invert_in_darkmode&sanitize=true" align=middle width=62.10057149999999pt height=24.65753399999998pt/> when <img src="/tex/f7a0f24dc1f54ce82fecccbbf48fca93.svg?invert_in_darkmode&sanitize=true" align=middle width=16.43840384999999pt height=14.15524440000002pt/> is far in the positive side and 
<img src="/tex/1d5ba78bbbafd3226f371146bc348363.svg?invert_in_darkmode&sanitize=true" align=middle width=29.223836399999986pt height=19.1781018pt/> is in the far in the negetive side. if we think about it the bigger the distance the more likely that
the classification is right when 0 is 50% to each side.

Insted of working in distances space we want to talk about chances or probability to be a part of a class given some x , p(y|x).
to do so we need to change our space from <img src="/tex/90562dba6bf49f79b1c70b8b77e31ded.svg?invert_in_darkmode&sanitize=true" align=middle width=62.10057149999999pt height=24.65753399999998pt/> to [0,1]. A very usefull function to do so is the sigmoid function:

<p align="center">
	<img src="./Lesson_3/Capture1.PNG" align="middle">
</p>

The function in <img src="/tex/8860040216a2e61c344544a77b5cd2ce.svg?invert_in_darkmode&sanitize=true" align=middle width=16.43840384999999pt height=14.15524440000002pt/> is 1(heigh probability) and 0(low probability) in <img src="/tex/b9652934c10244a0a8922e2315545845.svg?invert_in_darkmode&sanitize=true" align=middle width=29.223836399999986pt height=19.1781018pt/>

#### Classes probability:

<p align="center"><img src="/tex/8e7a487149a8001fb6a36dc2bf283cf6.svg?invert_in_darkmode&sanitize=true" align=middle width=205.52482665pt height=34.3600389pt/></p>

<p align="center"><img src="/tex/fed0a164f2c02654792cc0c41d97b6f9.svg?invert_in_darkmode&sanitize=true" align=middle width=346.61284514999994pt height=34.3600389pt/></p>

So we can say in general that:

<p align="center"><img src="/tex/a0c3bb08b0edfc6c42d3b1e74388fee7.svg?invert_in_darkmode&sanitize=true" align=middle width=187.22124465pt height=34.3600389pt/></p>


#### Finding the optimal <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>:

We can use maximum likelihood estimation method to find <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that will maximize the probability:

<p align="center"><img src="/tex/1df5b004798e038a30c9e86373998ab0.svg?invert_in_darkmode&sanitize=true" align=middle width=323.9386788pt height=44.89738935pt/></p>

because log is monotonic increasing function we can maximize log(P(y_1,y_2...y_m|x_1,x_2...x_,))

<p align="center"><img src="/tex/e7f7213a25a34231908aa9a21d05edf2.svg?invert_in_darkmode&sanitize=true" align=middle width=249.36182534999998pt height=44.89738935pt/></p>

This is same as:

<p align="center"><img src="/tex/b01e400e92d3bc19aef62ca564852934.svg?invert_in_darkmode&sanitize=true" align=middle width=242.8626057pt height=44.89738935pt/></p>

This equation is called log-loss loss function. while we already saw the mean square root loss: 

<p align="center"><img src="/tex/1421bd2ec6a07f1da22493b66d0b1bea.svg?invert_in_darkmode&sanitize=true" align=middle width=218.88848025pt height=44.89738935pt/></p>

This loss gives use the probability result between [0,1]


## SVM:

In general there is not much diffrent between SVM and perceptron in practice. both in the end try to minimize a form of this equation: 
<img src="/tex/d67f91f473bb05778cc962319ca19cca.svg?invert_in_darkmode&sanitize=true" align=middle width=257.31636315pt height=47.67123239999998pt/>

SVM consept is much closer to optimization approach(we have seen somthing similar in Logistic regression):

- build a convex function with parameter <img src="/tex/b7eeb7b0cafac9a943fc0aa95400e7b7.svg?invert_in_darkmode&sanitize=true" align=middle width=8.21920935pt height=14.15524440000002pt/>

- minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...)

- find optimal solution

### convex functions properies:

<p align="center">
	<img src="./Lesson_4/Capture.PNG" align="middle">
</p>

Has seen in the image a convex function is defined such that:

(1) line connects two points on the function will always be above the function(black line).

(2) points on the tangent Line are below the function(orange line). 

mathematically this two conditions can be written:

Line between A and B(black line) is = <img src="/tex/3f23e9ff11c67c53a8a19c98216b8cb0.svg?invert_in_darkmode&sanitize=true" align=middle width=193.8470688pt height=24.65753399999998pt/>

(1) <img src="/tex/c6c8611dbe712f795e13ca6bb676f8fb.svg?invert_in_darkmode&sanitize=true" align=middle width=227.80761465pt height=24.65753399999998pt/>

orange line = <img src="/tex/32bf8f68debb51bf5317c45bb506c645.svg?invert_in_darkmode&sanitize=true" align=middle width=224.9973891pt height=24.7161288pt/>

(2) <img src="/tex/304ce02a15f93b71ed1bb09c85f501b8.svg?invert_in_darkmode&sanitize=true" align=middle width=254.44775564999998pt height=24.65753399999998pt/>

### convex loss functions:

<p align="center">
	<img src="./Lesson_4/Capture2.PNG" align="middle">
</p>
We already saw some of the functions:

- 0-1 loss if <img src="/tex/10ed5b1ec98c30a601121c417f908b99.svg?invert_in_darkmode&sanitize=true" align=middle width=220.94645265000003pt height=22.831056599999986pt/>

- perceptron loss:  <img src="/tex/a8bc73e0215ba3cfa94b823bb346ddf7.svg?invert_in_darkmode&sanitize=true" align=middle width=141.15191474999997pt height=24.65753399999998pt/>

- Hindge loss(perceptron with 1 as margin):  <img src="/tex/cd2c95460ec787c2c9c6cefb1bfb03eb.svg?invert_in_darkmode&sanitize=true" align=middle width=169.46231444999998pt height=24.65753399999998pt/>

- log loss(perceptron with 1 as margin):  <img src="/tex/939d2ba2ed58cd7272bf9603fd6d331a.svg?invert_in_darkmode&sanitize=true" align=middle width=145.54749329999999pt height=27.91243950000002pt/>


### convexity proof:

#### Hindge loss and perceptron:

both perceptron and the hindge loss are sum of two linear functions one with zero slope and one with a slope off 1. 
a linear function is by definition convex and a sum of convex functions is convex.

#### Log loss convexity:

if <img src="/tex/446d7724bc30a4c0df9d95c85d20977d.svg?invert_in_darkmode&sanitize=true" align=middle width=70.53650669999999pt height=24.7161288pt/> then function is convex.

<img src="/tex/b7e932675e72003546f4d9235479c2dd.svg?invert_in_darkmode&sanitize=true" align=middle width=153.83515289999997pt height=38.19539789999999pt/>


### Non linear seperation SVM:

We can create nun linear lines easily by just choosing the right features(x) to work with. 

example:

<p align="center">
	<img src="./Lesson_4/Capture3.PNG" align="middle">
</p>

We want to seperate the +/- and our features is x1=x,x2=y easy to see that linear classification 
in a form of <img src="/tex/dfbb92691f48a6c68ef9e61bb2a2ddaf.svg?invert_in_darkmode&sanitize=true" align=middle width=125.71913804999998pt height=19.1781018pt/> will do poorly.
from the picture it's easy to see that a circle with radius 1 is the best solution:
<img src="/tex/b611c9eb2d86c650d01c1af1ddbf9d56.svg?invert_in_darkmode&sanitize=true" align=middle width=83.76692609999998pt height=26.76175259999998pt/> or in classification role <img src="/tex/7eb45dbaa3e9bf356017a106b4fb6422.svg?invert_in_darkmode&sanitize=true" align=middle width=219.47248454999996pt height=26.76175259999998pt/> .

In order to solve this problem lets choose new features <img src="/tex/3f895053a05fde4ba8e506d1f4e42b82.svg?invert_in_darkmode&sanitize=true" align=middle width=118.34074064999999pt height=26.76175259999998pt/> 

now we have a linear classification problem:

 <img src="/tex/b807f67cad74895cd56bc1c3571b8c6a.svg?invert_in_darkmode&sanitize=true" align=middle width=248.3290359pt height=24.65753399999998pt/>

We can generlize this to any elipse  <img src="/tex/454a15e1bf2bdb84826aa779105ea5ad.svg?invert_in_darkmode&sanitize=true" align=middle width=295.0184127pt height=26.76175259999998pt/> 

We can generlize it to any polynomial <img src="/tex/18866f54e78ba8402fe636c30a4254e7.svg?invert_in_darkmode&sanitize=true" align=middle width=189.8398062pt height=26.76175259999998pt/> 

The feature selection is called the kernal of the system.

### Regularization term:

We have seen regularization term before minimize <img src="/tex/5c6c894b142bc1232b0e11057a63a2dc.svg?invert_in_darkmode&sanitize=true" align=middle width=29.08680224999999pt height=24.65753399999998pt/>. We have also prooved that in the perceptron
role this condition increase the margin to optimal solution. 

In general: The more features the more our equation is complex, we simply cannot comprehensively sample all the possible combinations, leaving vast regions of feature space in the dark. This problem is called the curse dimensionality.
The regularization term goal is to cancell unnecessary or correlated features leaving us with smaller region to search.

<p align="center">
	<img src="./Lesson_4/Capture4.PNG" align="middle">
</p>

#### <a href="https://medium.freecodecamp.org/the-curse-of-dimensionality-how-we-can-save-big-data-from-itself-d9fa0f872335/">further reading</a> 

#### L1 and L2 Regularization terms:

- L1(Lasso regression): <img src="/tex/383e0268a36bd3b2c13c70aaa75dfea9.svg?invert_in_darkmode&sanitize=true" align=middle width=58.71103424999998pt height=24.657735299999988pt/>

- L2(Lasso regression): <img src="/tex/a23dffeff9bb98d5a8f93a5d0299231c.svg?invert_in_darkmode&sanitize=true" align=middle width=49.79450519999999pt height=26.76175259999998pt/>


comparison:

<p align="center">
	<img src="./Lesson_4/Capture5.PNG" align="middle">
</p>

The green line (L2-norm) is the unique shortest path, while the red, blue, yellow (L1-norm) are all same length (=12) for the same route. Generalizing this to n-dimensions. This is why L2-norm has unique solutions while L1-norm does not.

#### Notes:

##### Sparsity:

L2 minimization will minmize all <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> while L1 will create realy small-zero <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>  and very large <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> .

example:

L2-  <img src="/tex/67d5f4fea6ff00721aa61fda16aada72.svg?invert_in_darkmode&sanitize=true" align=middle width=73.82632784999998pt height=27.77565449999998pt/>---better solution then---- <img src="/tex/18ba3af0453ffa85c5f4167de85e3a36.svg?invert_in_darkmode&sanitize=true" align=middle width=69.26927204999998pt height=24.65753399999998pt/>

L1-  <img src="/tex/67d5f4fea6ff00721aa61fda16aada72.svg?invert_in_darkmode&sanitize=true" align=middle width=73.82632784999998pt height=27.77565449999998pt/>--------equally good-------- <img src="/tex/18ba3af0453ffa85c5f4167de85e3a36.svg?invert_in_darkmode&sanitize=true" align=middle width=69.26927204999998pt height=24.65753399999998pt/> 

#### <a href="http://www.chioka.in/differences-between-l1-and-l2-as-loss-function-and-regularization/">further reading</a> 

### SVM final form

#### build a convex function with parameter <img src="/tex/b7eeb7b0cafac9a943fc0aa95400e7b7.svg?invert_in_darkmode&sanitize=true" align=middle width=8.21920935pt height=14.15524440000002pt/>

We already showed convexity to the log-loss,hindge-loss and perceptron. The L1(linear function),L2(quadratic function) Regularization terms are also convex. By definition(derivation is a linear operator) some of two convex function is also convex. We can write an optimization rule subjected to equality constraints(Lagrange multiplier):

L(<img src="/tex/b79d1105b6900ffc883e3e210ab7d3a6.svg?invert_in_darkmode&sanitize=true" align=middle width=27.71687159999999pt height=22.831056599999986pt/>)=loss(<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>)+<img src="/tex/fd8be73b54f5436a5cd2e73ba9b6bfa9.svg?invert_in_darkmode&sanitize=true" align=middle width=9.58908224999999pt height=22.831056599999986pt/>XRegularization

J(<img src="/tex/cd20f0f2cfe649409e738e7cddc63861.svg?invert_in_darkmode&sanitize=true" align=middle width=170.03706885pt height=27.77565449999998pt/> 

####  minimize this function using gradient methods(gradient descent, newton method, conjugate gradient...) :

Our goal is to find <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that minimize J(<img src="/tex/6a25f78a4f9ee1ae0226f75622040d97.svg?invert_in_darkmode&sanitize=true" align=middle width=34.10958869999999pt height=24.65753399999998pt/>. There are variety of optimization technics finding optimal solution

for convex functions here are a list of some commun used in the field of ML:

##### Gradient descent:

<img src="/tex/04911b65e01a92bc1a3e6c65c1611f93.svg?invert_in_darkmode&sanitize=true" align=middle width=123.83933264999999pt height=22.465723500000017pt/>

##### Newton method:

<img src="/tex/985111ab1284fb4d7e9c15ee99731f2c.svg?invert_in_darkmode&sanitize=true" align=middle width=186.04270574999998pt height=26.76175259999998pt/>

##### conjugate gradient method:



<p align="center"><img src="/tex/35013eece0f7e0a914379ea65fa6bfdc.svg?invert_in_darkmode&sanitize=true" align=middle width=171.69148259999997pt height=143.2484295pt/></p>



##### Other methods and futer reading:

momentum,Rms prop and adam(combination of momentum and Rms) are versions of gradient descent widely used today.

##### <a href="https://blog.paperspace.com/intro-to-optimization-momentum-rmsprop-adam/">further reading</a> 

### Stochastic gradient descent vs batch gradient descent

The question is how ofen <img src="/tex/9e0b6d5a22648fc8d4fd2ee24b4d8799.svg?invert_in_darkmode&sanitize=true" align=middle width=152.03932095pt height=24.65753399999998pt/> is done.

- Stochastic gradient descent  J is computed every sample J=L.

- batch gradient descent J is computed after going over all samples J=E(L)

### Why to differ one over the other:  

In very large data sets saving X and <img src="/tex/32902e719b16dec67b28c9943762cd89.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> vectors or matrix can occupy large junk of your allocation memory. In addition 











