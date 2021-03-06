# Binomial Random Variable

**Definition** We say a discrete random variable $$\mathbb{X}$$ is a binomial random variable with parameter $$n, p$$, or has a binomial distribution with parameter $$n, p$$, denoted by $$\mathbb{X} \sim binomial(n, p)$$ if
$$
 \mathbb{X} \sim p(k) =
  \begin{cases}
   {n \choose k}p^k(1-p)^{n-k} & \text{if } k \in \{0, 1, 2, ..., n\} \\
   1-p       & \text{otherwise}
  \end{cases}
$$

This random variable happens if we have n i.i.d Bernoulli(p).

For $$\mathbb{X} \sim binomial(n, p)$$, $$\mu = np$$, and $$\sigma^2 = np(1-p)$$

**Property** If $$\mathbb{X} \sim binomial(n, p$$, then $$\mu = np, \sigma^2 = np(1-p)$$

**Proof 1** By definition

Firstly note that
$$\mathbb{E}[X^m] = \sum_{k=0}^n k^m {n \choose k}p^k(1-p)^{n-k} = np \sum_{k=0}^n k^{m-1} \frac{(n-1)!}{(k-1)!(n-k)!}p^{k-1}(1-p)^{n-k}$$
$$= np \sum_{k=1}^n k^{m-1} \frac{(n-1)!}{(k-1)!(n-k)!}p^{k-1}(1-p)^{n-k} = np \sum_{k=0}^{n-1} (k+1)^{m-1} \frac{(n-1)!}{k!(n-k-1)!}p^{k-1}(1-p)^{n-k}$$
$$= np \sum_{k=0}^{n-1} (k+1)^{m-1} {n-1 \choose k}p^k(1-p)^{n-k} = np(\mathbb{E}[\mathbb{Y}+1)^{m-1}]$$
where $$\mathbb{Y} \sim binomial(n-1, p)$$

So $$\mu = np \mathbb{E}[1] = np$$, and $$\sigma^2 = \mathbb{E}[\mathbb{X}^2] - \mu^2 = np\mathbb{E}[\mathbb{Y}+1)] - n^2p^2 = np((n-1)p + 1) - n^2p^2 = np(1-p)$$

**Proof 2**
Here we can find $$\mu$$ and $$\sigma$$ via m.g.f because $$\mathbb{X}$$ has finite range.

The moment generating function
$$M_x(t) = \mathbb{E}[e^{\mathbb{X}t}] = \sum_{k=0}^n e^{kt} {n \choose k}p^k(1-p)^{n-k} = (1-p+pe^t)^n$$
So the mean
$$ \mu = \mathbb{E}[\mathbb{X}] = M_x'(0) = n (1-p+pe^t)^{n-1} pe^t |_{t=0}= np$$
and variance
$$\sigma^2 = \mathbb{E}[\mathbb{X}^2] - \mathbb{E}[\mathbb{X}]^2 = M_X''(0) - \mu^2 = np + n(n-1)p^2 - n^2p^2 = np(1-p) $$ 


