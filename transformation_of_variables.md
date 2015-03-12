# Transformation of Variables

Let $$\mathbb{X} \sim f_X$$ be a continuous random variable with range $$A = X(S)$$, $$g$$ is a differentiable and invertible real function on A, then the p.d.f of $$\mathbb{Y} = g(\mathbb{X})$$, $$f_Y(y) = f_X(g^{-1}(y)) |\frac{\mathrm{d}g^{-1}(y)}{\mathrm{d}y} |$$, for $$y\in g(A)$$

**proof** If $$g$$ is increasing, $$g^{-1}$$ is also increasing.  The c.d.f $$F_Y(y) = \mathbb{P}( g(\mathbb{X}) \leq y ) = \mathbb{P}( \mathbb{X} \leq g^{-1}(y) ) = F_X( g^{-1}(y) )$$, so $$f_Y(y) = f_X(g^{-1}(y)) \frac{\mathrm{d}g^{-1}(y)}{\mathrm{d}y} = f_X(g^{-1}(y)) |\frac{\mathrm{d}g^{-1}(y)}{\mathrm{d}y} |$$


If $$g$$ is decreasing, then c.d.f $$F_Y(y) = \mathbb{P}( g(\mathbb{X}) \leq y ) = \mathbb{P}( \mathbb{X} \geq g^{-1}(y) ) = 1 - F_X( g^{-1}(y) )$$, so $$f_Y(y) = -f_X(g^{-1}(y)) \frac{\mathrm{d}g^{-1}(y)}{\mathrm{d}y}  = f_X(g^{-1}(y)) |\frac{\mathrm{d}g^{-1}(y)}{\mathrm{d}y} |$$

**Example**
If $$\mathbb{X} \sim uniform(0, 1)$$, and $$\mathbb{Y} = -2 \ln(\mathbb{X})$$, then $$\mathbb{Y} \sim \chi^2(2)$$

**Solution**
Since $$y=-2\ln(x)$$ if and only if $$x = e^{-\frac{y}{2}}$$
$$f_Y(y) = f_X(e^{-\frac{y}{2}}) | -\frac{1}{2} e^{-\frac{y}{2}} | = 
\begin{cases}
	\frac{1}{2} e^{-\frac{y}{2}} & \text{ if } x\geq 0 \\
	0 & \text{otherwise}
\end{cases}
\sim gamma(\frac{2}{2}, \frac{1}{2}) = \chi^2(2)$$

Suppose we have continuous random variables $$X_1, X_2, ..., X_n$$ with joint p.d.f $$f_{\bar{X}}( \bar{x} )$$, and $$g: \bar{X}(S) \to \mathbb{R}^n$$ is 1-1 then change of variable tells us
$$\mathbb{\bar{Y}} = g(\mathbb{\bar{X}}) \sim f_{\bar{Y}}(\bar{y}) = f_{\bar{X}}(g^{-1}(\bar{y}))|J_g( g^{-1}(\bar{y}) )|$$
where $$J_{g^{-1}}( g^{-1}(\bar{y}))$$ is the Jocobian of g at $$g^{-1}(\bar{y})$$.

**Example**
Suppose $$\mathbb{X}_1, \mathbb{X}_2 \sim i.i.d\ uniform(0, 1)$$ and $$\mathbb{Y}_1 = \mathbb{X}_1 + \mathbb{X}_2, \mathbb{Y}_2 = \mathbb{X}_1 - \mathbb{X}_2$$, what is the joint p.d.f for $$\mathbb{Y}_1, \mathbb{Y}_2$$ abd marginal p.d.f for each?

**Solution**
The joint p.d.f of $$\mathbb{X}_1, \mathbb{X}_2$$,
$$f_{\bar{X}}(\bar{x}) = f_{X_1}(x)f_{X_2}(x) = 
\begin{cases}
   1  & \text{if } x \in [0,1] \times [0,1] \\
   0 & \text{otherwise}
  \end{cases}
$$

Jacobian  $$g^{-1}(y1, y2) = (\frac{y_1+y_2}{2}, \frac{y_1-y_2}{2})$$ is
$$\left| \begin{array}{ccc}
\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2} \end{array} \right| = -\frac{1}{2}$$ 
for all $$y1, y2$$, so
$$f_{\bar{Y}}(\bar{y}) = f_{\bar{X}}(\frac{y_1+y_2}{2}, \frac{y_1-y_2}{2})| -\frac{1}{2} | = 
\begin{cases}
1 & \text{ if } \frac{y_1+y_2}{2} \in [0,1] \text{ and } \frac{y_1-y_2}{2} \in [0,1] \\
0 & \text{otherwise}

\end{cases}
$$
So the marginal p.d.f of $$Y_1, Y_2$$ can be calculated as

**Definition** If a sequence of r.v.’s $$X_1, ..., X_n$$ are independent and identically dis-
tributed (i.i.d.),then they are called a **random sample**.

So if $$X_1, ..., X_n$$ is a random sample from a distribution, the joint p.d.f of $$X_1, ..., X_n$$
$$f_{\bar{X}}(x_1, x_2, ..., x_3) =  \prod_{i=1}^n f(x_i)$$
where $$f$$ is the p.d.f of any $$X_i$$ in the random sample.
 
**Definition**
Suppose we have a random variable with p.d.f $$f(x, \theta)$$ where $$\theta$$ is an unknown vector, we then call $$\theta$$ a parameter and the set of $$\theta$$'s possible values, denoted $$\Theta$$, is called the parameter space.

**Example**
If $$\mathbb{X} \sim normal(\mu, \sigma^2)$$, its p.d.f has parameter $$\mu$$ and $$\sigma$$, with parameter space $$\{\mu, \sigma^2\} \in R \times
[0, \infty)$$

**Example**
If $$\mathbb{X} \sim Poisson(\lambda)$$, $$\mathbb{X}$$'s p.d.f has parameter $$\lambda$$ with a parameter space $$[0, \infty)$$

**Definition**
For a random sample $$X_1, ..., X_n$$, any function $$g(x_1, x_2, ..., x_n)$$ independent of parameter $$\theta$$ is called a statistics.

**Example**
$$\bar{\mathbb{X}} = \frac{1}{n}\sum_{i=1}^n\mathbb{X}_i$$
is called the sample mean and
$$S^2 = \frac{1}{n-1} \sum_{i=1}^n(\mathbb{X}_i - \bar{\mathbb{X}})^2$$
is called the sample variance. And they are both statistics.

**Theorem**
Two random variables $$\mathbb{X}_1, \mathbb{X}_2$$ are independent if and only if $$M_{X_1, X_2}(t_1, t_2) = M_{X_1}(t_1)M_{X_2}(t_2)$$

**Proof**
If $$\mathbb{X}_1, \mathbb{X}_2$$ are independent, then
$$M_{X_1, X_2}(x_1, x_2) = \int_{-\infty}^{\infty}\int_{-\infty}^{\infty} e^{x_1t_1+x_2t_2} \mathrm{d}F_{X_1}(x_1)\mathrm{d}F_{X_2}(x_2)$$
$$ = \int_{-\infty}^{\infty}\int_{-\infty}^{\infty} e^{x_1t_1}e^{x_2t_2} \mathrm{d}F_{X_1}(x_1)\mathrm{d}F_{X_2}(x_2) = \int_{-\infty}^{\infty}e^{x_1t_1}\mathrm{d}F_{X_1}(x_1)\int_{-\infty}^{\infty}e^{x_2t_2}\mathrm{d}F_{X_2}(x_2)$$
$$= M_{X_1}(t_1)M_{X_2}(t_2)$$
Note that the proof handles the case for both continuous and discrete case, this shows the usefulness of Riemann-Stieltjes integral.

Now if $$M_{X_1, X_2}(t_1, t_2) = M_{X_1}(t_1)M_{X_2}(t_2)$$, then we will use the fact that m.g.f uniquely determines a distribution.
Since
$$\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} e^{x_1t_1+x_2t_2} \mathrm{d}F_{X_1}(x_1)\mathrm{d}F_{X_2}(x_2)$$
$$= \int_{-\infty}^{\infty}e^{x_1t_1}\mathrm{d}F_{X_1}(x_1)\int_{-\infty}^{\infty}e^{x_2t_2}\mathrm{d}F_{X_2}(x_2) \text{ by assumption}$$
$$= \int_{-\infty}^{\infty}\int_{-\infty}^{\infty} e^{x_1t_1}e^{x_2t_2} \mathrm{d}F_{X_1}(x_1)\mathrm{d}F_{X_2}(x_2) \text{ basic operation on integral}$$
The first equation correspond to $$f_{\bar{X}}(t_1, t_2)$$ and the third correspond to $$f_{X_1}f_{X_2}$$'s, so $$f_{\bar{X}} = f_{X_1}f_{X_2}$$

Now let's introduce a less independent idea of independence. We say $$X_1, X_2, ..., X_n$$ and $$Y_1, Y_2, ..., Y_m$$ are
independent if $$f_{\bar{X}, \bar{Y}}(x, y) = f_{\bar{X}}(x)f_{\bar{Y}}(y)$$, where $$f_{\bar{X}, \bar{Y}}$$, $$f_{\bar{X}}$ and $f_{\bar{Y}}$$ are joint p.d.f of $$X_1, ..., X_n, Y_1, ..., Y_m$$, $$X_i$$'s and $$Y_i$$'s respectively.

If $$X_1, X_2, ..., X_n$$ and $$Y_1, Y_2, ..., Y_m$$ are independent, then $$g(X_1, X_2, ..., X_n)$$ and $$h(Y_1, Y_2, ..., Y_m)$$ are independent. Some consequences then follows:
(a) $$\mathbb{E}[g(x)h(y)] = \mathbb{E}[g(x)]\mathbb{E}[h(y)]$$
(b) $$M_{\bar{X}, \bar{Y}}( 0, t ) = M_Y(t)$$

**Example** If $$\mathbb{X} \sim \chi^2(a), \mathbb{Y} \sim \chi^2(b)$$ are independent chi-square random variable, then $$\mathbb{X}+\mathbb{Y} \sim \chi^2(a+b)$$

**Proof** Find the m.g.f. of $$\mathbb{X}+\mathbb{Y}$$ and we are done.
$$M_{X, Y}(t) = M_X(t)M_Y(t) = (1-2t)^{-\frac{a+b}{2}} \sim \chi^2(a+b)$$

**Example** If $$\mathbb{Z} \sim normal(0, 1)$$, then $$\mathbb{Z}^2 \sim \chi^2(1)$$

**Proof** Now this doesn't look like you can solve it with m.g.f, so we appeal to c.d.f. Note if $$f(x) = f(-x)$$ is an even function, then $$\int_{-a}^a f(x) \mathrm{d}x = 2\int_0^a f(x) \mathrm{d}x$$. 

$$F_{Z^2}(y) = \mathbb{P}(\mathbb{Z}^2 \leq y ) = \mathbb{P}(-\sqrt{y} \leq \mathbb{Z} \leq \sqrt{y} ) = 2 \int_0^{\sqrt{y}} f_Z(y) \mathrm{d}y$$

So p.d.f of $$F_{Z^2}$$ is 
$$\mathrm{D}_y 2\int_0^{\sqrt{y}} \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}} \mathrm{d}x = \frac{\sqrt{2}}{\sqrt{\pi}2} e^{-\frac{y}{2}} y^{-\frac{1}{2}} \sim \chi^2(1)$$

Suppose that $$\mathbb{X}_1, \mathbb{X}_2, \mathbb{X}_3, \mathbb{X}_4$$ are independent, we know that $$(\mathbb{X}_1, \mathbb{X}_2)$$ and $$(\mathbb{X}_3, \mathbb{X}_4)$$ are independent, so $$g(\mathbb{X}_1, \mathbb{X}_2)$$ and $$h(\mathbb{X}_3, \mathbb{X}_4)$$ are independent. But in general, $$g(\mathbb{X}_1, \mathbb{X}_2, \mathbb{X}_3, \mathbb{X}_4)$$ and $$h(\mathbb{X}_1, \mathbb{X}_2, \mathbb{X}_3, \mathbb{X}_4)$$ are not independent.

**Theorem** If $$\mathbb{X}_1, \mathbb{X}_2, ..., \mathbb{X}_n$$ are a random sample from $$normal(\mu, \sigma)$$, then
1.  The sample mean $$\bar{\mathbb{X}} = \frac{1}{n}\sum_{i=1}^n\mathbb{X}_i \sim normal(\mu, \frac{\sigma^2}{n})$$
2. The sample variance $$S^2 = \frac{1}{n-1} \sum_{i=1}^n (\mathbb{X}_i-\bar{\mathbb{X}})^2$$ and sample mean $$\bar{\mathbb{X}}$$ are independent.
3. $$\frac{(n-1)S^2}{\sigma^2} = \frac{\sum_{i=1}^n (\mathbb{X}_i-\bar{\mathbb{X}})^2}{\sigma^2} \sim \chi^2(n-1)$$

