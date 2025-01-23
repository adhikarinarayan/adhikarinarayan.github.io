---
title: "Hopfield Networks and the Interplay of AI, Physics, and Neuroscience"
date: 2024-10-12
categories: AI
excerpt: "The Nobel Prize in Physics 2024 was awarded jointly to John J. Hopfield and Geoffrey E. Hinton for foundational discoveries and inventions that enable machine learning with artificial neural networks - Nobel Prize Committee, Royal Swedish Academy of Sciences"
math: True
author: narayan
---




<p align="center">
 <img src="https://miro.medium.com/v2/resize:fit:786/format:webp/1*_ziP-j1yel5W0hdftUKlbA.jpeg" alt="nobel"  width="600" height="400">
</p>


> The Nobel Prize in Physics 2024 was awarded jointly to John J. Hopfield and Geoffrey E. Hinton "for foundational discoveries and inventions that enable machine learning with artificial neural networks" - Nobel Prize Committee, Royal Swedish Academy of Sciences

The Nobel Prize decision for physics this year surprised many people. The connection between the work of Hopfield and Hinton and the field of physics may not be immediately obvious. Hinton, often referred to as the 'godfather of AI', developed the concept of Boltzmann machines based on Hopfield's ideas. While Hinton has made numerous contributions to the field of AI, the Nobel committee recognized this particular idea as being significant for the Nobel Prize in physics. On the other hand, Hopfield, a physicist by training, has made contributions spanning from physics to neuroscience to AI. In this article, I will explore Hopfield's idea - the Hopfield network - which led to the Nobel Prize in physics. I will demonstrate how he elegantly applied this idea from physics to the human brain, thereby advancing the field of neural networks and AI.

## Hopfield Networks

John Hopfield introduced the concept of Hopfield networks in a seminal paper titled “Neural Networks and Physical Systems with Emergent Collective Computational Abilities” in 1982.  
Hopfield networks were introduced as a model for associative memory or Content-addressable memory (CAM). The human brain is composed of complex networks of neurons. Hopfield networks, while a simplified mathematical abstraction of biological neural networks, provide a compelling model for understanding the principles behind associative memory. They demonstrate how interconnected units can store and retrieve patterns based on partial cues, much like how a familiar scent can trigger a vivid memory.  
Hopfield network has two main components-

1. Neurons: It is the processing unit and can be in the state 1 or -1
	$$x_i\in \{-1,1\}^d$$
	where *d* is the length of the patterns
2. Connections: neurons are connected to each other with synapses. These connections can be mathematical denotes by weights which determine the strength of interaction between neurons.


### Learning
But how does the brain learn these patterns? In other words, how does it store the associative memory? Hopfield used the idea of Hebbian learning . Neurons learn by adjusting the weights using the Hebbian learning rule, i.e. “neurons that fire together, wire together.”

Hebbian learning rule can be expressed as:
$$w_{ij} = x_i \; x_j$$

Where $w_{ij}$  is the weight of neuron i to neuron j. If $x_i ,x_j$  have same states, the weight increases otherwise it decreases.

Let us understand this by an example. Let us say we have 3 neurons and they have some pattern as shown in the figure below.



<p align="center">
 <img src="https://miro.medium.com/v2/resize:fit:640/format:webp/1*Fn1i9HpssbPMBdhAL4svJQ.png" alt="example" >
</p>

We can use the Hebbian rule to calculate the weight of each pair of neurons. Each pattern can be represented with a vector, and the entire weight matrix can be computed by taking the outer product.

$$W=  x_i x_i^{T}\;\;and \;w_{ii}=0$$

Now let us explore the general case, suppose we have N patterns- 
$$\{x^{(1)}....{x^{(N)}}\},\;\; x^{i} \in  ℝ^{N\times1}$$ 
We want a weight matrix W, which works for set of patterns/memories.
$$W_{ij}= \frac{1}{N}\sum^{N}_{s=i} x_{i}^{(s)} x^{(s)}_{j},\;\; W_{ii}=0$$
Here the $W_{ij}$ is known as the average coactivation between i,j.
 
Wright can also be expressed in the matrix form as -

$$W= \frac{1}{N}\sum^{N}_{s=i} \textbf{x}^{(s)} (\textbf{x}^{(s)})^{T}$$


Here the outer product $x_i x_i^T$ captures the correlations between all pairs of neurons within that specific pattern.

