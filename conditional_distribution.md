# Conditional Distribution

In section 2.3 we talked about conditional probability, and in section 3.2 we talked about the general idea of conditional expectation based on the idea of conditional probability. Here is a review

**Definition** Let $$\mathbb{X}, \mathbb{Y}$$ be two random variable. When we say the conditional random variable of $$\mathbb{X}$$ given $$\mathbb{Y} = A$$, denoted by $$\mathbb{X}|{\mathbb{Y}=A}$$, we mean the random variable that has the following c.d.f:
$$F_{X|Y}(x|Y=y) = \frac{\mathbb{P}( \{\mathbb{X} \leq x\} \cap \{\mathbb{Y} = A\} )}{\mathbb{P}(\mathbb{Y} = A)} $$
Note $$A$$ can be a number or a set of number.

Now if  $$\mathbb{P}(\mathbb{Y} = A) = 0$$, we have a divide by zero issue. This can happen if $$A$$ is a constant and $$\mathbb{Y}$$ is continuous, or if $$A$$ is measurable but has measure zero (I will not discuss what "measure zero" means, refer to Lebesgue theory of integration).... etc. If this definition does not work, how do we define $$F_{X|Y}(x|Y=y)$$ or $$f_{X|Y}(x|Y=y)$$?

If $$\mathbb{X}, \mathbb{Y}$$ are two continuous random variable, then $$\mathbb{P}(\mathbb{Y} = y) = 0$$. Let $$g_y(x) = f_{X, Y}(x, y)$$. Intuitively, $$F_{X|Y}(x|Y=y)$$ should be $$\int_{-\infty}^x g_y(x) \mathrm{d}x$$ subject to a scaling factor, i.e, $$F_{X|Y}(x|Y=y) = c\int_{-\infty}^x g_y(x) \mathrm{d}x$$. But what should $$c$$ be?

By focusing on the consequence of a conditional probability, the answer is immediate. If $$F_{X|Y}(x|Y=y)$$ is a conditional c.d.f, it should be the case that $$\lim_{x\to\infty}F_{X|Y}(x|Y=y) = 1$$ because it is the probability that $$\mathbb{X}$$ takes on any value when $$\mathbb{Y}$$ is $$y$$. So we wish
$$\lim_{x\to\infty} c\int_{-\infty}^x g_y(x) \mathrm{d}x = 1$$
Therefore
$$c = \frac{1}{\int_{-\infty}^\infty f_{X,Y}(x, y)\mathrm{d}x}$$
So we have arrived at our reasonable definition
$$F_{X|Y}(x|Y=y) = \frac{\int_{-\infty}^x f_{X,Y}(x, y) \mathrm{d}x}{\int_{-\infty}^\infty f_{X,Y}(x, y)\mathrm{d}x} = \frac{\int_{-\infty}^x f_{X,Y}(x, y) \mathrm{d}x}{f_Y(y)}$$

As usually, we can always define p.d.f in terms of c.d.f. 
$$f_{X|Y}(x|Y=y) = F_{X|Y}'(x|Y=y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$

To further illustrate these definitions makes sense, if $$\Delta x$$ is very small, multiply it to both sides of $$f_{X|Y}(x|Y=y)$$, we get
$$f_{X|Y}(x|Y=y)\Delta x = \frac{f_{X,Y}(x, y)\Delta x\Delta y}{f_Y(y)\Delta y} \cong \frac{\mathbb{P}(x \leq \mathbb{X} \leq x + \Delta x, y \leq \mathbb{Y} \leq y + \Delta y)}{\mathbb{P}( y \leq \mathbb{Y} \leq y + \Delta y )}$$ 
which is the conditional probability that $$\mathbb{X}$$ is very close to $$x$$, given that $$\mathbb{Y}$$ is very close to $$y$$. So we have arrived at our definition of continuous random variable when their joint distribution exists.

