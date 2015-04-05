# Cumulative distribution Function

** Definition ** Given $$\mathbb{X}$$, we define the cumulative distribution function (c.d.f) of $$\mathbb{X}$$ to be 
$$F(x) = \mathbb{P}\{\mathbb{X} \leq x\}$$

We denote $$\mathbb{X}$$ has c.d.f $$F$$ as $$\mathbb{X} \sim F(x)$$ for brevity. And note that $$F$$ is defined on $$\mathbb{R}$$.

Cumulative Distribution Function has some useful properties:

(a). c.d.f is right continuous.

** Proof **

From analysis, we know

 $$\lim_{n\to\infty}f(x_n)=f(x)\text{ for any sequence } \{x_n\} \text{ such that } x_n \to x$$
 ** if and only if **
 $$\lim_{t\to x}f(t)=f(x)$$

 
And for any $$\{x_n\}$$ in $$[x, \infty )$$ such that $$x_n\to x$$, and let $$A_n$$ be $$(-\infty, x_n]$$

$$F(\mathbb{X}\leq x) = \mathbb{P}( \mathbb{X} = \cap_{n=1}^\infty A_n )
 \text{ (because } (-\infty, x] = \cap_{n=1}^\infty A_n )$$
$$= \mathbb{P}(\cap_{n=1}^\infty\{\mathbb{X} = A_n \}) = \cap_{n=1}^\infty\mathbb{P}(\mathbb{X} = A_n ) = \lim_{n\to\infty}\mathbb{P}(\mathbb{X} = A_n ) = \lim_{n\to\infty}\mathbb{P}(\mathbb{X} \leq x_n )$$

The choice of $$\{x_n\}$$ was arbitrary, so 

$$\forall_x \lim_{t\to x^+}F(t) = F(x)$$

(b). c.d.f is non-decreasing.

(c). $$\lim_{t\to \infty}F(t) = 1, \lim_{t\to -\infty}F(t) = 0$$

(d). If $$a<b$$, $$\mathbb{P}( \mathbb{X}\leq b ) = \mathbb{P}( \mathbb{X} \leq a ) + \mathbb{P}( a < \mathbb{X} \leq b )$$ (because $$\{\mathbb{X}\leq a\}$$ and $$\{a<\mathbb{X}\leq b\}$$ are disjoint set), so 

$$\mathbb{P}( a < \mathbb{X} \leq b ) = F(b) - F(a)$$

**C.d.f and its properties are often useful, because it is independent of the different types of random variable.** These properties are true as long as it is a c.d.f of a random variable.


