---
title: "The Exponential Mechanism as a Selection Kernel"
description: "How randomizing the selection step with an exponential mechanism turns post-selection inference into a one-dimensional tilted-Gaussian problem."
tags: [selective inference, exponential mechanism]
---

Many data-driven procedures end with a choice: a split in a tree, the top
candidate in a ranking, a policy from a library. The question we then want to
answer — what is the effect in the selected leaf, how good is the winner — is
only fixed *after* the data have been looked at. This note records the basic
construction behind my recent work: make that choice with a prespecified
randomized rule, and the resulting conditional inference stays tractable.

## The setting

Write $$D \sim P$$ for the data and $$Z = Z(D)$$ for the **data summary** used
to make the choice. The same $$Z$$ is used for every candidate and is never
redefined after selection. The candidates form a space $$(\mathcal S, \nu)$$
with **base measure** $$\nu$$, and a **utility** $$u(z, s)$$ scores candidate
$$s$$ on data $$z$$.

A deterministic rule reports $$\hat s(z) \in \arg\max_s u(z, s)$$. Instead we
draw the reported candidate $$S$$ from a **selection kernel** $$K(ds \mid z)$$
whose density with respect to $$\nu$$ is the **exponential mechanism**

$$
\kappa_\tau(s \mid z)
= \frac{\exp\{u(z,s)/\tau\}}{\int \exp\{u(z,s')/\tau\}\,\nu(ds')},
\qquad \tau > 0.
$$

With $$\nu$$ the counting measure on a finite set this is the softmax; as
$$\tau \downarrow 0$$ it concentrates on the maximizers of $$u(z,\cdot)$$. The
temperature $$\tau$$ therefore controls how far the reported candidate may
depart from the best one.

## Conditioning on the selection

Fix a candidate $$s$$ with target $$\theta_s$$ and an estimator $$T_s$$ with
$$\operatorname{Var}(T_s) = \sigma_s^2$$. Suppose $$(T_s, Z)$$ is jointly
Gaussian, exactly or as a reference approximation. Split $$Z$$ into the part
explained by $$T_s$$ and a residual,

$$
b_s = \frac{\operatorname{Cov}(Z, T_s)}{\sigma_s^2}, \qquad
R_s = Z - b_s T_s,
$$

so that $$R_s$$ is independent of $$T_s$$ and carries the nuisance information.
Conditioning on the realized selection $$\{S = s\}$$ and on $$R_s = r$$, Bayes'
rule gives the **selection-tilted Gaussian law**

$$
p(t \mid S = s, R_s = r) \;\propto\;
\phi_{\theta_s, \sigma_s^2}(t)\;\kappa_\tau(s \mid r + b_s t).
$$

The tilt is just the selection probability evaluated along the line
$$z(t) = r + b_s t$$. Its cumulative distribution function $$F_s(t; \theta \mid r)$$
is a **selective CDF pivot**: $$F_s(T_s; \theta_s \mid R_s)$$ is uniform given
$$S = s$$, and inverting it in $$\theta$$ gives an interval $$C_s$$ with

$$
P\{\theta_s \in C_s \mid S = s\} \ge 1 - \alpha .
$$

## Why the randomization matters

With a deterministic rule the tilt is an indicator of a selection event, and
the conditional law can be a Gaussian truncated to a tiny region, which
produces very long intervals. The exponential mechanism replaces the
indicator by a smooth, strictly positive weight that is available in closed
form up to its normalizer. The same recipe covers structured choices: for a
tree grown split by split, $$\kappa_\tau$$ becomes a product of stagewise
normalized split probabilities.

## Open questions

- Continuous candidate spaces (locations, peaks), where the normalizer is an
  integral rather than a sum.
- Choosing $$\tau$$, or a different kernel altogether, before seeing the data,
  to balance decision quality against the precision of $$C_s$$.
