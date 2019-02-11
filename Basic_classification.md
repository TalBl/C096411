---
layout: page
mathjax: true
permalink: /classification/
---

- [Introduction:type of learning](#intro)
- [Linear regression-2D-Model](#LR_2D)
  - [2D-Model-Generalization](#LR_G)
- [Linear regression-nD-Model](#LR_nD)
- [Perceptron](#PR)
- [Logistic Regression](#LR)
- [SVM](#SVM)



<a name='intro'></a>
## Quick Intro

This course is an introduction to machine learning basics theory and practice. There are 3 different types of learning:

### Supervised learning
supervised learning is maybe the most common modern way of teaching. In this method a "Teacher" shows you an example
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

Reinforcement learning is based on interaction with the environment. The learning is done using Trial and error. 

<p align="center">
	<img src="./Lesson_0/Image3.PNG" align="middle">
</p>


<a name='LR'></a>
## Linear regression 



### 2D Basic Model:
<a name='LR_2D'></a>
#### Notations:

$$
\begin{align}
 & S(Training~data)=\left\{ \left( {{X}_{1}},{{Y}_{1}} \right),\ldots .,\left( {{X}_{m}},{{Y}_{m}} \right) \right\} \\ 
 & {{X}_{i}}=input~i\left( image,voice,\ldots  \right)~~.~~{{Y}_{i}}=True~label\left( cat,''\text{hello }\!\!~\!\!\text{ siri''}... \right) \\ 
 & {{{\hat{Y}}}_{i}}=model~approximated~label \\ 
 & m-number~of~training~vecors~X \\ 
\end{align}
$$