**Definition** If $$\mathbb{X}, \mathbb{Y}$$ are two continuous random variable whose joint density function is $$f(x,y)$$, then
$$F_{X|Y}(x|Y=y) = \frac{\int_{-\infty}^x f_{X,Y}(x, y) \mathrm{d}x}{f_Y(y)}$$
$$f_{X|Y}(x|Y=y) = F_{X|Y}'(x|Y=y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$

Similarly, for discrete random variable
**Definition** If $$\mathbb{X}, \mathbb{Y}$$ are two discrete random variable whose joint density function is $$f(x,y)$$, then
$$F_{X|Y}(x|Y=y) = \frac{\sum_{x_i \leq x, f(x_i, y)>0} f(x_i, y)}{f_Y(y)}$$
$$f_{X|Y}(x|Y=y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$

**Example** We say normal random variables $$\mathbb{X}, \mathbb{Y}$$ has bivariate normal distribution if their joint p.d.f
$$f(x, y) = \frac{1}{2\pi\sigma_x\sigma_y}e^{ -\frac{1}{2(1-\rho^2)} [\frac{(x-\mu_x)^2}{\sigma^2_x} + \frac{(y-\mu_y)^2}{\sigma^2_y} - 2\rho\frac{(x-\mu_x)(y-\mu_y)}{\sigma_x\sigma_y}]} \text{ so }$$
for some $$\mu_x, \mu_y, \sigma_x, \sigma_y > 0$$, and $$\rho \in (-1, 1)$$
$$f_{X|Y}(x|y) = C_1 e^{ -\frac{1}{2(1-\rho^2)} [\frac{(x-\mu_x)^2}{\sigma^2_x} + \frac{(y-\mu_y)^2}{\sigma^2_y} - 2\rho\frac{(x-\mu_x)(y-\mu_y)}{\sigma_x\sigma_y}]} (C_1 = \frac{1}{\int_{-\infty}^\infty f(x, y) 2\pi\sigma_x\sigma_y} \mathrm{d}x)$$
$$= C_2 e^{ -\frac{1}{2(1-\rho^2)} [\frac{(x-\mu_x)^2}{\sigma^2_x} - 2\rho\frac{x(y-\mu_y)}{\sigma_x\sigma_y}] } (C_2 = C_1 e^{-\frac{1}{2(1-\rho^2)} [ \frac{(y-\mu_y)^2}{\sigma^2_y} + 2\rho\frac{\mu_x(y-\mu_y)}{\sigma_x\sigma_y}]})$$
$$= C_3 e^{-\frac{1}{2(1-\rho^2)\sigma^2_x} [x-(\mu_x + \rho\frac{\sigma_x}{\sigma_y}(y-\mu_y))]^2}$$
Now since $$f_{X|Y}(x|y)$$ is a p.d.f (a conditional p.d.f is still p.d.f), it must be the case that $$C_3 = \frac{1}{\sqrt{2\pi(1-\rho^2)}\sigma_x}$$, and $$f_{X|Y}(x|y) \sim normal( \mu_x + \rho\frac{\sigma_x}{\sigma_y}(y-\mu_y), (1-\rho^2)\sigma^2_x )$$

Knowing $$f_{X|Y}(x|y)$$ enables us to find $$f_Y(y)$$ because by the definition of $$f_{X|Y}$$, it is easy to show $$f_Y(y) = \frac{f(x, y)}{f_{X|Y}(x|y)} $$

For the following derivation, I will omit what $$C_i's$$ are, because those therms are irrelevant to our discussion.

$$f_Y(y) = C_1 e^{ -\frac{1}{2(1-\rho^2)} [\frac{(x-\mu_x)^2}{\sigma^2_x} + \frac{(y-\mu_y)^2}{\sigma^2_y} - 2\rho\frac{(x-\mu_x)(y-\mu_y)}{\sigma_x\sigma_y}] + \frac{1}{2(1-\rho^2)\sigma^2_x} [x-(\mu_x + \rho\frac{\sigma_x}{\sigma_y}(y-\mu_y))]^2}$$
$$= C_2 e^{ -\frac{1}{2(1-\rho^2)} [ \frac{(y-\mu_y)^2}{\sigma^2_y} - 2\rho\frac{(x-\mu_x)y}{\sigma_x\sigma_y}] + \frac{1}{2(1-\rho^2)\sigma^2_x} [2\mu_x\rho\frac{\sigma_x}{\sigma_y}(y-\mu_y) + \rho^2\frac{\sigma^2_x}{\sigma^2_y}(y-\mu_y)^2]}$$
$$= C_3 e^{ \frac{1}{2(1-\rho^2)\sigma^2_x} [ \frac{\sigma^2_x(y-\mu_y)^2}{\sigma^2_y} - 2\rho\frac{\sigma_x}{\sigma_y}(x-\mu_x)y - 2\mu_x\rho\frac{\sigma_x}{\sigma_y}(y-\mu_y) - \rho^2\frac{\sigma^2_x}{\sigma^2_y}(y-\mu_y)^2]  }$$
$$= C_4 e^{ \frac{1}{2(1-\rho^2)\sigma^2_x}  (1-\rho^2) \frac{\sigma^2_x(y-\mu_y)^2}{\sigma^2_y}} = C_4 e^{ \frac{\sigma^2_x(y-\mu_y)^2}{2\sigma^2_y}} \sim normal( \mu_y, \sigma^2_y )$$

Similarly, $$\mathbb{X} \sim  normal( \mu_x, \sigma^2_x)$$. Note this interesting point, even if the joint distribution of $$\mathbb{X}, \mathbb{Y}$$ exists and $$\mathbb{X}, \mathbb{Y}$$ are both normal, it doesn't mean they are independent (of course, you might think the question is why should they be). But under what condition are they independent? when $$\rho = 0$$, we see $$f(x, y) = f_X(x)f_Y(y)$$. This $$\rho$$ is in fact the correlation of $$\mathbb{X}$$ and $$\mathbb{Y}$$.

Another example illustrates you can not always apply the formula $$f_{X|Y}(x|Y=y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$, because the joint distribution might not exists for the two random variables.

**Example** If we know the probability of an experiment being successful is p, p exits but unknown. We also know that the value of p is a beta distribution with parameter $$\alpha, \beta$$. So we decide to do the experiment n+m times and we found out that n of which turned out successful. Now what do we know about the distribution of p?

**Solution**
Let $$E_1, E_2, ..., E_{m+n}$$ be i.i.d $$bernoulli(p)$$, where $$E_i$$ is 1 if the ith experiment turns out successful and 0 otherwise. Given $$P \sim beta(\alpha, \beta)$$ and $$N = \sum_{i=1}^{m+n} E_i \sim binomial(m+n, p)$$, the conditional c.d.f 
$$F_{P|N}(p|\mathbb{N}=n) = \frac{\mathbb{P}( \{P \leq p\} \cap \{\mathbb{N} = n\} )}{\mathbb{P}(\mathbb{N} = n)} = \frac{\mathbb{P}( \mathbb{N} = n | P \leq p )\  \mathbb{P}( P \leq p )}{\mathbb{P}(\mathbb{N} = n)} $$
$$= \frac{\int_0^p \mathbb{P} (\mathbb{N} = n | P=t) \mathbb{P}( P \leq t ) \mathrm{d}t }{\int_0^1 \mathbb{P} (\mathbb{N} = n | P=t) \mathrm{d}t }$$
$$\Rightarrow f_{P|N}(p|\mathbb{N}=n) = F'_{P|N}(p|\mathbb{N}=n) =   \frac{\mathbb{P} (\mathbb{N} = n | P=p)\ f_P(p)}{\int_0^1 \mathbb{P} (\mathbb{N} = n | P=p) \mathrm{d}p }$$
$$= \frac{ {n+m \choose n}p^n(1-p)^m }{\int_0^1{ n+m \choose n}p^n(1-p)^m\mathrm{d}p}\frac{1}{B(\alpha,	\beta)} p^{\alpha-1} (1-p)^{\beta-1} = C p^{n+\alpha-1} (1-p)^{m+\beta-1}$$
And this must be the p.d.f for $$beta(n+\alpha, m+\beta )$$.


