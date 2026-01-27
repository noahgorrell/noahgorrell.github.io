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

Classically, harmonic analysis is essentially concerned with two types of functions: functions defined on Euclidean space \\(\mathbb R^n\\), and functions defined on a cube \\([0,1)^n\\). (Equivalently, one can view the latter as the study of *periodic* functions on \\(\mathbb R^n\\).) For simplicity, we will consider only the \\(n=1\\) case. For a function[^fn] \\(f:\mathbb R \to \mathbb R\\), we define its *Fourier transform* \\(\hat f: \mathbb R\to\mathbb R\\) by \\[\hat f(\xi) = \int_{\mathbb R} f(x)e^{-2\pi i x\xi}\, dx.\\]

[^fn]: Strictly speaking, the integral expression for \\(\hat f\\) may not be well-defined. We can fix this issue by imposing the conditions that \\(f\\) is continuous and compactly supported, or else \\(f\in L^1(\mathbb R)\\), the space of integrable functions on \\(\mathbb R\\) (up to almost everywhere equivalence). The same kind of condition must be assumed for functions on an interval as well.

For a function \\(f:[0,1)\to \R\\), we define its *Fourier series* \\((f_k)_{k\in\mathbb Z}\\) by
\\[f_k=\int_0^1 f(x)e^{-2\pi i kx}\,dx.\\]
This is, in an important sense, the analogue of the Fourier transform for functions defined on the interval. Soon, it will actually make more sense to consider functions defined on the circle \\(S^1\\), rather than the interval, but it is clear that these are the same thing.

Let us make some observations about these spaces. First, \\(\mathbb R\\) and \\([0,1)\\) are both abelian groups: the real line has its additive group structure, while the interval has the group structure of addition ''modulo 1''. Second, both of these spaces come equipped with a topology: the real line has the Euclidean metric, while the circle \\(S^1\\) inherits its topology from \\(\mathbb R^2\\). Thirdly, the group structure and the topology interact "nicely". (I will leave this notion vague here.) In particular, both the real line and the circle are examples of *locally compact abelian groups*. This leads us to our first abstraction of harmonic analysis.

Abstract Harmonic Analysis
=====