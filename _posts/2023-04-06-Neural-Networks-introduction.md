---
layout: post
title: "Introduction to neural Networks"
author: ROMMANE Soukaina
categories: journal
tags: [Deep Learning]
image: BeautifulCouple.jpg
---


#  Why Deep Learning?

We consider the problem of handwritten digits recognition. It appears very obvious to humans to recognize a handwritten digit but imagine that we want to write a computer program that takes as input an image of handwritten digit and gives us as output the corresponding digit in the image. We can think of a program that recognize digits based on the description of the shape of each. For example, a 7 has a vertical stroke with two short strokes, one on the top left and the other on the middle. But how to express this algorithmically, and how to make those conditions in practice and manage all special cases?
We can immediately realise how it’s complicated or even impossible.
To solve this kind of problems, scientists have tough about some methods that make computers learn from data. This idea lays in the heart of Machine Learning. One of the most powerful of these algorithms is Neural Networks.

### Neural Networks
Neural Network is one of the algorithms of machine learning, inspired by the biological human brain. To explain the similarity between the human brain and the concept behind neural networks, let's try to understand how the human brain recognise the image of a cat. First, all the formations contained in the image will be transferred to the brain using the eyes, which represent in this case the input layer. Next, the brain starts to analyse this image using its biological neurons, which represent intermediates layers (the hidden layers). The last step  is decision making: is it a cat or something else? 
Based on its memory storage, the brain makes its decision and send it to be either written by hand or told by mouth or simply saved in memory (The output Layer).

### Neuron
Talking about Neuron means that there’s an input, weight, a threshold and an output. There’s two types of Neuron, the perceptron and the sigmoid.
### The perceptron
The perceptron takes binary input and gives binary output. Each input $x_i$ has a weight $w_i$ that express his importance to the output, and the threshold is a parameter of the neuron.
The output of the perceptron is given by:

$$
\begin{equation}\label{Neuron}
\overrightarrow{O}=\left\{
\begin{array}{l}
1 \; \textrm{if} \quad \sum\limits_{i} w_{i} x_{i} \; + \; \textrm{threashod} \;>0,\\
0 \; \textrm{if} \quad \sum\limits_{i} w_{i} x_{i} \;+ \; \textrm{threashod} \;\leqslant 0
\end{array}\right.
\end{equation}
$$

which is equivalent to:
$$
\begin{equation}\label{Neuron_1}
\overrightarrow{O}=\left\{
\begin{array}{l}
1 \; \textrm{if} \quad w.x \; + \; b \;>0,\\
0 \; \textrm{if} \quad w.x \; + \; b \;\leqslant 0
\end{array}\right.
\end{equation}
$$

To understand how it works, let’s take a simple example. Suppose that you want to predict if Jean is going to travel in Italy for the holidays based on tree binary variables: $x_1$ is equal  to 1 if the total price of the plane tickets and the hotel is less or equal to 500 euros and $x_1$ is equal to zero if not, $x_2$ is equal to 1 if the weather is nice and $x_2$ is equal to 0 if not, $x_3$ is equal to 1 if his best friend is going to give him company and it’s equal to zero if not.\\
The output $\overrightarrow{O}$ is a binary variable

$$
\begin{equation}\label{example}
\overrightarrow{O}=\left\{
\begin{array}{l}
1 \; \textrm{if Jean is going to Italy} \\
0 \; \textrm{else}
\end{array}\right.
\end{equation}
$$

To each input, we associate a weight that express the importance of this input. 

$w_i$ is the weight of the input of $x_i$ for $i \in \{1,2,3\}$.
The output is given by: 

$$\overrightarrow{O}=W.X +b$$ 

If we take $W =[7, 5, 9]$, $b = -12$ and $x =[1,0,1]^t$,
that’s mean that the total price of the plane tickets and the hotel is less or equal to 500 euros, the weather is not nice and his best friend is going with him. Based on the weight matrix, the fact that his best friend is going with him is more important than the ticket price which is more important than the weather for Jean. 
Based on the weight matrix and the input given: 

$$\overrightarrow{O} = [7,5,9].[1,0,1]^t - 12$$ 

which implies that Jean Go. 

Changing the weight matrix and the threshold will gives different results, even if this change is too much small. This is one of the problems of perceptron: \textbf{Small change in input doesn’t imply small change in output }
For example  for $x =[0,0,1]$ implies that

$$\overrightarrow{O} = W.x +b = -1 <0$$ 
 
implies that Jean doesn’t go.
This is a big problem using perceptron to make decision. 

### The sigmoid

![Perceptron vs Sigmoid](/assets/img/perceptron_sigmoid.png)


