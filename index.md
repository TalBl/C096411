## Quick Intro

This course is an introduction machine learning basics theory and practice. Learning is a general word refers to decision making using previews knowledge. There are 3 different types of learning:

### Supervised learning
supervised learning is maybe the most common modern way of teaching. In this method some "Teacher" shows you an example
and you are required to repeat the example logic on some other examples.


<img src="./Lesson_0/image1.PNG" />

### Unsupervised learning:

Unsupervised learning is a way to make Decisions based on correlation in the data.

<img src="./Lesson_0/Image2.PNG" >


### Reinforcement learning:

In this method the Decision is based on interaction with the environment. The learning is done using Trial and error. 

<img src="./Lesson_0/Image3.PNG" >
 


## Linear regression 

### Notations:

<p align="center"><img src="/tex/deed5a976bc21a58974765470f762967.svg?invert_in_darkmode&sanitize=true" align=middle width=500.97334319999993pt height=117.56169315pt/></p>



In linear regression we assume the connection between X and Y is linear:
<img src="/tex/0c30b8a45eb9c4b777e0681c018f1f45.svg?invert_in_darkmode&sanitize=true" align=middle width=110.50777649999998pt height=31.141535699999984pt/> trying to fit <img src="/tex/f4661f991f454717a2f55bca1bbb53ea.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> in order to achieve the lowest error.(we want<img src="/tex/39053daaabd24fd4a891b570d0e8b71f.svg?invert_in_darkmode&sanitize=true" align=middle width=14.194299900000003pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>)

<img src="./Lesson_1/Capture1.PNG" >


In order to achieve the learning goal(<img src="/tex/4be0688c6c52f0fe18ef69ee724c7114.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>) we want to minimize the sum of all  – error as much as possible. 

#### The formulation is:

<img src="/tex/d02322874875d8983fec512aac90f760.svg?invert_in_darkmode&sanitize=true" align=middle width=383.3007585pt height=44.51174640000002pt/>
	
The goal is to find <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/>that minimize the error.

#### Finding <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> that minimize this equation:

<img src="./Lesson_1/Capture4.PNG" >

### Generalization:

Our main goal is to do well on the real world not on our training set S. 
Let’s assume the real world model is not a linear model but it's possible to draw a line such that
<img src="/tex/a5a3c89b53bed887e7e194b0670abc9a.svg?invert_in_darkmode&sanitize=true" align=middle width=17.35165739999999pt height=24.657735299999988pt/>errors(green lines) would be 0. in this case we can imagine the error as a independent variable with a
variance <img src="/tex/8cda31ed38c6d59d14ebefa440099572.svg?invert_in_darkmode&sanitize=true" align=middle width=9.98290094999999pt height=14.15524440000002pt/> and mean=0:

<img src="/tex/80a688401b2d63aeb61914789c6784da.svg?invert_in_darkmode&sanitize=true" align=middle width=75.07395389999999pt height=31.141535699999984pt/>

such that:

<img src="/tex/ca89eb69465758b6088dd7d9603ea63f.svg?invert_in_darkmode&sanitize=true" align=middle width=332.22947505pt height=31.141535699999984pt/>
<img src="/tex/db4687f9b00b761097c90fa73c326767.svg?invert_in_darkmode&sanitize=true" align=middle width=160.35375344999997pt height=24.65753399999998pt/>
<img src="/tex/3f9dbf0b3d5cc2a4eb6671ed6a6f7396.svg?invert_in_darkmode&sanitize=true" align=middle width=160.35375344999997pt height=24.65753399999998pt/>

Lets prove the equality for <img src="/tex/747fe3195e03356f846880df2514b93e.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=14.15524440000002pt/> and <img src="/tex/d7b3f21735902404cb0e0d7ba7d13d5f.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=14.15524440000002pt/> holds:

<p align="center"><img src="/tex/3458ec4e9d788b903089ed1dfcc6bc90.svg?invert_in_darkmode&sanitize=true" align=middle width=486.9725916pt height=167.67248684999998pt/></p>



Now using the formulation above we want to 

### General case:

Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :
<p align="center"><img src="/tex/b19f2899fc690a170bfb567feb9dd070.svg?invert_in_darkmode&sanitize=true" align=middle width=157.88615865pt height=69.71700614999999pt/></p>

#### The minimization equation is now:
<p align="center"><img src="/tex/6fc422262f6502040f3f70c54e85d136.svg?invert_in_darkmode&sanitize=true" align=middle width=239.41068689999997pt height=32.940961349999995pt/></p>

#### Finding <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that minimize this equation:

<img src="/tex/380e0bd4a705031f0b3ea2ee23979386.svg?invert_in_darkmode&sanitize=true" align=middle width=270.3127812pt height=34.099002299999995pt/>









