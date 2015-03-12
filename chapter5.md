# Joint Distribution

It is reasonable that sometimes we are interested in more than one r.v (for example, the price of a meal and the degree of satisfaction it will give you).

For any n random variables $$X_1, X_2, ..., X_n$$, let $$\bar{X} : S \to \mathbb{R}^n$$ be a function s.t $$\bar{X}(s) = (X_1(s), X_2(s), ..., X_n)$$.  $$\bar{X}$$ is called a random vector of these n random variables. We call the p.d.f (c.d.f) of $$F_{\bar{X}}$$ the joint c.d.f (p.d.f) of $$(X_1(s), X_2(s), ..., X_n)$$.

If the range of $\bar{X}$ is discrete, $X_1, X_2, ..., X_n$ are discrete random variables with joint p.m.f
$$f_{\bar{X}}(\bar{x}) = \mathbb{P}( X_1 = x_1, X_2 = x_2, ..., X_n = x_n )\text{ , where }\bar{x} = (x_1, x_2, ..., x_n) \in \mathbb{R}^n $$
and joint c.d.f
$$F_{\bar{X}}(\bar{x}) = \mathbb{P}( X_1 \leq x_1, X_2 \leq x_2, ..., X_n \leq x_n )$$
Note that $\bar{X}$ is discrete iff $X_1, X_2, ..., X_n$ are discrete. But if $\bar{X}$ is not discrete, it is not necessary that all of $X_i's$ are continuous. And if some $X1_i$'s are discrete while the others are continuous, it can be proved that joint distribution does not exist for $\bar{X}$. So in order to have a continuous random vector, All of $X_i's$ must be continuous.

If $X_1, X_2, ..., X_n$ are continuous, there is $f_{\bar{X}}(\bar{x}) \geq 0$ such that joint c.d.f
$$F_{\bar{X}}(\bar{x}) = \mathbb{P}( X_1 \leq x_1, X_2 \leq x_2, ..., X_n\leq x_n ) = \int_{-\infty}^{x_1}\int_{-\infty}^{x_2}...\int_{-\infty}^{x_n} f_{\bar{X}}(\bar{x}) \mathrm{d}x_n ... \mathrm{d}x_2 \mathrm{d}x_1$$


