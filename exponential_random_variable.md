# Exponential Random Variable

**Definition** We say a continuous random variable $$\mathbb{X}$$ is has a exponential distribution with parameter $$\lambda$$, denoted $$\mathbb{X} \sim exp(\lambda)$$ if
$$
\begin{cases}
 \mathbb{X} \sim f(x) = \lambda e^{-\lambda x} & \text{if } x \geq 0\\
 0 & \text{otherwise}
 \end{cases}
$$

**Property** If $$\mathbb{X} \sim exp(\lambda)$$, $$\mu = \frac{1}{\lambda}, \sigma^2 = \frac{1}{\lambda^2}$$

**Proof 1** By definition
$$\mathbb{E}[\mathbb{X}] = \int_0^\infty \lambda x e^{-\lambda x} \mathrm{d}x = [-xe^{-\lambda x}]_0^\infty + \int_0^\infty e^{-\lambda x} \mathrm{d}x = \frac{1}{\lambda}$$
And since $$\mathbb{E}[\mathbb{X}^2] = \int_0^\infty \lambda x^2 e^{-\lambda x} \mathrm{d}x = [-x^2e^{-\lambda x}]_0^\infty + \int_0^\infty 2xe^{-\lambda x} \mathrm{d}x = \frac{2}{\lambda^2}$$
$$\sigma^2 = \mathbb{E}[\mathbb{X}^2] - \mu^2 = \frac{1}{\lambda^2}$$


**Proof 2** By moment generating function
Since $$D_t (\lambda e^{-\lambda x} e^{xt}) = \lambda x e^{(t-\lambda) x}$$ is continuous on $$(-\lambda, \lambda ) \times [0, \infty)$$, we can apply m.g.f method.

$$M_X(t) = \int_0^\infty \lambda e^{-\lambda x} e^{xt} \mathrm{d}x = \int_0^\infty \lambda e^{(t-\lambda) x} \mathrm{d}x = [\frac{\lambda}{t-\lambda}]_{t = 0}^\infty = \frac{\lambda}{\lambda - t}$$ so
$$\mu = M_X'(0) = \frac{\lambda}{(\lambda - t)^2} |_{t=0} = \frac{1}{\lambda}$$
$$\sigma^2 = M_X''(0) - \mu^2 = \frac{2\lambda}{(\lambda - t)^3} |_{t=0} - \frac{1}{\lambda^2} = \frac{1}{\lambda^2}$$


