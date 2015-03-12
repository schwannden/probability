# Joint Gaussion

**Definition** We say $$\mathbb{X_1}, ..., \mathbb{X_n}$$ are said to be **jointly Gaussian**, or have **multivariate normal distribution** if the joint moment generating function of $$\bar{\mathbb{X}}$$ has the following form:
$$M_{\bar{\mathbb{X}}}(\bar{t}) = e^{\bar{t}^{\ T}\mu} e^{\bar{t}^{\ T}A\bar{t}}$$
Where $$A$$ is symmetric positive semidefinite matrix.

**Theorem**
The random variables $$\mathbb{Y_1}, ..., \mathbb{Y_n}$$ are jointly Gaussian if and only if $$\mathbb{Y_1}, ..., \mathbb{Y_n}$$ arrives from nonsingular linear transformation of independent normal random variables $$\mathbb{X}_1, ..., \mathbb{X}_n$$. I.e., there exists nonsingular matrix $$A$$ such that 
$$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$
and
$$\mathbb{X}_i \sim normal(0, \lambda_i)$$

**proof** If $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$, then
$$M_{\bar{\mathbb{Y}}}(\bar{t}) = e^{\bar{t}^{\ T}\mu} \mathbb{E}[e^{\bar{t}^{\ T}A\bar{\mathbb{X}}}]$$
Let $$\bar{s}^T = \bar{t}^{\ T}A$$, note that
$$\mathbb{E}[e^{\bar{s}^T\bar{\mathbb{X}}}] = \prod_{i=1}^n\mathbb{E}[e^{s_i \mathbb{X}_i}] \text{ (because} \mathbb{X}_i's \text{ are independent)}$$
$$= \prod_{i=1}^n e^{-\frac{\lambda_i}{2}s_i^2} = e^{\bar{s}^T D \bar{s}} \text{ where } D = $$