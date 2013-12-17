GP-SSM
======

Gaussian Process State-Space Models


Introduction
-----

This Matlab toolbox implements algorithms to learn (i.e. identify) state-space models of nonlinear dynamical systems based on Gaussian processes. There are a few advantages of the proposed approaches:

* No parametric form of the system dynamics needs to be given by the user. Assumptions about the kind of smoothness of the dynamics function are introduced via the choice of the covariance function (see chapter 4 in Rasmussen and Williams, Gaussian Processes for Machine Learning, 2006).

* Model complexity and fit is traded off automatically.

* Error bars on model predictions capture uncertainty due to scarce or ambiguous data.

In particular, this toolbox implements the algorithms of the two following papers:

[1] R. Frigola, F. Lindsten, T. B. Schön and C. E. Rasmussen. Bayesian Inference and Learning in Gaussian Process State-Space Models with Particle MCMC, in Neural Information Processing Systems (NIPS), 2013.
http://media.nips.cc/nipsbooks/nipspapers/paper_files/nips26/1449.pdf

[2] R. Frigola, F. Lindsten, T. B. Schön and C. E. Rasmussen. Identification of Gaussian Process State-Space Models with Particle Stochastic Approximation EM, 2013, submitted.


First Steps
-----

**IMPORTANT:**  The GP-SSM code requires the Gaussian Process for Machine Learning (GPML) toolbox which is freely available here:
http://www.gaussianprocess.org/gpml/code

1. You need to run two different startup.m files, first the one for the GPML toolbox and then the one in this toolbox (GP-SSM/startup.m).

2. Create a problem definition file. As an example, see GP-SSM/OneDimNonlinear/onedimnonlinearset.m which defines the problem of learning the 1-dimensional nonlinear system used in references [1] and [2].

3. Call learngpssm.m with the training data and the S structure containing the problem definition generated in the previous step.


Contributing
-----
Please feel free to fork this repo and modify it and improve it in any way that suits you. This version of the code emphasises modularity and clarity and can deal with multidimensional states. However, some features are not yet implemented, e.g.

* Sequential factorisation of the covariance matrices.
* Efficient use of sparse covariance functions, e.g. FIC.

