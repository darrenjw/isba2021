---
title: "A compositional approach to Bayesian computation"
subtitle: "ISBA 2021 virtual world meeting"
author: "Darren Wilkinson"
date: "darrenjw.github.io"
institute: "Newcastle University, UK"
output: beamer_presentation
---


## Background

* For non-trivial problems, Bayesian computation typically relies on computationally intensive methods, such as MCMC, SMC or ABC
* These often require a custom implementation in some programming language
* All of the languages commonly used are very old, dating back to the dawn of the computing age, and quite unsuitable for scalable and efficient Bayesian computation
* Interpreted dynamic languages such as R, Python and Matlab are far too slow, among many other things
* Languages such as C, C++, Java and Fortran are much faster, but are also very poorly suited to the development of efficient, well-tested, scalable code, able to take advantage of modern computing hardware


## Functional programming

* FP languages emphasise the use of *immutable* data, *pure, referentially transparent functions*, and *higher order functions*
* FP languages more naturally support composition of models, data and computation than imperative languages, leading to more scalable and testable software
* Statically typed FP languages (such as Haskell and Scala) correspond closely to the *simply-typed lambda calculus* which is one of the canonical examples of a *Cartesian closed category* (CCC)
* This connection between typed FP languages and CCCs enables the borrowing of ideas from category theory into FP
* Category theory concepts such as *functors*, *monads* and *comonads* are useful for simplifying code that would otherwise be somewhat cumbersome to express in pure FP languages

## Concurrency, parallelism, distribution, state

* Modern computing platforms feature processors with many cores, and possibly many such processors - parallel programming is required to properly exploit this
* Most of the notorious difficulties associated with parallel programming revolve around *shared mutable state*
* In pure FP, state is not mutable, so there is no mutable state, shared or otherwise
* Consequently, most of the difficulties typically associated with parallel and concurrent programming simply don't exist in FP - parallelism in FP is so easy and natural that it is sometimes completely automatic
* This natural scalability of FP languages is one reason for their recent resurgence

## Bayesian computation

* *map-reduce* operations on *functorial* data collections can trivially parallelise (and distribute):
    * Likelihood evaluations for big data
	* ABC algorithms
	* SMC particle propagation, re-weighting and re-sampling
* Gibbs sampling algorithms can be implemented as *cobind* operations on an appropriately coloured (parallel) *comonadic* conditional independence graph
* *Probabilistic programming languages* (PPLs) can be implemented as embedded domain specific languages (DSLs) trivially using *for/do* syntax for *monadic composition* in conjunction with *probability monads*
* Automatic differentiation (AD) for compute graphs is particularly natural in functional languages, facilitating gradient-based algorithms such as MALA, HMC and PDMP


## Further information

[`github.com/darrenjw/isba2021`](https://github.com/darrenjw/isba2021)

![QR code](../Talk/qr-code-s.png)
