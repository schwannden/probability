# Expectation

Expectation is a way to characterize a random variable.

**Definition** Let $$g$$ be a real function, the expectation of a random variable $$\mathbb{X} \sim f$$, denoted $$\mathbb{E}[g(\mathbb{X})]$$, is defined as
$$\mathbb{E}[g(\mathbb{X})] =
\begin{cases}
\sum_{x|f(x)>0} g(x)f(x) & \text{ for discrete random variable} \\
\int_{-\infty}^{\infty} g(x)f(x) \mathrm{d}x & \text{ for continuous random variable}
\end{cases}$$
Note here $$f$$ is treated as p.m.f in discrete case and p.d.f in continuous case.

In the special case $$g(x) = x$$, $$\mathbb{E}[g(\mathbb{X})] = \mathbb{E}[\mathbb{X}]$$ is called the **mean** of $$\mathbb{X}$$, usually denoted by $$\mu$$. And in the special case that $$g(x) = (x-\mu)^2$$, $$\mathbb{E}[g(\mathbb{X})] = \mathbb{E}[(\mathbb{X}-\mu)^2]$$ is called the **variance** of $$\mathbb{X}$$, usually denoted by $$\sigma^2$$

Some properties of mean and variance:

1. For any constant $$a$$, $$\mathbb{E}[a] = a$$. This follows from the fact that $${\sum_{x|f(x)>0}f(x) = 1}$$ in discrete case, and $${\int_{-\infty}^{\infty}f(x)\mathrm{d}x = 1}$$ in continuous case.

2. For any constants $$a, b$$, $$\mathbb{E}[a\mathbb{X}+b] = a\mathbb{E}[\mathbb{X}]+b$$, provided that $$\mathbb{E}[\mathbb{X}]$$ exists. The proof follows from the fact that we can take scalar out of a convergent integral and series.

3. Let $$\sigma^2$$ be the variance of $$\mathbb{X}$$, the variance of $$a\mathbb{X}$$ is $$a^2\sigma^2$$, the proof is trivial.

4. $$\sigma^2 = \mathbb{E}[(\mathbb{X}-\mu)^2] = \mathbb{E}[\mathbb{X}^2]-2\mu\mathbb{E}[\mathbb{X}]+\mathbb{E}[\mu^2] = \mathbb{E}[\mathbb{X}^2] - \mu^2$$




