# Poisson Random Variable
I have written a much more detailed introduction to Poisson random variable [here](https://docs.google.com/file/d/0B3_JVAzZH1m9NmJBdU02TVRtaXc/edit?usp=sharing) in my [blog](http://schwannden.wix.com/rigor#!math/ck0q).

**Definition** We say a discrete r.v $\mathbb{X}$ is a Poisson r.v with parameters $\lambda$, denoted $\mathbb{X} \sim poisson(\lambda)$, if
$$
 \mathbb{X} \sim p(n) =
  \begin{cases}
   \frac{\lambda^n}{n!}e^{-\lambda} & \text{if } n \in 0, 1, 2, 3... \\
   0       & \text{otherwise}
  \end{cases}
$$

**Property** If $$\mathbb{X} \sim posson(\lambda)$$, then $$\mu = \sigma^2 = \lambda$$

**Proof 1** By definition
$$\mathbb{E}[\mathbb{X}] = \sum_{n=0}^\infty n\frac{\lambda^n}{n!}e^{-\lambda} = \lambda \sum_{n=1}^\infty \frac{\lambda^{n-1}}{(n-1)!}e^{-\lambda} = \lambda$$
$$\mathbb{E}[\mathbb{X}^2] = \sum_{n=0}^\infty n^2\frac{\lambda^n}{n!}e^{-\lambda} = \lambda \sum_{n=1}^\infty n  \frac{\lambda^{n-1}}{(n-1)!}e^{-\lambda} =  \lambda \sum_{n=0}^\infty (n+1)  \frac{\lambda^{n}}{n!}e^{-\lambda} = \lambda (\mathbb{E}[\mathbb{X}] + 1)$$
so $$var(\mathbb{X}) = \mathbb{E}[\mathbb{X}^2] - (\mathbb{E}[\mathbb{X}])^2 = \lambda$$

**Proof 2** By moment generating function

First lets check if it is eligible to apply moment generating function.

(a) 
$$\frac{\mathrm{d}}{\mathrm{d}t} f(n)e^{nt} = \frac{\lambda^n}{(n-1)!}e^{-\lambda}e^{nt}$$
$$\sum_{n=1}^\infty \frac{\lambda^n}{(n-1)!}e^{-\lambda}e^{nt} = \lambda e^{t-\lambda} \sum_{n=0}^\infty \frac{(\lambda e^t)^n}{n!} = \lambda e^{\lambda e^t + t - \lambda}$$

This convergence is definitely uniform for some closed interval containing $$0$$ (In fact, this convergence is uniform for all closed interval, see appendix for uniform convergence property on power series).

(b) $$\sum f(n)e^{nt} = \sum_{n=0}^\infty e^{nt}  \frac{\lambda^n}{n!}e^{-\lambda} = e^{-\lambda} \sum_{n=0}^\infty \frac{ (\lambda e^t)^n}{n!} = e^{\lambda (e^t - 1)}$$ converges on all points

Since (a), (b) hold, $$\mu = M_X'(0)$. $M_X(t) = e^{\lambda (e^t - 1)}$$ as (b) already showed, so the mean
$$ \mu = M_x'(0) = \lambda e^t e^{\lambda (e^t - 1)} |_{t=0} = \lambda $$
and variance
$$\sigma^2 = \mathbb{E}[\mathbb{X}^2] - \mathbb{E}[\mathbb{X}]^2 = M_X''(0) - \mu^2 = \lambda + \lambda^2 - \lambda^2 = \lambda$$


