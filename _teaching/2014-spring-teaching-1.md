---
title: "ERGM(Exponential Random Graph Models)"
collection: teaching
type: "Undergraduate course"
permalink: /teaching/2014-spring-teaching-1
venue: "University 1, Department"
date: 2026-01-02
location: "Seoul,Republic of KOREA"
---

This is a description of a teaching experience. You can use markdown like any other post.

================================================================================
EXPONENTIAL RANDOM GRAPH MODELS (ERGMS)
================================================================================

1. MATHEMATICAL FOUNDATION
--------------------------
* Definition: ERGMs are a statistical framework for modeling network data by 
  [cite_start]explicitly accounting for dependencies among edges[cite: 26].
* [cite_start]Probability Equation[cite: 30, 33]:
  P(Y=y) = (1 / kappa(theta)) * exp{ sum(theta_i * g_i(y)) }
  - [cite_start]g_i(y): Sufficient statistics (network features)[cite: 31].
  - [cite_start]theta_i: Corresponding parameters[cite: 32].
  - [cite_start]kappa(theta): The normalizing constant (sum of all possible networks)[cite: 33].


2. MARKOV RANDOM GRAPH MODELS & LIMITATIONS
-------------------------------------------
* Definition: Assumes conditional dependence only between edges sharing a 
  [cite_start]common vertex[cite: 40].
* [cite_start]Statistics: Typically counts k-stars and triangles[cite: 42].
* [cite_start]Key Limitations[cite: 50, 51, 52]:
  - Model Degeneracy: Placing probability mass on unrealistic graphs.
  - Poor Fit: Low-order terms often fail to capture real data structures.
  - Instability: Rapid changes in statistics relative to parameter changes.


3. STABLE STATISTICS (GEOMETRICALLY WEIGHTED)
---------------------------------------------
* GWD (Geometrically Weighted Degree): Controls weighting of vertex degrees 
  [cite_start]to provide numerical stability[cite: 58, 63].
* GWESP (Geometrically Weighted Edgewise Shared Partnership): Counts edges 
  [cite_start]in triangles while down-weighting higher-order configurations[cite: 70, 71].
* Nodal Effects: Includes Homophily (edges between similar nodes) and 
  [cite_start]Main effects (covariates)[cite: 74, 75].


4. ESTIMATION CHALLENGES & METHODS
----------------------------------
* The "Doubly-Intractable" Problem: Direct computation of kappa(theta) is 
  [cite_start]infeasible due to 2^(n choose 2) possible network combinations[cite: 82, 84].

[Comparison of Estimation Methods]
* MPLE (Maximum Pseudo Likelihood): 
  - [cite_start]Simplest and computationally efficient[cite: 108, 109].
  - [cite_start]Ignores dependence structures; generally poor performance[cite: 111, 112].
* MCMC MLE: 
  - [cite_start]Approximates kappa(theta) using Monte Carlo samples[cite: 116].
  - [cite_start]Theoretically sound but depends on the initial estimate[cite: 117].
* Exchange Algorithm: 
  - [cite_start]Uses auxiliary variables to cancel out the normalizing constant[cite: 120].
  - [cite_start]Requires "perfect sampling," which is often unavailable[cite: 122].


5. ADVANCED TOPICS
------------------
* DERGMs (Degeneracy-Restricted ERGMs): Restricts the model to graphs with 
  [cite_start]bounded degeneracy to ensure stability and reliable inference[cite: 129, 131].
* Finite Mixtures of ERGMs: Models heterogeneity in network ensembles by 
  [cite_start]assuming networks belong to latent classes[cite: 135].
* DPM-ERGMs: Dirichlet Process Mixtures that automatically infer the number 
  [cite_start]of clusters in a collection of networks[cite: 139, 140].
* Linear Programming (LP): Used to verify if MCMC likelihood approximations 
  [cite_start]are valid by checking the "Convex Hull Condition"[cite: 141, 144].


6. KEY FINDINGS
---------------
* Model degeneracy is a fundamental issue that no auxiliary variable MCMC 
  [cite_start]can completely avoid[cite: 124].
* For count-valued edges, MPLE is recommended for large-variance settings 
  [cite_start]due to its scalability[cite: 147].
* Goodness-of-Fit (GOF) is assessed by simulating networks from the fitted 
  [cite_start]model and comparing them to observed structural characteristics[cite: 126].

================================================================================
