---
layout: post
title: "Understanding Tensors"
date: 2024-10-03
categories: Maths, AI
excerpt: "What is a Tensor? This is a question that is usually discussed in mathematics or physics lectures. With the advent of neural networks, we can see its prominence in the field of AI as well..
For a physicist - A tensor is a mathematical object that can be used to describe a physical quantity. "
---

What is a Tensor? This is a question which is usually discussed in mathematics or physics lectures. With the advent of neural networks we can see its prominence in the field of AI as well..
For a physicist - Tensor is a mathematical object that can be used to describe a physical quantity. Vectors and Scalars are just special cases of tensors. They can be covariant or contravariant. They have some special transformation rules too. 
But we are not heading towards a course in General relativity, Hence In our discussion, we will look into tensor simply as multidimensional array. 
But one can ask, why to even use tensors here? we will try to answer this question in the upcoming post. First let's familiarize ourselves with this concept.

## Tensor Basics: Dimensions and Rank 

To define a tensor, we need two things- i) dimension ii) rank(order).
Each tensor lives in some vector space it can have dimension(m) like 1,2,3..... so on. Also, to represent each element we need some indices, it is called rank(n) of tensor.
If there is a tensor of rank-n and dimension-m, then it will have $m^n$ components.

Let us understand it with a simple example:
Suppose m = 2 , n = 1, then it will have 2 components and 1 index. Suppose m = 2 and n = 1. This tensor will have 2 components and 1 index. We've seen this tensor before - it's a vector in 2D space! $A_i = (A_1,A_2)$.
Actually vector and scalar are also tensors. Vector is tensor of rank 1, it can be represented by a column. Scalar is tensor of rank 0, it is represented by a number.
If we take n=2,m=2, it will have 4 components. Also it will have two indices for each component. Surely we don't have name for it. But it's representation looks familiar.
It is a matrix.
$$
A_{i,j} = \begin{bmatrix}  
a_{11} & a_{12}\\  
a_{21} & a_{22}   
\end{bmatrix}
$$

If we increase rank further we will have a structure like a rubric cube and so on. Higher order tensors are hard to visualize.

## Tensor Operations
We have understood these objects little bit, now next question is, can we do ordinary addition, multiplication etc. with these? The answer is, yes.
Multiplication is not straightforward, there are many concepts like element-wise multiplication, inner product, outer product etc.

### Addition and Subtraction

We can add two tensors, provided they have same shape. It is similar to element wise addition or subtraction of Matrix. The final object will also be a tensor of same shape.



### Inner Product

Inner product is generalization of dot product for the tensors.
It takes two tensors and return a tensor of lower order by contracting along a specified direction.
For tensor of rank-2:
$$(A.B)_{i,k}= \sum_{j=1}^{n} A_{i,j}.B_{j,k}$$ 

Example:
$$
A = \begin{bmatrix}  
1 & 2\\  
4 & 5
\end{bmatrix}
\\
,
B = \begin{bmatrix}  
2 & 2\\  
5 & 12   
\end{bmatrix}
$$
$$
A.B = \begin{pmatrix}  
1*2+5*2 & 2*1+2*12\\  
2*4+5*4 & 4*2+12*5   
\end{pmatrix}
$$


Dot product is special case of Inner product, where both of tensors are vectors.

`u` · `v` = u₁v₁ + u₂v₂ + ... + uₙvₙ


### Outer Product
Given two tensors, outer product returns the tensor whose order is sum of the order of inputs.
For rank-1 tensor(Vector):
$$A\otimes B=A_i * B_j$$
It will become a tensor of rank-2.
Example:
A = [1,2,5,4], B=[5,0,2]

$$A \otimes B = A*B^T= \begin{bmatrix}  
1*5 & 1*0 & 1*2\\  
2*5 & 2*0 & 2*2 \\
5*5 & 5*0 & 5*2 \\
4*5 & 4*0 & 4*2
\end{bmatrix}=\begin{bmatrix}  
5& 0& 2\\  
10 & 0 & 4 \\
25 & 0 & 10 \\
20 & 0 & 8
\end{bmatrix} $$ 
Here the order of product is 2.

Similarly we can extend this process to higher order tensors of p-th and q-th order.

$$(A ⊗ B)_{i1...ip j1...jq} = A_{i1...ip} * B{j1...jq}$$



