---
layout: default
published: true
mathjax: true
---


My thesis research has been in rare events in nonlinear optics. This research combines techniques in nonlinear waves, wave propagation, stochastic simulation, and numerical optimization. In a past life I did research in nonlinear water waves, but the most fulfilling parts of my doctoral research have been in stochastic simulation. In particular, I've studied a mode-locked laser model and quantified error rates using importance sampling. 

#### Importance Sampled Monte Carlo Integration
Monte Carlo integration allows one to numerically approximate an integral by drawing a large number of random samples from a probability distribution. For our purposes, consider an integral of the form


$$
I = \int_{D} f(\mathbf{x})p(\mathbf{x})\,d\mathbf{x} 
$$


where the integral is over some region $D$ in $n$-dimensional space and $f$ and $p$ are functions on that space. Additionally, we require that $p$ is a probability density function (PDF), meaning essentially that it is non-negative and integrates to 1 over $D$. Monte Carlo integration works to approximate $I$ by randomly sampling from $p$ and then averaging $f$. For instance, after drawing $N$ samples our approximation to $I$ is


$$
\hat{I}_N = \frac{1}{N}\sum_{l=1}^N f(\mathbf{X}_l)
$$


where each $X_l$ is a random variable drawn from the distribution $p$.  This works as the integral $I$ is also an expectation integral. As such, Monte Carlo integration is a useful technique for computing integrals or assessing probabilistic outcomes of random processes.

However, if we're interested in rare events, it may take an infeasible amount of samples in order to adequately refine the probability.


$$
I = \int_{D} f(\mathbf{x})\frac{p(\mathbf{x})}{p^*(\mathbf{x})}p^*(\mathbf{x})\,d\mathbf{x}.
$$

$$
\hat{I}_N = \frac{1}{N}\sum_{l=1}^N f(\mathbf{X}_l)\frac{p(\mathbf{X}_l)}{p^*(\mathbf{X}_l)}.
$$

$$
L(\mathbf{X}_l)=\frac{p(\mathbf{X}_l)}{p^*(\mathbf{X}_l)}
$$