Hopfield networks have some interesting properties:
1.  Hopfield networks are **recurrent neural networks**. The output of a neuron can become the input to other neurons.
2. Hopfield networks perform more effectively when the stored patterns are **orthogonal** to each other.
3. The connection weights in a Hopfield network are **symmetric**, meaning that $w_{ij} = w_{ji}$ for any pair of neurons *i* and *j*. 
4. Usually self-connections $w_{ii} = 0$ are usually set to zero in Hopfield networks to prevent unstable dynamics and redundancy
5. Neurons in a Hopfield network can have either **binary (0 and 1)** or **bipolar (-1 and +1)** states, depending on the specific implementation.



### Retrieval

Once the patterns are stored, they can be retrieved from a cue or noise that partially matches the original pattern.

We can update the states in two ways:

1. **Synchronously** — all neurons update their states simultaneously at each time step, based on the states of all neurons from the previous time step.  
2. **Asynchronously** — neurons are updated one at a time, asynchronously. This means that a neuron’s state is updated based on the current states of all the other neurons, and then the next neuron is updated, and so on. Asynchronous updates lead to guaranteed stable states, hence we will use it here.

The update rule is as follows:

$$x_{i}(t+1) = sign(∑ (w_{ij} * x_{j}(t)) - \theta_i)$$

where-
- $s_j(t)$ is the state of neuron j at the current time step.
- $w_{ij}$: The weight of the connection between neuron i and neuron j.
- sign is  the sign function (returns +1 if the argument is positive, -1 if it's negative).
- $s_i(t+1)$: The state of neuron i at the next time step.
- $\theta_i$ is the bias term for neuron i

This update rule minimizes the Energy function:

$$E =-\frac{1}{2} \sum^{d}_{i=1}\sum^{d}_{j=1} x_i w_{ij}x_j -\sum^{d}_{i=1}\theta_ix_i\;\;, i\neq j$$

$$E =-\frac{1}{2} \sum_{i\neq j}\sum \textbf{X}^T W_{ij} \textbf{X} - \Theta \textbf{x}$$

It is also known as Hopfield energy. The update rule can be derived from Hopfield energy using gradient descent.  
We can iteratively update it until it converges — i.e. $x(t+1)=x(t)$

### Example

To demonstrate the learning process, we start with two images (patterns) as shown in the code below and then train them using Hopfield networks. Pattern 1 represents the letter "T" and Pattern 2 represents the letter "I."
Once the learning process is finished, the Hopfield network can retrieve the closest pattern to a given noisy pattern.

The code example can be found [here](https://github.com/adhikarinarayan/talks/blob/main/hopfield.ipynb).

## Connection with Physics
The energy function mentioned above is strikingly similar to the Ising model in statistical mechanics.  
In his seminal paper of 1982, Hopfield mentioned: “This case (symmetric case) is isomorphic with an Ising Model, and the V_ij(connection weight) provides the role of exchange coupling.”

In Physics, the Ising model is the simplest model for ferromagnetism. We consider a lattice, and each point in that lattice has a spin (+1 or -1).

The Hamiltonian for the Ising model can be written as: -

$$H = - \sum_{<ij>} J_{ij} \sigma_i \sigma_i + \sum_j h_j \sigma_j $$

where -
- $\sigma_i\in \{-1,1\}$ represents the spin of site i.
- J: The interaction strength between neighboring spins.
-  the first sum is over pairs of nearest-neighbor spins.
- h: The external magnetic field strength.

It is similar to the energy function of the Hopfield energy function. Spin can be thought of as analogous to the state of a neuron, and interaction strength is similar to the weight matrix, and so on.
## Significance of Hopfield networks

The Hopfield networks, while quite basic and with several limitations such as issues with overlapping patterns, have played a significant role in the advancement of AI and neural networks. They served as early models of associative memory and laid the foundation for later models such as Boltzmann machines. Hopfield networks were important in unsupervised learning because we don’t have outputs and hence have no loss function. Therefore, their energy minimization-based approaches are very useful.

## References:

1. [Hopfield network — Wikipedia](https://en.wikipedia.org/wiki/Hopfield_network#Hebbian_learning_rule_for_Hopfield_networks)
2. [Hopfield Networks — Notes on AI](https://notesonai.com/hopfield+networks)
3. [Hopfield Networks - YouTube](https://www.youtube.com/watch?v=81B-ESqgCjs&ab_channel=JeffOrchard)
4. [Hopfield Networks is All You Need](https://ml-jku.github.io/hopfield-layers/)
