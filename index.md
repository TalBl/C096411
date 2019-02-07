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

equations:

```math
#### a^2+b^2=c^2
```
#### Let $\text{S}_1(N) = \sum_{p=1}^N \text{E}(p)$

#### $E = mc^2$


$$
#### \mu = \frac{\sum_{i=1}^{n}{x}}{n}
$$ 

The first component of this approach is to define the score function that maps the pixel values of an image to confidence scores for each class. We will develop the approach with a concrete example. As before, let's assume a training dataset of images \\( x_i \in R^D \\), each associated with a label \\( y_i \\). Here \\( i = 1 \dots N \\) and \\( y_i \in \{ 1 \dots K \} \\). That is, we have **N** examples (each with a dimensionality **D**) and **K** distinct categories. For example, in CIFAR-10 we have a training set of **N** = 50,000 images, each with **D** = 32 x 32 x 3 = 3072 pixels, and **K** = 10, since there are 10 distinct classes (dog, cat, car, etc). We will now define the score function \\(f: R^D \mapsto R^K\\) that maps the raw image pixels to class scores.

**Linear classifier.** In this module we will start out with arguably the simplest possible function, a linear mapping:

$$
f(x_i, W, b) =  W x_i + b
$$

#### In linear regression we assume the connection between X and Y is linear:
${{\hat{Y}}_{i}}={{\omega }_{1}}{{X}_{i}}+{{\omega }_{0}}$ trying to fit ${{\omega }_{1}},{{\omega }_{0}}$ in order to achieve the lowest error.(we want$~{{\hat{Y}}_{i}}$ to be as close as possible to ${{Y}_{i}}$)

here the sum is taken over all pixels. Here is the procedure visualized:
