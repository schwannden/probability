# Chi-square Random Variable 

**Definition** We say a continuous r.v $$\mathbb{X}$$ is a Chi-square if it is $$gamma( \frac{1}{2}, \frac{k}{2} )$$ for some $$k > 0$$, denoted $$\mathbb{X} \sim \chi^2(k)$$.

So by the property of $gamma$ distribution, we know:

**Property** If $$\mathbb{X} \sim \chi^2(k)$$, $$\mu = k, \sigma^2 = \frac{k}{2}$$

**Theorem** If $$\mathbb{Z} \sim normal(0, 1)$$, then $$\mathbb{Z}^2 \sim \chi^2(1)$$

**Proof** $$\mathbb{P}(\mathbb{Z}^2 \leq x) = \mathbb{P}(-\sqrt{x} \leq \mathbb{Z} \leq \sqrt{x}) =  2\int_0^{\sqrt{x}} \frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}} $$
$$ \text{ so p.d.f } f \text{ of } \mathbb{Z}^2 = \frac{\mathrm{d}}{\mathrm{d}x}2\int_0^{\sqrt{x}} \frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}} = \frac{1}{\sqrt{\pi}}\frac{1}{2}(\frac{1}{2} x)^{-\frac{1}{2}}e^{-\frac{x}{2}} \sim gamma(\frac{1}{2}, \frac{1}{2}) = \chi^2(1)$$

**Theorem** If $$\mathbb{Z}_1, ..., \mathbb{Z}_n \sim \text{ i.i.d } normal(0, 1)$$, then $$\sum_{i=1}^n \mathbb{Z}_i \sim \chi^2(n)$$

**Proof** $$M_{Z_i}(t) = (\frac{1/2}{1/2 - t})^{\frac{1}{2}} = (1-2t)^{-\frac{1}{2}}$$, so $$M_{\sum_{i=0}^n Z_i}(t) = M_{Z_1}(t)^n = (1-2t)^{-\frac{n}{2}} \sim gamma(\frac{1}{2}, \frac{n}{2}) = \chi^2(n)$$

**lemma** If $$\mathbb{X} \sim \chi^2(n)$$ and $$\mathbb{Y} \sim \chi^2(m)$$ are independent, then $$\mathbb{X}+\mathbb{Y} \sim \chi^2(n+m)$$

**Example** $$Z_1 \sim normal(\delta, 1), and Z_2, ..., Z_p \sim normal(0, 1)$$ are $$p$$ independent random variable, then $$W = \sum_{i=1}^p Z_i^2 \sim \chi^2_p(\delta^2)$$

**Solution**
$$V = (Z_1 - \delta)^2 + \sum_{i=2}^p Z_i^2 \sim \chi^2(p)$$

$$\mathbb{E}[V] = \mathbb{E}[ (Z_1 - \delta)^2 + \sum_{i=2}^p Z_i^2 ] = \mathbb{E}[\sum_{i=1}^p Z_i^2] - 2\delta\mathbb{E}[Z_1] + \delta^2$$
$$= \mathbb{E}[W] - \delta^2 = p \Rightarrow \mathbb{E}[W] = p + \delta^2$$
Now variance
$$var(V) = var( (Z_1-\delta)^2 ) + 2cov( (Z_1-\delta)^2, \sum_{i=2}^p Z_i^2 ) + var( \sum_{i=2}^p Z_i^2 )$$
$$= var(Z_1^2 -2\delta Z_1 + \delta^2) + var( \sum_{i=2}^p Z_i^2 )$$
$$= var(Z_1^2)+2cov(Z_1^2, -2\delta Z_1)+var(-2\delta Z_1) + var( \sum_{i=2}^p Z_i^2 )$$
$$= var(\sum_{i=1}^p Z_i^2) -4\delta cov(Z_1^2, Z_1) + 4\delta^2 var(Z_1)$$
$$= var(W) -4\delta(\mathbb{E}[Z_1^3]-\mathbb{E}[Z_1^2]\mathbb{E}[Z_1])+4\delta^2$$
Now $$\mathbb{E}[Z_1^3]$$ can be obtained by m.g.f. Recall that $$M_{Z_1}(t) = e^{\delta t + \frac{1}{2}t^2}$$
$$M_{Z_1}'(t) = (\delta+t)e^{\delta t + \frac{1}{2}t^2}$$
$$M_{Z_1}''(t) = (\delta+t)^2e^{\delta t + \frac{1}{2}t^2}+e^{\delta t + \frac{1}{2}t^2}$$
$$M_{Z_1}'''(t) = (\delta+t)^3e^{\delta t + \frac{1}{2}t^2}+3(\delta+t)e^{\delta t + \frac{1}{2}t^2}$$
So $$M_{Z_1}'''(0) = \delta^3+3\delta$$, and $$M_{Z_1}''(0) = \delta^2 + 1$$. Therefore $$var(W) = 2p+4\delta^2$$

