# Beta Random Variable

**Definition** of $beta function$: $$beta\ function$$ has two parameters $$x, y>0$$:
$$B(x, y) = \int_0^1 t^{x-1}(1-t)^{y-1}\mathrm{d}t$$ 

We say a continuous r.v $\mathbb{X}$ is a beta r.v with parameters $x, y$, denoted $$\mathbb{X} \sim \beta(x, y)$$, if
$$
 \mathbb{X} \sim f(x) =
  \begin{cases}
   \frac{1}{B(x, y)} t^{x-1} (1-t)^{y-1} & \text{if } x > 0, y>0 \\
   0       & otherwises
  \end{cases}
$$

The follow question shows how $$beta$$ distribution might arise:

**Example** If we know the probability of an experiment being successful is p, p exits but unknown. We also know that the value of p is a uniform distribution in [0,1]. So we decide to do the experiment n+m times and we found out that n of which turned out successful. Now what do we know about the distribution of p?

\textbf{Solution}
Let $$E_1, E_2, ..., E_{m+n}$$ be i.i.d Bernoulli(p), where $$E_i$$ is 1 if the ith experiment turns out successful and 0 otherwise. Given $$P \sim uniform(0, 1)$$ and $$N = \sum_{i=1}^n E_i \sim binomial(m+n, p)$$, the conditional c.d.f 
$$F_{P|N}(p|\mathbb{N}=n) = \frac{\mathbb{P}( \{P \leq p\} \cap \{\mathbb{N} = n\} )}{\mathbb{P}(\mathbb{N} = n)} = \frac{\mathbb{P}( \mathbb{N} = n | P \leq p )\  \mathbb{P}( P \leq p )}{\mathbb{P}(\mathbb{N} = n)} $$
$$= \frac{\int_0^p \mathbb{P} (\mathbb{N} = n | P=t) f_\mathbb{P}(t)\mathrm{d}t }{\int_0^1 \mathbb{P} (\mathbb{N} = n | P=t) \mathrm{d}t }$$
$$\Rightarrow f_{P|N}(p|\mathbb{N}=n) = F'_{P|N}(p|\mathbb{N}=n) =   \frac{\mathbb{P} (\mathbb{N} = n | P=p)\ f_P(p)}{\int_0^1 \mathbb{P} (\mathbb{N} = n | P=p) \mathrm{d}p }$$
$$= \frac{ {n+m \choose n}p^n(1-p)^m }{\int_0^1{ n+m \choose n}p^n(1-p)^m\mathrm{d}p} = \frac{1}{B(n+1, m+1)} p^n (1-p)^m$$
And this is exactly the p.d.f for $$beta(n+1, m+1)$$.

**Example** $$X_1, .., X_n \overset{i.i.d}{\sim} uniform(0, 1), Y_1 = X_{(1)} (min( X_1, ..., X_n )), Y_n = X_{(n)}$$, show that $$Y_1 \sim beta(1, n), Y_n \sim beta(n, 1)$$

**Solution**
$$F_{Y_n}(y) = \mathbb{P}(X_1 \leq y, ..., X_n \leq y) = y^n $$
for $$y \in [0, 1]$$, so $$f_{Y_n}(y) = ny^{n-1} = \frac{1}{B(n, 1)}y^{n-1} \sim beta(n, 1)$$ for $$y \in [0, 1]$$. $$F_{Y_1}$$ can be shown similarly, with $$F_{Y_1}(y) = 1-(1-y)^n$$, and $$f_{Y_1} = n(1-y)^{n-1}$$


