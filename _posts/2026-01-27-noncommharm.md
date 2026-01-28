---
title: 'Non-commutative harmonic analysis'
date: 2026-01-27
permalink: /posts/2026/01/non-commutative-harmonic-analysis/
tags:
  - operator-theory
  - expository
---

This post aims to give a brief introduction to the branch of operator theory known as *non-commutative harmonic analysis*. The objective of this area is to generalise ideas from Fourier analysis to arbitrary locally compact groups. To understand this, we will first need to talk about classical Fourier analysis and then discuss an intermediate area called *abstract harmonic analysis*.

Classical Fourier Analysis
=====

There are many excellent introductions to classical Fourier analysis. If you are familiar with any of them, feel free to skip this section. Otherwise, I will try my best not to take too long.

Classically, harmonic analysis is essentially concerned with two types of functions: functions defined on Euclidean space \\(\mathbb R^n\\), and functions defined on a torus \\(\mathbf T^n\\), where \\(\mathbf T\\) denotes the unit circle in the complex plane. (Parametrising the circle by the interval \\([0,1)\\), one can view the latter as the study of *periodic* functions on \\(\mathbb R^n\\).) For simplicity, we will consider only the \\(n=1\\) case. For a function[^fn] \\(f:\mathbb R \to \mathbb R\\), we define its *Fourier transform* \\(\hat f: \mathbb R\to\mathbb R\\) by \\[\hat f(\xi) = \int_{\mathbb R} f(x)e^{-2\pi i x\xi}\, dx.\\]

[^fn]: Strictly speaking, the integral expression for \\(\hat f\\) may not be well-defined. We can fix this issue by imposing the conditions that \\(f\\) is continuous and compactly supported, or else \\(f\in L^1(\mathbb R)\\), the space of integrable functions on \\(\mathbb R\\) (up to almost everywhere equivalence). The same kind of condition must be assumed for functions on an interval as well.

For a function \\(f:\mathbf T\to \mathbb R\\), we define its *Fourier series* \\(\hat f: \mathbb Z\to\mathbb R\\) by
\\[\hat f(k)=\int_{\mathbf T} f(\omega)\omega^k\,d\sigma(\omega),\\] where \\(\sigma\\) is the surface measure on the sphere. This is, in an important sense, the analogue of the Fourier transform for functions defined on the circle.

Let us make some observations about these spaces. First, \\(\mathbb R\\) and \\(\mathbf T\\) are both abelian groups: the real line has its additive group structure, while the unit circle is a subgroup of the multiplicative group \\(\mathbb C\setminus\{0\}\\). Second, both of these spaces come equipped with a "nice" topology: the Euclidean metric on \\(\mathbb R\\) is very nice, and the circle inherits the 2-dimensional Euclidean metric. (In particular, both these spaces are [locally compact](https://en.wikipedia.org/wiki/Locally_compact_space#weakly_locally_compact) and Hausdorff.) Thirdly, these topologies "respect" the group structures, in the sense that the group operation and inverse map are continuous with respect to these topologies.

A Special Case of Pontryagin Duality
-----
Let us consider the integrands in the definitions of the Fourier transform and Fourier series.

**Exercise:** Show that the functions \\(x\mapsto e^{-2\pi i x\xi}\\), for some \\(\xi\in\mathbb R\\), are exactly the continuous group homomorphisms from \\(\mathbb R\\) to \\(\mathbf T\\).

We write \\(\hat{\mathbb R}\\) for the set of continuous group homomorphisms from \\(\mathbb R\\) to \\(\mathbf T\\). The preceding exercise says that the elements of \\(\hat{\mathbb R}\\) can be parametrised by the real numbers.

**Exercise:** Show that \\(\hat{\mathbb R}\\) is a group under pointwise multiplication, and the identification \\(\hat{\mathbb R}\cong \mathbb R\\) is a group isomorphism.

Therefore, given an integrable function $f:\mathbb R\to \mathbb R$, we can think of the Fourier transform $\hat f$ as a function defined on $\hat{\mathbb R}$.

Similarly, the functions \\(\omega\mapsto \omega^k\\), for some \\(k\in \mathbb Z\\), are exactly the continuous group homomorphisms from \\(\mathbf T\\) to itself. Writing $\hat T$ for this set of homomorphisms, we again see that $\hat T$ is a group under pointwise multiplication and is isomorphic to $\mathbb Z$.

Abstract Harmonic Analysis
=====
Let \\(G\\) be a locally compact abelian group. (That is, \\(G\\) is a group, equipped with a locally compact Hausdorff topology that respects the group structure.)