**Proof**
1. This can be proved by m.g.f. The m.g.f of $$\bar{\mathbb{X}} = \prod_{i=1}^n \mathbb{E}[e^{\frac{tX_1}{n}}] = e^{\mu t + \frac{\sigma^2 / n}{2}t} \sim normal(\mu, \frac{\sigma^2}{n})$$
2. To show that $$\bar{\mathbb{X}}$$ and $$S^2$$ are independent, we need only to show that $$\bar{\mathbb{X}}$$ and $$(\mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})$$ are independent.
The joint m.g.f of $$\bar{\mathbb{X}}$$ and $$(\mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})$$ is
$$M_{(\bar{\mathbb{X}}, \mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})}( t, t_1, ..., t_n ) = \mathbb{E}[e^{ \frac{t}{n}\sum_{i=1}^n X_i + \sum_{i=1}^n t_i X_i - \sum_{i=1}^n t_i \frac{\sum_{i=1}^n X_i}{n} }]$$
$$= \mathbb{E}[e^{\sum_{i=1}^n( \frac{t}{n}+t_i-\bar{t} )X_i}] = \text{ ( by the independence of } \mathbb{X}_i \text{'s )} \prod_{i=1}^n \mathbb{E}[e^{\frac{t}{n}+t_i-\bar{t} X_i}]$$
$$= \prod_{i=1}^n M_{X_i}(\frac{t}{n}+t_i-\bar{t}) = \prod_{i=1}^n e^{\mu (\frac{t}{n}+t_i-\bar{t}) + \frac{\sigma^2}{2} (\frac{t}{n}+t_i-\bar{t})^2 }$$
$$= e^{ \mu t + \frac{(\sigma^2/n)}{2}t^2 + \mu  \sum_{i=1}^n (t_i - \bar{t}) + \frac{\sigma^2}{2} \sum_{i=1}^n (t_i-\bar{t})^2 + \frac{\sigma^2}{n^2}nt \sum_{i=1}^n (t_i - \bar{t})}$$
$$( \sum_{i=1}^n (t_i - \bar{t}) = 0 ) = e^{ \mu t + \frac{(\sigma^2/n)}{2}t^2}e^{\frac{\sigma^2}{2} \sum_{i=1}^n (t_i-\bar{t})^2} = M_{\bar{X}}(t)\prod_{i=1}^n M_{X_i}(t_i-\bar{t})$$
And
$$\prod_{i=1}^n M_{X_i}(t_i-\bar{t}) =  \text{ ( by the independence of } \mathbb{X}_i \text{'s ) } \mathbb{E}[e^{ \sum_{i=1}^n (t_i-\bar{t})X_i }]$$
$$= \mathbb{E}[e^{ \sum_{i=1}^n (t_i X_i-\frac{\sum_{j=1}^n t_j X_i}{n}) }] = \mathbb{E}[e^{ \sum_{i=1}^n t_i X_i-\frac{\sum_{i=1}^n \sum_{j=1}^n t_j X_i}{n}) }] = \mathbb{E}[e^{ \sum_{i=1}^n t_i X_i-\frac{\sum_{j=1}^n \sum_{i=1}^n t_j X_i}{n}) }]$$
$$ = \mathbb{E}[e^{ \sum_{i=1}^n (t_i X_i-\frac{\sum_{j=1}^n X_j t_i}{n}) }] = \mathbb{E}[e^{ \sum_{i=1}^n (X_i-\bar{\mathbb{X}}) t_i} ] = M_{(\mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})}( t_1, ..., t_n )$$
$$\text{ so }M_{(\bar{\mathbb{X}}, \mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})}(t) = M_{\bar{\mathbb{X}}}(t) M_{(\mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})}( t_1, ..., t_n )$$
3. First we need the following equality
$$\sum_{i=1}^n (X_i-\mu)^2 = \sum_{i=1}^n (X_i-\bar{X}+\bar{X}-\mu)^2 = \sum_{i=1}^n (X_i-\bar{X})^2 + n(\bar{X}-\mu)^2 + 2(\bar{X}-\mu)\sum_{i=1}^n(X_i-\bar{X})$$
$$= \sum_{i=1}^n (X_i-\bar{X})^2 + n(\bar{X}-\mu)^2$$ 
because $$\sum_{i=1}^n(X_i-\bar{X}) = 0$$. Dividing both side by $$\sigma^2$$

$$\sum_{i=1}^n (\frac{X_i-\mu}{\sigma})^2 = \sum_{i=1}^n (\frac{X_i-\bar{X}}{\sigma})^2 + (\frac{\bar{X}-\mu}{\sigma/\sqrt{n}})^2$$

Now
$$\sum_{i=1}^n (\frac{X_i-\mu}{\sigma})^2 \sim \chi^2(n) \text{ and } (\frac{\bar{X}-\mu}{\sigma/\sqrt{n}})^2 \sim \chi^2(1)$$
And since $$\bar{\mathbb{X}}$$ and $$(\mathbb{X}_1-\bar{\mathbb{X}}, ..., \mathbb{X}_n-\bar{\mathbb{X}})$$ are independent,
$$M_{\sum_{i=1}^n (\frac{X_i-\mu}{\sigma})^2}(t) = (1-2t)^{-\frac{n}{2}} = M_{(\frac{X_i-\bar{X}}{\sigma})^2}(t)M_{(\frac{\bar{X}-\mu}{\sigma/\sqrt{n}})^2}(t) = M_{(\frac{X_i-\bar{X}}{\sigma})^2}(t)(1-2t)^{-\frac{1}{2}}$$

Note that if $$\sum_{i=1}^n(\frac{X_i-\bar{X}}{\sigma})^2 \sim \chi^2(n-1)$$ the above equation will hold, so it must be the case that $$\sum_{i=1}^n(\frac{X_i-\bar{X}}{\sigma})^2 = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$$ by the 1-1 correspondence between distribution and m.g.f.


