---
title: "Notation for Randomized Selective Inference"
description: "The notation I use across papers on inference after randomized selection, and the literature each term is borrowed from."
tags: [notation, selective inference]
---

The papers on randomized selection draw on selective inference, differential
privacy and information theory, and each field has its own names for the same
objects. This note fixes one convention and records where each term comes from.

## Core objects

| Concept | Term | Symbol | Borrowed from |
|---|---|---|---|
| Data and law | data, law | $$D \sim P,\ P \in \mathcal P$$ | standard |
| Statistic used to select | data summary | $$Z = Z(D) \in \mathcal Z$$ | — |
| What can be chosen | candidate space; selected candidate | $$(\mathcal S, \nu);\ S$$ | McSherry–Talwar |
| Randomized selection rule | selection kernel | $$K(ds \mid z)$$ | DP mechanism; channel |
| Its density | selection probability / density | $$\kappa(s \mid z)$$ | Tian–Taylor |
| Utility | utility | $$u(z, s)$$ | McSherry–Talwar |
| Main family | exponential mechanism | $$\kappa_\tau(s \mid z) \propto e^{u(z,s)/\tau}$$ | McSherry–Talwar |
| Scale | temperature | $$\tau > 0$$ | — |
| Non-randomized rule | deterministic selection | $$\hat s(z) \in \arg\max_s u(z,s)$$ | Lee et al. |
| Target | target; target statistic | $$\theta_s;\ T_s,\ \sigma_s^2$$ | Fithian–Sun–Taylor |
| Residual | regression coefficient; residual | $$b_s;\ R_s = Z - b_s T_s$$ | Lee et al. |
| Pivot | selective CDF pivot | $$F_s(t; \theta \mid r)$$ | Lee et al. |

## Guarantees

- **Selective coverage:** $$P\{\theta_s \in C_s \mid S = s\} \ge 1 - \alpha$$,
  as opposed to the unconditional $$P\{\theta_S \in C_S\} \ge 1 - \alpha$$.
- **Selective type I error:** $$E[\phi_s \mid S = s] \le \alpha$$ for every law
  in the selected null.
- A *selection event* $$\{\hat s(Z) = s\}$$ only makes sense for deterministic
  rules; for randomized rules I write "conditioning on the realized selection
  $$\{S = s\}$$".

## Terms I avoid, and why

| Avoid | Use instead | Reason |
|---|---|---|
| channel | selection kernel | kept for information-theoretic remarks |
| Gibbs channel / kernel | exponential mechanism | kept only for the Gibbs variational principle |
| reference measure | base measure | "reference" is reserved for the Gaussian reference model |
| propensity | conditional selection probability | propensity belongs to the behaviour policy |
| score | utility | score is kept for influence functions |
| $$k$$ for selection probability | $$\kappa$$ | $$k$$ is reserved for top-$$k$$ |
| $$\omega$$ | kernel-indexed notation | $$\omega$$ is Tian–Taylor's additive randomization |

## Sources

- W. Fithian, D. Sun and J. Taylor. [Optimal inference after model selection](https://arxiv.org/abs/1410.2597).
- J. D. Lee, D. L. Sun, Y. Sun and J. E. Taylor. [Exact post-selection inference, with application to the lasso](https://arxiv.org/abs/1311.6238). *Annals of Statistics*, 2016.
- X. Tian and J. Taylor. [Selective inference with a randomized response](https://doi.org/10.1214/17-AOS1564). *Annals of Statistics*, 2018.
- F. McSherry and K. Talwar. Mechanism design via differential privacy. *FOCS*, 2007.
