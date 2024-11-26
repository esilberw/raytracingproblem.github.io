# The Ray Tracing Problem
Elliot SILBERWASSER, Emile MERIAN

### Abstract

The ray tracing problem is a decision problem defined as followed : given an environment of refractive and infractive complex 3D shapes called an optical system, we want to know if a ray projected from a starting coordinate in this environment will reach a destination coordinate. This project seeks to demonstrate that The ray tracing of three-dimensional optical systems consisting of quadratic reflective or refractive objects is undecidable, even if all the objects are presented by a system of rational quadratic inequalities.

## Introduction

To prove the undecidability of the ray tracing problem, we will focus on another known undecidable problem, the Membership problem. By reducing all instances of the membership problem into instances of the ray tracing problem, we will prove that not all instances of the ray tracing problem can be decided, and as such is undecidable.

## Preliminaries

We will now give some basic terminologies and definitions that will be useful to further our explanations. 

A reduction is a way to convert a problem into another such that : Let A, B two problems.

If the problem A can be reduced to the problem B, we can use the solution of the problem B to solve the
problem A.

This principle is very useful for showing the undecidability of a problem. To show that the problem B is
undecidable, we will show that problem A which is a problem known as undecidable can be reduced to
problem B. Therefore, the problem B is undecidable too, otherwise this contradicts the fact that problem
A is undecidable.
We can summarize the power of the reduction into two conclusions:
1. If there exists a reduction from the problem A to the problem B and we know that B is decidable,
then the problem A must be decidable
2. Inversely, if there exists a reduction from the problem A to the problem B and the problem A is known
undecidable the the problem B must me undecidable

## Problem definition

A problem can be defined as a language. Each problem instance can be encoded using a finite word w on
a finite alphabet Σ∗. Consequently, a language is an infinite set of finite words.

A decision problem is a problem where the answer is a binary yes or no. So, we decide the problem when
we can give an answer for any given input.

The question to answer for the Ray Tracing Problem is the following:
Given an optical system (namely, a finite set of reflective or refractive objects), a light ray’s
initial position and direction, and some fixed point p, does the ray eventually reach p?[1]
Deciding a decidable problem comes down to knowing whether a word w (≡ an instance of the problem)
belongs to the language L or not, where L represents the problem. It’s called the Membership Problem.
w ∈ L?
To answer at this question, we need to consider three cases:
1. w ∈ L, w is a positive instance of L ⊆ Σ∗.
2. w ∈ Σ∗ \ L, w is a negative instance ( /∈ L).
3. w is a finite words on Σ∗ which does not correspond to the encoding rules for any instances of the
problem, and therefore does not represent a valid instance of the problem considered.

### Turing Machine

A Turing Machine is a 7-tuple (Q, Σ, Γ, δ, q0, qaccept, qreject)
• Q is the finite set of control states.
• Σ is the input alphabet not containing the blank symbol of the language.
• Γ is the tape alphabet.
• δ : Q × Γ → Q × Γ is the transition function.
• q0 ∈ Q is the start state.
• qaccept ∈ Q is the accepting state.
• qreject ∈ Q is the rejecting state, where qaccept̸ = qreject

A basic Turing Machine is therefore a machine with a tape which will contain the word w (the problem
instance) to read, a reading head position and control states. The machine will move state depending on the
input read by the tape head and the transition function which will determine the state to reach depending
on the input.
When a Turing Machine stops in a state qaccept, then the word w ∈ L, otherwise, the word w /∈ L. It is even
sometimes possible for the Turing Machine to loop indefinitely on a word w.
Consequently, a Turing Machine can reject a word w in two cases:
1. If the terminal state is a qreject.
2. When the Turing Machine loop on w and therefore that the Turing Machine does not stop on the
input.
In this case, the Turing Machine is called a Turing-Recognizable language. It is the equivalent of saying that
the problem (≡ the language) is undecidable because we do not know how to find an algorithm that solves
all the instances of the problem in a finite number of steps has there is a possibility of the machine infinitely
looping.

### Ray Tracing

As mentioned above, an instance of the problem can be reduced to a word on a given alphabet. In our case,
the alphabet is binary and is composed of the symbols {0, 1}.
The overall vision of the problem can be seen as a starting input corresponding to an entry point of the
ray, which will then pass through the different reflective and refractive surfaces of the optical system. The
Turing Machine calculates after each passage through a surface, the exit position by the deviation caused
by the different surfaces.
In this way, the input will change on the tape depending on the modifications induced by the different
surfaces of the optical system.
Therefore, an instance of the problem is defined by two binary fractions U = 0.u0.u1.u2... and V =
0.v0.v1.v2.... These two words represent the coordinates (x, y) in decimal relative of a unit square.
We can apply two different operations on U and V.

1. LeftMove δ(q, c) = (q′, c′, L)
2. RightMove δ(q, c) = (q′, c′, R)
   
These two operations allow us to modify the encoding on the U and V words on the tape. The transformations
U′ and V′ induced by the transition functions are the following.

For the LeftMove operation, we have the following transformations [1]
U′ = 2∞∑i=1 ui/2i+1 = 2.(U − u0/2)
V′ = c′/2 + 1/2.∞∑i=0 vi/2i+1 = c′/2 + v/2

For the RightMove operation, we have the following transformations [1]
U′ = v0/2 + c′/4 + 1/2.∞∑i=1 ui/2i+1 = v0/2 + c′/4 + (U − u0/2)/2
V′ = 2∞∑i=1 vi/2i+1 = 2(V − v0/2)



## Proposed Solution

## Implementation

<iframe src="https://codesandbox.io/embed/d85szx?view=preview&expanddevtools=1"
     style="width:100%; height: 500px; border:0; border-radius: 4px; overflow:hidden;"
     title="Ray Tracing Problem Project"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

***

## Conclusion

## References
