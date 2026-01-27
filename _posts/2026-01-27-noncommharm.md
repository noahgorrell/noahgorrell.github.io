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

Classically, harmonic analysis is essentially concerned with two types of functions: functions defined on Euclidean space \\(\mathbb R^n\\), and functions defined on a cube \\([0,1]^n\\). (Equivalently, one can view the latter as the study of *periodic* functions on \\(\mathbb R^n\\).) For an integrable function \\(f:\mathbb R^n \to \mathbb R\\), we define its *Fourier transform* \\(\hat f: \mathbb R^n\to\mathbb R\\) by \\[\hat f(\xi) = \int_{\mathbb R^n} f(x)e^{-2\pi i x\cdot \xi}\, dx.\\]
