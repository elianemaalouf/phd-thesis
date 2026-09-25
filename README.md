# Contributions to data-driven Bayesian solutions to inverse problems: from classical multivariate statistics to modern generative neural networks
 
PhD thesis in Computer Science (Computational Statistics), University of Neuchâtel, Switzerland.
Defended on 10 June 2026.
 
**Author:** Eliane Maalouf

**Co-Supervisors:** David Ginsbourger (Univ. Bern), Kilian Stoffel (Univ. Neuchâtel)

**Reviewers:** Paul Cotofrei (Univ. Neuchâtel), Fabrice Gamboa (Univ. Toulouse), Jo Eidsvik (Norwegian Univ. of Science and Technology)
 
## Abstract
Inverse problems, inferring hidden causes from observed effects, are often ill-posed in that
solutions may be non-unique and unstable. Bayesian inference offers a principled way to
quantify this uncertainty through the posterior distribution, but in high dimensions it is
frequently impractical: exploring the posterior depends on knowing the likelihood function,
typically requiring as many calls to forward models, which computational costs can
be limiting. This thesis develops two data-driven methodologies that shift this computational
burden to an offline learning stage using existing synthetic input-output datasets
so that inference can typically be carried out without repeated forward-solver evaluations,
while allowing limited forward calls when needed for tuning, calibration, or diagnostics.
The first contribution introduces a probabilistic inversion framework built on Regularized
Canonical Correlation Analysis (RCCA). Propagating Gaussian input and noise
priors through RCCA transformations and correlations yields closed-form Gaussian posteriors
in the canonical space, retaining components typically discarded, and in the original
input space. For linear forward models in a saturated dimension reduction regime, this
posterior matches the analytical Bayesian solution (with plug-in covariance estimates).
Tunable regularization makes the method robust to unknown noise variance, and we provide
empirical guidance for selecting its parameters.
The second contribution is FastABC, a likelihood-free simulation based inference
method. FastABC uses a joint Sinkhorn Auto-Encoder (jSAE) to learn a low-dimensional
latent representation of the joint input-output relationship, effectively replacing the forward
solver with a learned surrogate at inference time. Posterior approximation is then
performed with sequential Approximate Bayesian Computation (ABC) by sampling in
the latent space via Subset Simulation (SuS), enabling amortized inference without an
explicit likelihood or a parametric noise model.

Across both contributions, we emphasize rigorous diagnostics and evaluation throughout
method development. Beyond pointwise error measures, we employ proper scoring
rules tailored to multivariate probabilistic predictions. We validate the proposed methods
on geophysical travel-time tomography in both linear and slightly nonlinear settings, and
we additionally evaluate FastABC on conditional image generation. Results illustrate
robust behavior across the tested noise levels and degrees of nonlinearity in these tests,
and demonstrate how modern generative neural networks as well as multivariate statistics
can make Bayesian inference for inverse problems feasible for complex high-dimensional
problems.
 
## Contents
 
- `Maalouf_PhD_thesis_2026.zip` — containing full pdf manuscript file
 
## Code
 
The two methodologies developed in the thesis are implemented in separate repositories:
 
- [LRCCA_inversion](https://github.com/elianemaalouf/LRCCA_inversion) — Bayesian inversion based on regularized canonical correlation analysis
- [FastABC_inversion](https://github.com/elianemaalouf/FastABC_inversion) — simulation-based inference combining multimodal generative neural networks with subset simulation
 
## Related publications
 
- Maalouf E, Ginsbourger D, Linde N. Fast ABC with joint generative modelling and subset simulation. *LOD 2021*, LNCS 13163, Springer, 2022. https://doi.org/10.1007/978-3-030-95467-3_30
- Maalouf E, Ginsbourger D, Linde N. Approximate Bayesian geophysical inversion using generative modeling and subset simulation. *NeurIPS 2020 Workshop on Machine Learning and the Physical Sciences*.
 
## Citation
 
Maalouf E. *Contributions to data-driven Bayesian solutions to inverse problems: from classical multivariate statistics to modern generative neural networks.* PhD thesis, University of Neuchâtel, 2026.
 
## License
 
© Eliane Maalouf, 2026. All rights reserved. 
