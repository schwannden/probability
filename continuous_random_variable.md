# Continuous Random Variable
**Definition** We say a real function $$F$$ is absolutely continuous if there exists real function $$f$$ such that
$$\forall_a \forall_x \ \ F(x) = f(a) + \int_a^x f(t) \mathrm{d}t$$

**Definition**
We say a random variable $$\mathbb{X} \sim F$$ is continuous if its c.d.f $$F$$ is absolutely continuous

**Definition**
The function $$f$$ such that $$\forall_a \forall_x \ \ F(x) = f(a) + \int_a^x f(t) \mathrm{d}t $$ is called the probability density function (p.d.f) of  $$\mathbb{X}$$.

Now let's take a look at the probability mass function of $$\mathbb{\mathbb{X}}$$.

For any number $$a\in\mathbb{R}$$, let $$A_n$$ be the half open interval $$(a-\frac{1}{n}, a]$$
$$\mathbb{P}(\mathbb{X}=a) = \mathbb{P}( \mathbb{X} = \cap_{n=1}^\infty A_n )
 \text{ (because   } a = \cap_{n=1}^\infty A_n )$$
$$= \mathbb{P}(\cap_{n=1}^\infty\{\mathbb{X} = A_n \}) = \cap_{n=1}^\infty\mathbb{P}(\mathbb{X} = A_n )$$ 
where the last equality comes from the continuity of probability function on monotonic sequence of sets. Now
$$\cap_{n=1}^\infty\mathbb{P}(\mathbb{X} = A_n ) = \cap_{n=1}^\infty F(a) - F(a-\frac{1}{n}) = \lim_{n\to\infty} F(a) - F(a-\frac{1}{n})$$

If $$\mathbb{X}$$ is continuous r.v,  then
$$\mathbb{P}(\mathbb{X}=a) = \lim_{n\to\infty} F(a) - F(a-\frac{1}{n}) = 0$$
because $$F$$ is continuous.

Therefore, p.m.f of a continuous r.v is meaningless, because it's p.m.f is 0 every where. So p.d.f is what we need to capture the spirit of $$\mathbb{P}\{\mathbb{X}=x\}$$, even though $$\mathbb{P}\{\mathbb{X}=x\}$$ is $$0$$.
\textbf{Remark}

1. When something has a probability 0, it doesn't mean it won't happen! As we just see, any p.m.f of a contunuous random variable is 0.

2. Given a c.d.f $$F$$, its corresponding p.d.f $$f$$, is not unique. However, it rarely matters because the results we need generally come from imtergrating $$f$$, and even if there are differen $$f$$'s, the result after intergrating is always the same. Why? To answer this you will have to take some courses in measure theory.

