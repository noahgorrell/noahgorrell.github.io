---
title: 'A Tidbit on Properties of Sequences'
date: 2026-02-05
permalink: /posts/2026/02/sequence-properties/
tags:
  - cool posts
  - category1
  - category2
---

Introductions
====

Let \\(X\\) be a set, and let \\(X^{\mathbb N}\\) denote the set of sequences in \\(X\\).

Consider a function \\(P : X^{\mathbb N} \to \{0,1\} \\). Interpreting 0 and 1 as boolean values, we can understand \\(P\\) as a proposition about sequences. Therefore, given a sequence \\((x_n)\in X^{\mathbb N}\\), we will abusively write \\(P((x_n))\\) to denote that \\(P((x_n))=1\\) and \\(\neg P((x_n))\\) to denote that \\(P((x_n))=0\\).

Given such a proposition \\(P\\), let \\(\bar P((x_n))\\) denote the proposition that \\(P((x_{n_k}))\\) holds for every subsequence \\((x_{n_k})\\) in \\((x_n)\\). We will say that \\(P\\) is *subinvariant* if \\(P\implies \bar P\\). In words, this says that if \\(P\\) holds for some sequence, then it also holds for every subsequence.Additionally, we will say that \\(P\\) is *cosubinvariant* if \\(\overline{\neg\left(\overline{\neg P}\right)}\implies P\\). Unwrapping this statement and taking the contrapositive, this says that if \\(P\\) fails to hold for some sequence, then there exists a subsequence, *no subsequence of which* satisfies \\(P\\).

Note: neither subinvariance nor cosubinvariance imply one another, and a proposition can have both properties, as demonstrated by the following few examples. However, one useful, though uninteresting, fact is that if \\(P\\) is subinvariant, then \\(\neg P\\) is cosubinvariant.

Let's consider some examples. First, let \\(P((x_n))\\) denote the proposition that the sequence \\((x_n)\\) is eventually constant. Here, \\(P\\) is subinvariant: if the sequence \\((x_n)\\) is eventually constant, then any subsequence is eventually constant as well. However, it is *not* cosubinvariant, unless \\(X\\) (the codomain of our sequences) is empty or singleton. To see this, consider a sequence that alternates between two values.

For a second example, given a proper, non-empty subset \\(Y\subset X\\), let \\(P((x_n))\\) denote the proposition that infinitely many sequence values in \\((x_n)\\) lie in \\(Y\\). This is *not* subinvariant; to see this, consider a sequence that alternates between a point in \\(Y\\) and a point not in \\(Y\\). However, it is cosubinvariant; in fact, you can convince yourself that \\(\neg P\\) is subinvariant, and it follows immediately that \\(P\\) is cosubinvariant.

The motivating example for this post is [convergence in a topological space](https://math.stackexchange.com/a/504415/1322358). Suppose \\(X\\) is a topological space. Given \\(x\in X\\), let \\(P_x((x_n))\\) denote the proposition that \\(x_n\to x\\). Then the proposition \\(P_x\\) is both subinvariant and cosubinvariant.

Main Point
===
Suppose we have a subinvariant proposition \\(P:X^{\mathbb N}\to \{0,1\}\\) and a cosubinvariant proposition \\(Q:X^{\mathbb N}\to \{0,1\}\).

**Theorem:** If \\(P\implies \neg\left(\overline{\neg Q}\right)\\), then \\(P\implies Q\\). In words, to prove that \\(P\implies Q\\), one only needs to prove the following proposition:
> If \\(P(x_n)\\) holds, then \\((x_n)\\) has a subsequence satisfying \\(Q\\).         (1)
**Proof:** Assume that (1) holds. By way of contradiction, assume there exists a sequence \\((x_n)\\) with \\(P(x_n)\\) and \\(\neg Q(x_n)\\). Since \\(Q\\) is cosubinvariant, there exists a subsequence \\((x_{n_k})\\), no subsequence of which satisfies \\(Q\\). However, since \\(P\\) is subinvariant, \\(P(x_{n_k})\\) holds. By our assumption, \\((x_{n_k})\\) has a subsequence satisfying \\(Q\\), a contradiction. QED.