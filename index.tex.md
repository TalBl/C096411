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

$$
\begin{align}
  & S=\left\{ \left( {{X}_{1}},{{Y}_{1}} \right),\ldots .,\left( {{X}_{m}},{{Y}_{m}} \right) \right\} \\ 
 & S=Training~data~ \\ 
 & {{X}_{i}}=input~i\left( image,voice,\ldots  \right)~~.~~{{Y}_{i}}=True~label\left( cat,''\text{hello }\!\!~\!\!\text{ siri''}... \right) \\ 
 & {{{\hat{Y}}}_{i}}=approximated~label \\ 
 & m-number~of~training~vecors~X \\ 
\end{align}
$$



In linear regression we assume the connection between X and Y is linear:
${{\hat{Y}}_{i}}={{\omega }_{1}}{{X}_{i}}+{{\omega }_{0}}$ trying to fit ${{\omega }_{1}},{{\omega }_{0}}$ in order to achieve the lowest error.(we want$~{{\hat{Y}}_{i}}$ to be as close as possible to ${{Y}_{i}}$)

<img src="./Lesson_1/Capture1.PNG" >


In order to achieve the learning goal(${{\hat{Y}}_{i}}$ to be as close as possible to ${{Y}_{i}}$) we want to minimize the sum of all  – error as much as possible. 

#### The formulation is:

$argmi{{n}_{{{\omega }_{0}},{{\omega }_{1}}}}~\underset{i=1}{\overset{m}{\mathop \sum }}\,{{\left( {{Y}_{i}}-{{{\hat{Y}}}_{i}} \right)}^{2}}=\underset{i=1}{\overset{m}{\mathop \sum }}\,{{\left( {{Y}_{i}}-\left( {{\omega }_{0}}+{{\omega }_{1}}{{X}_{i}} \right) \right)}^{2}}$
	
The goal is to find ${{\omega }_{0}},{{\omega }_{1}}$that minimize the error.

#### Finding ${{\omega }_{0}},{{\omega }_{1}}$ that minimize this equation:

<img src="./Lesson_1/Capture3.PNG" >

### General case:

Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :


\\begin{align}
  & Y=[{{Y}_{1}},{{Y}_{2}}....,{{Y}_{m}}] \\ 
 & X=[1,{{X}_{1}},{{X}_{2}}...,{{X}_{m}}] \\ 
 & \omega ={{[{{\omega }_{0}},{{\omega }_{1}}.....,{{\omega }_{m}}]}^{T}} \\ 
 &  \\ 
 & \arg \min {{\left( Y-\,\widehat{Y} \right)}^{2}}={{\left( Y-\,{{X}}\omega  \right)}^{2}} \\ 
\end{align}



Finding \[\omega \] that minimize this equation
$\frac{d}{d\omega }=\left( 2Y-2X\omega  \right){{X}^{T}}=0\to \omega =\frac{{{X}^{T}}Y}{{{X}^{T}}X}$




**Linear classifier.** In this module we will start out with arguably the simplest possible function, a linear mapping:

$$
f(x_i, W, b) =  W x_i + b
$$



