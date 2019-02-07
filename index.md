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

<img src="./Lesson_1/Capture3.PNG" >

### General case:

Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :
<p align="center"><img src="/tex/4caf25b23b5d00ecb26ed11c54dd1f2d.svg?invert_in_darkmode&sanitize=true" align=middle width=424.64207115pt height=20.2374942pt/></p>

#### The minimization equation is now:
<p align="center"><img src="/tex/6fc422262f6502040f3f70c54e85d136.svg?invert_in_darkmode&sanitize=true" align=middle width=239.41068689999997pt height=32.940961349999995pt/></p>

#### Finding W that minimize this equation:

Finding \[\omega \] that minimize this equation
<img src="/tex/7dcdedec5402fc8dd15699ff8b76c8ad.svg?invert_in_darkmode&sanitize=true" align=middle width=278.53197735000003pt height=34.099002299999995pt/>





