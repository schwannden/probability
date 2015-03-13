# Joint Gaussian

**Definition** We say $$\mathbb{X_1}, ..., \mathbb{X_n}$$ are said to be **jointly Gaussian**, or have **multivariate normal distribution** if the joint moment generating function of $$\bar{\mathbb{X}}$$ has the following form:
$$M_{\bar{\mathbb{X}}}(\bar{t}) = e^{\bar{t}^{T}\mu} e^{\bar{t}^{T}K\bar{t}}\ \ \ \ \ \ \ \ \ \ \ \ \ \ (1)$$
Where $$K$$ is symmetric positive semidefinite matrix.

#### Alternative Derivation
**Theorem**
The random variables $$\mathbb{Y_1}, ..., \mathbb{Y_n}$$ are jointly Gaussian if and only if $$\mathbb{Y_1}, ..., \mathbb{Y_n}$$ arrives from nonsingular linear transformation of independent normal random variables $$\mathbb{X}_1, ..., \mathbb{X}_n$$. I.e., there exists nonsingular matrix $$A$$ such that 
$$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}\ \ \ \ \ \ \ \ \ \ \ (2)$$
and
$$\mathbb{X}_i \sim normal(0, \lambda_i)$$

**proof** If $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$, then
$$M_{\bar{\mathbb{Y}}}(\bar{t}) = e^{\bar{t}^{\ T}\mu} \mathbb{E}[e^{\bar{t}^{\ T}A\bar{\mathbb{X}}}]$$
Let $$\bar{s}^T = \bar{t}^{\ T}A$$, note that
$$\mathbb{E}[e^{\bar{s}^T\bar{\mathbb{X}}}] = \prod_{i=1}^n\mathbb{E}[e^{s_i \mathbb{X}_i}] \text{ (because} \mathbb{X}_i's \text{ are independent)}$$
$$= \prod_{i=1}^n e^{-\frac{\lambda_i}{2}s_i^2} = e^{\bar{s}^T D \bar{s}} \text{ where } D = \left[ \begin{array}{ccc}
\lambda_1 & \cdots{} & 0\\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{array} \right] $$
So
$$\mathbb{E}[e^{\bar{t}^{\ T}A\bar{\mathbb{X}}}] = e^{\bar{t}^{\ T}ADA^T\bar{t}}$$
Now it remains to show that $$ADA^T$$ is symmetric, positive definite.
1. $$ADA^T$$ is symmetric because $$D$$ is diagonal (the proof is trivial).
2. For all $$\bar{t}$$, we have $$\bar{t}^{\ T}ADA^T\bar{t} = \sum_{i=1}^n s_i^2 \lambda_i \geq 0$$, and note that $$\bar{t}^{\ T}ADA^T\bar{t} = 0$$ iff $$A^T\bar{t} = 0$$ iff $$\bar{t} = 0$$ because $$A$$ is nonsingular. So $$ADA^T$$ is positive definite.

#### Covariance

**Theorem** Let $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$ be jointly Gaussian as in (2), and $$K$$ be a symmetric positive definite matrix as in (1). $$K$$ is the covariance matrix of $$\$$

**Proof** First note that 
$$\mathbb{E}[\bar{\mathbb{Y}}] = A\mathbb{E}[\bar{\mathbb{X}}]+\bar{\mu} = \bar{\mu}$$
So the covariance matrix of $$\bar{\mathbb{Y}}$$ is
$$\mathbb{E}[(\bar{\mathbb{Y}}-\bar{\mu})(\bar{\mathbb{Y}}-\bar{\mu})^T] = \mathbb{E}[A\mathbb{X}\mathbb{X}^TA^T] = A\mathbb{E}[\mathbb{X}\mathbb{X}^T]A^T = ADA^T = K$$