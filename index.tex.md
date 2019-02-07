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

$\begin{align}
  & S=\left\{ \left( {{X}_{1}},{{Y}_{1}} \right),\ldots .,\left( {{X}_{m}},{{Y}_{m}} \right) \right\} \\ 
 & S=Training~data~ \\ 
 & {{X}_{i}}=input~i\left( image,voice,\ldots  \right)~~.~~{{Y}_{i}}=True~label\left( cat,''\text{hello }\!\!~\!\!\text{ siri''}... \right) \\ 
 & {{{\hat{Y}}}_{i}}=approximated~label \\ 
 & m-number~of~training~vecors~X \\ 
\end{align}$



In linear regression we assume the connection between X and Y is linear:
${{\hat{Y}}_{i}}={{\omega }_{1}}{{X}_{i}}+{{\omega }_{0}}$ trying to fit ${{\omega }_{1}},{{\omega }_{0}}$ in order to achieve the lowest error.(we want$~{{\hat{Y}}_{i}}$ to be as close as possible to ${{Y}_{i}}$)


```math
#### a^2+b^2=c^2
```

**Linear classifier.** In this module we will start out with arguably the simplest possible function, a linear mapping:

$$
f(x_i, W, b) =  W x_i + b
$$



