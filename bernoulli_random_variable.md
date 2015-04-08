# Bernoulli Random Variable
**Definition** We say a discrete random variable $$\mathbb{X}$$ is a Bernoulli random variable with parameter $$p$$, or has a Bernoulli distribution with parameter $$p$$, denoted by $$\mathbb{X} \sim Bernoulli(p)$$ if

$$ \mathbb{X} \sim p(n) =
\begin{cases} 
p & \text{ if } n = 1 \\ 
1-p & \text{ if } n = 0 
\end{cases}$$

For $$\mathbb{X} \sim Bernoulli(p)$$, $$\mu = p$$, and $$\sigma^2 = p(1-p)$$

**Property** If $$\mathbb{X} \sim Bernoulli(p)$$, then $$\mu = p, \sigma^2 = p(1-p)$$

**Proof 1**
By definition, trivial

**Proof 2**
Since $$\mathbb{X}$$ has finite range, and there is no problem in interchanging limit and finite summation, we can find $$\mu$$ and $$\sigma$$ via m.g.f.

$$M_X(t) = \mathbb{E}[e^{\mathbb{X}t}] = pe^{1*t} + (1-p)e^{0*t} = pe^t$$
So $$\mu = M_X'(0) = p$$, $$\sigma^2 = M_X''(0) - (M_X'(0))^2 = p-p^2 = p(1-p)$$

