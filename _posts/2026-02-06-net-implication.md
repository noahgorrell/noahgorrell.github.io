---
title: 'A Tidbit on Properties of Sequences'
date: 2026-02-06
permalink: /posts/2026/02/sequence-properties/
tags:
  - cool posts
  - category1
  - category2
---

This post is as much for me as it is for anyone else.

Order Theory
====

We begin in a very abstract setting: the world of preorders. Recall that a preorder is a binary relation \\(\leq \\) on a set \\(S\\), satisfying two properties:
* reflexivity: \\(a\leq a\\) for every \\(a\in S\\);
* transitivity: if \\(a\leq b\\) and \\(b\leq c\\) then \\(a\leq c\\), for all \\(a,b,c\in S\\).
A subset \\(R\subset S\\) is said to be *downwards-closed* if for every \\(a\in S\\) we have \\(\{b\in S: b\leq a\}\subset R\\). More generally, we will say that \\(R\\) is *locally downwards-closed* if for every \\(a\in S\\), there exists \\(a'\leq a\\) such that \\(\{b\in S: b\leq a'\}\subset R\\).

**Theorem:** Let \\(P\subset S\\) be downwards-closed, and let \\(R\subset S\\) be locally downwards-closed. Suppose that for every \\(x\in P\\), there exists \\(y\leq x\\) with \\(y\notin R\\). Then \\(P\cap R=\emptyset\\).
**Proof:** Suppose \\(x\in P\cap R\\). Since \\(R\\) is locally downwards-closed, choose \\(x'\in S\\) with \\(x'\leq x\\) and \\(\{y\in S : y\leq x'\}\subset R\\). Since \\(P\\) is downwards-closed, we also have \\(x'\in P\\), but by our assumption this implies that there exists \\(y\leq x'\\) with \\(y\notin R\\), a contradiction. QED.

This is a very simple statement, but because preorders appear so ubiquitously throughout mathematics, it has useful interpretations.

Sequences
===
Let \\(X\\) be a set. The set of sequences in \\(X\\), denoted \\(X^{\mathbb N}\\), can be given a preorder by setting \\((x_n)_{n\in\mathbb N}\leq (y_n)_{n\in\mathbb N}\\) if \\((x_n)\\) is a subsequence of \\((y_n)\\). In this setting, a subset \\(P\subset X^{\mathbb N}\\) is downwards-closed if it is invariant under taking subsequences; that is, if a sequence lies in \\(P\\), then each of its subsequences also lies in \\(P\\). Meanwhile, \\(P\\) is locally downwards-closed if the following property holds: for any sequence \\((x_n)_{n\in\mathbb N}\in P\\), there exists a subsequence \\((x_{n_k})_{k\in\mathbb N}\\), every subsequence of which also lies in \\(P\\). Let's consider some examples.

1. First, let \\(P\\) denote the set of sequences that are eventually constant. This is clearly downwards-closed and therefore locally downwards-closed. Its complement, the set of sequences that are *not* eventually constant, is not downwards-closed, nor locally downwards-closed. (Consider a sequence that alternates between two values.)
2. Next, given an element \\(x\in X\\), let \\(P\\) denote the set of sequences that are eventually equal to \\(x\\). This is also downwards-closed and therefore locally downwards-closed. Its complement, the set of sequences that are *not* eventually equal to \\(x\\), is not downwards-closed; consider a sequence that alternates between \\(x\\) and some other element of \\(X\\). However, it is locally downwards-closed; simply choose a subsequence whose range does not include \\(x\\).
3. More generally, given a subset \\(Y\subset X\\), the set of sequences that are eventually contained in \\(Y\\) is downwards-closed and therefore locally downwards-closed. Its complement is locally downwards-closed, but not downwards-closed, unless \\(Y=\emptyset\\) or \\(Y=X\\).
4. Given a subset \\(Y\subset X\\), let \\(P\\) denote the set of sequences \\((x_n)_{n\in\mathbb N}\\) such that the set \\(\{n\in\mathbb N : x_n\in Y\}\\) is infinite. This is not downwards-closed but is locally downwards-closed. Its complement *is* downwards-closed and therefore locally downwards-closed.

These ideas can be analogised to the setting of nets as well.

Now, if \\(X\\) is a topological space, recall that a sequence \\(x_n\\) in \\(X\\) is said to *converge* to \\(x\in X\\) if for every neighbourhood \\(U\\) of \\(x\\), \\(x_n\\) is eventually contained in \\(U\\). Given \\(x\in X\\), it is easy to see that the set of sequences converging to \\(x\\) is downwards-closed. (You can show this directly, but you can also see the set of sequences converging to \\(x\\) as an intersection of the sets described in 3 above.) Moreover, the set of sequences *not* converging to \\(x\\) is locally downwards-closed. Therefore, the theorem stated above specialises to the following result.

**Theorem:** Let \\(\tau_1\\) and \\(\tau_2\\) be two topologies on \\(X\\).[^top] Suppose that, whenever \\(x_n\to x\\) with respect to \\(\tau_1\\), there exists a subsequence \\((x_{n_k})_{k\in\mathbb N}\\) that converges to \\(x\\) with respect to \\(\tau_2\\). Then, \\(\tau_1\\) is a finer topology than \\(\tau_2\\).

[^top]: Strictly, we require these topologies to be locally second-countable, but this condition can be removed if we consider nets instead of sequences.

<!-- Consider a function \\(P : X^{\mathbb N} \to \{0,1\} \\). Interpreting 0 and 1 as boolean values, we can understand \\(P\\) as a proposition about sequences. Therefore, given a sequence \\((x_n)\in X^{\mathbb N}\\), we will abusively write \\(P((x_n))\\) to denote that \\(P((x_n))=1\\) and \\(\neg P((x_n))\\) to denote that \\(P((x_n))=0\\).

Given such a proposition \\(P\\), let \\(\bar P((x_n))\\) denote the proposition that \\(P((x_{n_k}))\\) holds for every subsequence \\((x_{n_k})\\) in \\((x_n)\\). We will say that \\(P\\) is *subinvariant* if \\(P\implies \bar P\\). In words, this says that if \\(P\\) holds for some sequence, then it also holds for every subsequence. We will say that \\(P\\) is *cosubinvariant* if \\(\overline{\neg\left(\overline{\neg P}\right)}\implies P\\). Unwrapping this statement and taking the contrapositive, this says that if \\(P\\) fails to hold for some sequence, then there exists a subsequence, *no subsequence of which* satisfies \\(P\\).

Note: neither subinvariance nor cosubinvariance imply one another, and a proposition can have both properties, as demonstrated by the following few examples. However, one useful, though uninteresting, fact is that if \\(P\\) is subinvariant, then \\(\neg P\\) is cosubinvariant.

Let's consider some examples. First, let \\(P((x_n))\\) denote the proposition that the sequence \\((x_n)\\) is eventually constant. Here, \\(P\\) is subinvariant: if the sequence \\((x_n)\\) is eventually constant, then any subsequence is eventually constant as well. However, it is *not* cosubinvariant, unless \\(X\\) (the codomain of our sequences) is empty or singleton. To see this, consider a sequence that alternates between two values.

For a second example, given a proper, non-empty subset \\(Y\subset X\\), let \\(P((x_n))\\) denote the proposition that infinitely many sequence values in \\((x_n)\\) lie in \\(Y\\). This is *not* subinvariant; to see this, consider a sequence that alternates between a point in \\(Y\\) and a point not in \\(Y\\). However, it is cosubinvariant; in fact, you can convince yourself that \\(\neg P\\) is subinvariant, and it follows immediately that \\(P\\) is cosubinvariant.

The motivating example for this post is [convergence in a topological space](https://math.stackexchange.com/a/504415/1322358). Suppose \\(X\\) is a topological space. Given \\(x\in X\\), let \\(P_x((x_n))\\) denote the proposition that \\(x_n\to x\\). Then the proposition \\(P_x\\) is both subinvariant and cosubinvariant.

Main Point
===
Suppose we have a subinvariant proposition \\(P:X^{\mathbb N}\to \{0,1\}\\) and a cosubinvariant proposition \\(Q:X^{\mathbb N}\to \{0,1\}\\).

**Theorem:** To prove that \\(P\implies Q\\), one only needs to prove the following proposition:
> If \\(P(x_n)\\) holds, then \\((x_n)\\) has a subsequence satisfying \\(Q\\).         (1)

**Proof:** Assume that (1) holds. By way of contradiction, assume there exists a sequence \\((x_n)\\) with \\(P((x_n))\\) and \\(\neg Q((x_n))\\). Since \\(Q\\) is cosubinvariant, there exists a subsequence \\((x_{n_k})\\), no subsequence of which satisfies \\(Q\\). However, since \\(P\\) is subinvariant, \\(P(x_{n_k})\\) holds. By our assumption, \\((x_{n_k})\\) has a subsequence satisfying \\(Q\\), a contradiction. QED.

One application of this theorem is the following: suppose the set \\(X\\) is imbued with two topologies, \\(\tau_1\\) and \\(\tau_2\\). (Technically, we require these topologies to be locally second-countable in order to work with sequences, but what we did above can easily be extended to nets in order to accomodate any topologies.) To prove that \\(\tau_1\\) is finer than \\(\tau_2\\), one only needs to establish the following proposition:
> If \\(x_n\to x\\) with respect to \\(\tau_1\\), then there exists a subsequence \\((x_{n_k})\\) that converges to \\(x\\) in \\(\tau_2\\). -->