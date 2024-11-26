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
We can summary the powerful of the reduction into two conclusions:
1. If there exists a reduction from the problem A to the problem B and we know that B is decidable,
then the problem A must be decidable
2. Inversely, if there exists a reduction from the problem A to the problem B and the problem A is known
undecidable the the problem B must me undecidable

## Problem definition

### Ray Tracing

### Turing Machine

## Proposed Solution

## Implementation

<iframe src="https://d85szx.csb.app/"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="Ray Tracing Problem Project"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

***

## Conclusion

## References
