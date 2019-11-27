---
layout: default
published: true
mathjax: true
---


My thesis research has been in rare events in nonlinear optics. This research combines techniques in nonlinear waves, wave propagation, stochastic simulation, and numerical optimization. In a past life I did research in nonlinear water waves, but the most fulfilling parts of my doctoral research have been in stochastic simulation. In particular, I've studied a mode-locked laser model and quantified error rates using importance sampling. 

## Importance Sampled Monte Carlo Integration
Monte Carlo is a numerical simulation technique for calculating integrals and assessing probabilities. It utilizes the fact that the *expected value* of a random quantity is calculated mathematically via an integral:


$$
I=\mathbb{E}_p[f(\mathbf{X})] = \int_{D} f(\mathbf{x})p(\mathbf{x})\,d\mathbf{x}.
$$


where $f$ is some function and $p$ is the probability distribution that gives rise to the random variable $\mathbf{X}$. Monte Carlo integration works to approximate $I$ by randomly sampling from $p$ and then averaging $f$. For instance, after drawing $N$ samples our approximation to $I$ is


$$
\hat{I}_N = \frac{1}{N}\sum_{l=1}^N f(\mathbf{X}_l).
$$

However, if we're interested in rare events, it may take an infeasible amount of samples in order to adequately refine the probability. *Importance sampling* can be used to draw samples from another probability distribution, $p^*$ (called a biasing distribution), which leads to the rare event of interest more frequently. Mathematically, this technique amounts to a simple tweak of the integral: 


$$
I = \int_{D} f(\mathbf{x})\frac{p(\mathbf{x})}{p^*(\mathbf{x})}p^*(\mathbf{x})\,d\mathbf{x}.
$$

The Monte Carlo average is then computed via

$$
\hat{I}_N = \frac{1}{N}\sum_{l=1}^N f(\mathbf{X}_l)\frac{p(\mathbf{X}_l)}{p^*(\mathbf{X}_l)}.
$$

where $f$ is now multiplied by the *likelihood ratio* of the biased noise $L(\mathbf{X}_l)=\frac{p(\mathbf{X}_l)}{p^*(\mathbf{X}_l)}$. 

This all might sound simple enough, but the most difficult part of importance sampling is the determination of the biasing distribution, which is usually accomplished through some kind of optimization. For instance, in my mode-locked laser research, I studied an *escape problem* where I was interested in the probability that a pulse of light would escape its bit-slot (or wander outside of the time allotted for its transmission) and cause a communication error. A number of stabilizing physical elements needed to be overcome for this to occur, so the error paths were found to be quite complicated. These paths, found using a combination of asymptotic, analytic, and numerical methods, sometimes involved a large number of oscillations.

<div class="center">
<video width=":100%" controls>
  <source src="/docs/Oscillations3.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 
</div>

For more on importance sampling please view my [tutorial repository]( https://github.com/natsan91/Importance_Sampling) on Github. 





