---
title: "Tensors and AI"
date: 2024-10-05
categories: [Maths, AI]
excerpt: "Tensor and differential geometry are two mathematical tools heavily used in general relativity.  
Starting from 1916, in his equations Einstein began to use a rule to make his calculations more clear and concise "
math: True
---

> "I have made a great discovery in mathematics; I have suppressed the summation sign every time that the summation must be made over an index which occurs twice..." - Albert Einstein

After publishing his groundbreaking papers on the special theory of relativity and the photoelectric effect in his  "miracle year" of 1905, Einstein began developing the general theory of relativity, extending the principles of special relativity to include gravity and accelerated frames of reference.  
Tensor and differential geometry are two mathematical tools heavily used in general relativity.  
Starting from 1916, in his equations Einstein began to use a rule to make his calculations more clear and concise - Summation over repeated index is automatically understood without writing the summation symbol explicitly. Later, it came to be known as Einstein's summation notation.  
  
It is very useful rule and makes tensorial calculations concise -  
1.  Repeated indices are implicitly summed over  
2. Each index can appear at most twice in the equation  
3. Each term must contain identical non-repeated indices

Examples:

$$\sum_{i} a_ib_i=a_ib_i$$


Let us say we have two matrices A (m x n) and B (n x p), after multiplication resulting in a matrix C (m x p). The element Cᵢⱼ is calculated as the sum of the products of corresponding elements in the i-th row of A and the j-th column of B:

Then  $C_{i,j} = \sum_{k}A_{i,k}B_{k,j}$

It can be written simply as $C_{i,j} = A_{i,k}B_{k,j}$ using summation notation.


## Usefulness of Tensor in AI

As we discussed tensors are very useful in many branches of physics particularly in General relativity etc. However, this object is widely used in deep learning and AI too. Let us explore the reason -  
  
### 1. It can easily represent multidimensional data  
In AI we often deal we data in forms such as text or images. An image can be represented with a tensor.  
For each element 3 indices- (height, width, and color channel) are required to show the pixel intensity for a specific channel.  

Example:  
A 256x256 RGB image is a tensor of shape (256,256,3).  
However, a 256x256 grayscale image is a tensor of shape (256,256) since its color channel value is zero for all pixels.  
<p align="center">
 <img src="https://raw.githubusercontent.com/adhikarinarayan/adhikarinarayan.github.io/refs/heads/main/assets/images/3dtensorr.svg" alt="3dtensor">
</p>


In NLP we use embedding for the representation of text. Usually, we store these embeddings in a matrix, which is again a tensor.
### 2. Generalize Linear Algebra  
Using tensors we can generalize concepts like eigenvalue, and eigenvectors to higher orders. We can generalize the transformation too. For example, we can easily apply linear transformation in CNN where data is represented in the form of a tensor.  
  
### 3. Efficient computation  
GPUs are the backbone of computation in AI these days. They are designed for the tensor operations. Libraries like Pytorch use this and optimize the algorithms for enhancing the computational efficiency of deep learning models. Since Tensors extend the concept of matrix to higher dimensions they are highly suitable for to be used to parallel processing.


## References

[Einstein Summation -- from Wolfram MathWorld](https://mathworld.wolfram.com/EinsteinSummation.html)
