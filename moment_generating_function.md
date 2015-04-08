# Moment Generating Function

The moment generating function (m.g.f) of a random variable $$\mathbb{X}$$, denoted $$M_X(t)$$, is defined as
$$M_X(t) = \mathbb{E}[e^{\mathbb{X}t}]\text{ provided the expectation exists}$$

Moment generating function is very useful in finding out some properties of a random variable. As the following two theorems shows how can we find the means of a random variable by its m.g.f.

**Theorem** If $$\mathbb{X} \sim p$$ is a discrete random variable with finite range, Then $$M_X'(0) = \mu$$.

**Theorem** If $$\mathbb{X} \sim p$$ is a discrete random variable with infinite range, $$x_1, x_2, ...$$ is the sequence of all points in the range of $$\mathbb{X}$$, and let $$g_n(t) = e^{x_n t}p(x_n)$$. Now if there exists $$\epsilon$$ such that
1. $$\sum_{n=1}^\infty g_n(t) \text{ converges for some } t \text{ in } [0-\epsilon, 0+\epsilon]$$
2. $$\sum_{n=1}^\infty g_n'(t)  \text{ converge absolutely in } [0-\epsilon, 0+\epsilon]$$

Then $$M_X'(0) = \mu$$.

**Theorem** If $$\mathbb{X} \sim f$$ is a continuous random variable, let $$g(x, t) = e^{x t}f(x)$$.
1. There exists a closed interval $A$ such that $$0 \in A$$ and for all $$t \in A$$, $$M_X(t)$$ exist
2. For every $$\epsilon > 0$$ there exists $$\delta$$ such that $$| \mathrm{D}_t g(x, t) - \mathrm{D}_t g(x, s) | < \epsilon$$ for all $$x$$ and for all $$|s-t|\leq\delta$$

Then $$M_X'(0) = \mu$$.

**Proof to both** If the conditions are satisfied,
$$M_X'(0) = \frac{\mathrm{d}}{\mathrm{d} t}\mathbb{E}[e^{\mathbb{X}t}] |_{t=0} = \mathbb{E}[ \frac{\mathrm{d}}{\mathrm{d} t} e^{\mathbb{X}t}] |_{t=0} = \mathbb{E}[\mathbb{X}] = \mu$$
We can take the differentiation into expectation because the theorems in analysis tells us we can interchange differentiation with infinite summation or differentiation with integration if conditions 1, 2 are satisfied (See appendix for under what conditions are we allowed to do so).

**Definition** The nth moment of a random variable $$\mathbb{X}$$ is defined as $$\mathbb{E}[\mathbb{X}^n]$$

Reader should be able to varify that $$M_X^{(n)}(0) = \mathbb{E}[\mathbb{X}^n]$$ (under appropriate conditions), so that $$\sigma^2 = M_X''(0) - (M_X'(0))^2$$ provides a nother way tp caluculate variance via moment generating function.

**Theorem** Uniquess Property of Moment Generating Function.
$$M_X(t) = M_Y(t) \text{ if and only if } \mathbb{X}=\mathbb{Y}$$

This is the first theorem you encounter in this textbook that I shall not give it a proof. Because the proof concept is beyond basic analysis.



