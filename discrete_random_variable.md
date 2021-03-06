# Discrete Random Variable

** Definition **
We say a random variable $$\mathbb{X}$$ is discrete if the range of $$\mathbb{X}$$ is at most countable, and we define probability mass function (p.m.f) of $$\mathbb{X}$$ to be $$p(x) = \mathbb{P}\{\mathbb{X}=x\}$$, denoted $$\mathbb{X} \sim p(x)$$

This is very straight forward, because $$\mathbb{P}\{\mathbb{X}=x\}$$ is, well, $$\mathbb{P}\{\mathbb{X}=x\}$$. There really is no need for other fancy method.

**Remark**

If $$\mathbb{X}$$ is discrete r.v with p.m.f $$p(x)$$ and c.d.f $$F(x)$$

(a) The sample space $$S$$ need not be at most countable, only the range of $$\mathbb{X}$$ need to be at most countable.

(b) $$p(x) > 0$$ for at most countable point, because the range of $$\mathbb{X}$$ is at most countable.

(c) $$F(x) = \sum_{t\leq x, p(t)>0}p(t)$$

Here, we cannot simply sum $$p(t)$$ over all $$t\leq x$$, because the number of $$t\leq x$$ might be uncountable.



