# Normal Random Variable

**Definition** We say a continuous random variable $$\mathbb{X}$$ is has a normal distribution with parameter $$\mu, \sigma^2$$, denoted $$\mathbb{X} \sim normal(\mu, \sigma^2)$$ if
$$
 \mathbb{X} \sim f(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}
 \text{ for all } x\in\mathbb{R}
$$

**Property** If $$\mathbb{X} \sim normal(\mu, \sigma^2)$$, then $$\mu$$ is the mean and $$\sigma^2$$ is the variance

**Proof 1** By definition

First note that if $$\mathbb{X} \sim normal(\mu, \sigma^2)$$, then $$\mathbb{X} = \sigma\mathbb{Z}+\mu$$, where $$\mathbb{Z}$$ is standard normal distribution, with $$\mu = 0, \sigma = 1$$. So we only need to prove that the mean and variance of $$\mathbb{Z}$$ is $$0$$ and $$1$$, (to see why $$\mathbb{X} = \sigma\mathbb{Z}+\mu$$, look at their c.d.f).

$$\mathbb{E}[\mathbb{Z}] = \int_{-\infty}^\infty \frac{x}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}\mathrm{d}x = 0 \text{ because } \frac{x}{\sqrt{2\pi}} e^{-\frac{x^2}{2}} \text{ is odd and the integration exists}$$
$$\text{variance of } \mathbb{Z} = \int_{-\infty}^\infty \frac{x^2}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}\mathrm{d}x = \int_{-\infty}^\infty x * \frac{x}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}\mathrm{d}x$$
$$\text{(integration by part) } = 0 + \frac{1}{\sqrt{2\pi}} \int_{-\infty}^\infty e^{-\frac{x^2}{2}}\mathrm{d}x = 1$$

Here we used the identity $$\int_{-\infty}^\infty e^{-\frac{x^2}{2}}\mathrm{d}x = \sqrt{2\pi}$$

**Proof 2** By moment generating function

Since $$D_t (f(x)e^{xt}) = xe^{xt}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$ is continuous on $$\mathbb{R}^2$$, we can use m.g.f method.

The moment generating function
$$M_x(t) = \mathbb{E}[e^{\mathbb{X}t}] = \int_{-\infty}^\infty e^{xt} \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}} \mathrm{d}x = \frac{1}{\sqrt{2\pi}\sigma} \int_{-\infty}^\infty e^{-\frac{(x-\mu)^2-2 \sigma^2 t x}{2\sigma^2}} \mathrm{d}x$$

$$= \frac{1}{\sqrt{2\pi}\sigma} e^{\frac{(\mu+\sigma^2 t)^2 - \mu^2}{2\sigma^2}} \int_{-\infty}^\infty e^{-\frac{(x-(\mu+\sigma^2 t))^2}{2\sigma^2}} \mathrm{d}x = e^{\frac{2\mu\sigma^2 t+\sigma^4 t^2 }{2\sigma^2}} = e^{\frac{\sigma^2 t^2}{2}+\mu t}$$
So the mean
$$ \mu = \mathbb{E}[\mathbb{X}] = M_x'(0) = (\sigma^2 t + \mu) e^{\frac{\sigma^2 t^2}{2}+\mu t} |_{t=0} = \mu$$
and variance
$$\sigma^2 = M_X''(0) - \mu^2 = (\sigma^2 t + \mu)^2 e^{\frac{\sigma^2 t^2}{2}+\mu t} + \sigma^2 |_{t=0} - \mu^2 = \sigma^2$$



