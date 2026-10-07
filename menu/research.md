---
layout: page
cards: true
title: Research
permalink: /research
---

I develop **inference-aware adaptive algorithms**: data-driven procedures whose decisions are explicitly randomized, conditionally auditable, and designed so that useful uncertainty quantification survives them. A method chooses something from the data — variables, a tree, the leading candidates, a policy — and the scientific question is then asked about what was chosen. My work builds the randomization into the selection rule itself and conditions on its output, so that the chosen question can still be answered with valid confidence intervals and tests.

# Research Directions

1. **Inference after randomized selection.** Conditional inference for selected effects in longitudinal causal models, for the leaves of regression and classification trees, and for winners among many candidates — with the exponential mechanism as a common, tractable selection rule.

2. **Continuous and structured selections.** Extending these guarantees beyond finite candidate sets, to selected locations, peaks, change-points and anomalous regions.

3. **Designing the randomization.** Choosing the selection rule before the analysis, to balance the quality of the decision against the precision of the inference that follows it.

4. **Selected policies and learned control.** Inference for the value of a policy or controller that was chosen using the same logged data it is evaluated on.

5. **Reliability of learning systems.** What a learning pipeline must preserve to remain identifiable: classification under unknown label noise, and models retrained on contaminated or self-generated data.

Longer write-ups are in my [research notes]({{ site.github.url }}/notes).

# Publications & Preprints

{% include publications.html %}

# Software

1. [SI-CART](https://github.com/BakshiSoham/SI-CART) — selective inference with randomized regression trees.

2. [LLMCollapse](https://github.com/BakshiSoham/LLMCollapse) — simulations for iterative training on contaminated sources.
{: .refs}

# Selected Talks

1. Randomized Trees with Conditional Inference. *Joint Statistical Meetings (JSM)*, Boston, MA, USA, 2026. [Slides]({{ site.github.url }}/assets/file/SIRTreesJSM26.pdf).

2. Selective Inference for Time-Varying Moderated Effects. *Statistical Analysis of Multi-Outcome Data (SAM)*, Salzburg, Austria, 2024. [Slides]({{ site.github.url }}/assets/file/SIMRTSlides.pdf).

3. Non-Identifiability of Bayes Classifier. *Joint Statistical Meetings (JSM)*, Toronto, Canada, 2023. [Slides]({{ site.github.url }}/assets/file/slides_jsm.pdf).

4. Geometry in Statistics. *Math Club*, Indian Statistical Institute, Bengaluru Centre, India, 2022. [Slides]({{ site.github.url }}/assets/file/slides_statgeo.pdf).

5. Hopf–Rinow Theorem and Geodesic Completeness. *Visiting Students Research Program (VSRP)*, School of Mathematics, TIFR, India, 2021. [Slides]({{ site.github.url }}/assets/file/VSRP.pdf).
{: .refs}

# Awards & Fellowships

1. Rackham Conference Travel Grant, University of Michigan, 2026.

2. Rackham International Travel Grant, University of Michigan, 2023–2024.

3. Visiting Students Research Program, selected with honorarium, School of Mathematics, Tata Institute of Fundamental Research, Mumbai, India, 2021.

4. Summer Research Fellowship Programme (offered), Indian Academy of Sciences, Indian National Science Academy and National Academy of Sciences, India, 2021.

5. Regional Mathematical Olympiad qualifier and participant, Indian National Mathematical Olympiad Training Camp, Indian Statistical Institute, Kolkata, India, 2018–2019.
{: .refs}

# Service

1. Reviewer, *International Conference on Machine Learning (ICML)*, 2026.

2. Reviewer, *Journal of the Royal Statistical Society: Series B*, 2026.

3. Core Organizing Committee member, *Michigan Student Symposium for Interdisciplinary Statistical Sciences (MSSISS)*, University of Michigan.

4. Member, Institute of Mathematical Statistics (IMS) and American Statistical Association (ASA).
{: .refs}
