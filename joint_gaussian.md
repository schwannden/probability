# Joint Gaussian

**Definition** We say $$\mathbb{X}_1, ..., \mathbb{X}_n$$ are said to be **jointly Gaussian**, or have **multivariate normal distribution** if the joint moment generating function of $$\bar{\mathbb{X}}$$ has the following form:
$$M_{\bar{\mathbb{X}}}(\bar{t}) = e^{\bar{t}^T\mu} e^{\frac{1}{2}\bar{t}^TK\bar{t}}\ \ \ \ \ \ \ \ \ \ \ \ \ \ (1)$$
Where $$K$$ is symmetric positive definite matrix.

#### Alternative Derivation
**Theorem**
The random variables $$\mathbb{Y}_1, ..., \mathbb{Y}_n$$ are jointly Gaussian if and only if $$\mathbb{Y}_1, ..., \mathbb{Y}_n$$ arrives from nonsingular linear transformation of independent normal random variables $$\mathbb{X}_1, ..., \mathbb{X}_n$$. I.e., there exists nonsingular matrix $$A$$ such that 
$$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}\ \ \ \ \ \ \ \ \ \ \ (2)$$
and
$$\mathbb{X}_i \sim normal(0, \lambda_i)$$

**proof** 

($$\Leftarrow$$) If $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$, then
$$M_{\bar{\mathbb{Y}}}(\bar{t}) = e^{\bar{t}^{\ T}\mu} \mathbb{E}[e^{\bar{t}^{\ T}A\bar{\mathbb{X}}}]$$
Let $$\bar{s}^T = \bar{t}^{\ T}A$$, note that
$$\mathbb{E}[e^{\bar{s}^T\bar{\mathbb{X}}}] = \prod_{i=1}^n\mathbb{E}[e^{s_i \mathbb{X}_i}] \text{ (because} \mathbb{X}_i's \text{ are independent)}$$
$$= \prod_{i=1}^n e^{\frac{\lambda_i}{2}s_i^2} = e^{\frac{1}{2}\bar{s}^T D \bar{s}} \text{ where } D = \left[ \begin{array}{ccc}
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{array} \right] $$
So
$$\mathbb{E}[e^{\bar{t}^{\ T}A\bar{\mathbb{X}}}] = e^{\frac{1}{2}\bar{t}^{\ T}ADA^T\bar{t}}$$
Now it remains to show that $$ADA^T$$ is symmetric, positive definite.
1. $$ADA^T$$ is symmetric because $$D$$ is diagonal (the proof is trivial).
2. For all $$\bar{t}$$, we have $$\bar{t}^{\ T}ADA^T\bar{t} = \sum_{i=1}^n s_i^2 \lambda_i \geq 0$$, and note that $$\bar{t}^{\ T}ADA^T\bar{t} = 0$$ iff $$A^T\bar{t} = 0$$ iff $$\bar{t} = 0$$ because $$A$$ is nonsingular. So $$ADA^T$$ is positive definite.

($$\Rightarrow$$) Now if
$$M_{\bar{\mathbb{Y}}}(\bar{t}) = e^{\bar{t}^{T}\mu} e^{\frac{1}{2}\bar{t}^{T}K\bar{t}} \text{, where $$K$$ is symmetric positive definite matrix}$$

Since $$K$$ is symmetric positive definite, it can be diagonalized into $$ADA^{-1}$$, where $$A$$ is orthonormal matrix (i.e, $$A$$ has $$n$$ linearly independent eigenvectors). But since $$A$$ is orthonormal, $$A^{-1} = A^T$$. Now let 
$$\bar{\mathbb{X}} = A^T(\bar{\mathbb{Y}}-\bar{\mu})$$

We want to show that $$\mathbb{X}_i \sim normal(0, \lambda_i)$$

$$M_{\bar{\mathbb{X}}}(\bar{t}) = e^{-\bar{t}^T A^T \bar{\mu}}\mathbb{E}[e^{\bar{t}^TA^T\bar{\mathbb{Y}}}]$$
Notice that $$\mathbb{E}[e^{\bar{t}^TA^T\bar{\mathbb{Y}}}] = M_{\bar{\mathbb{Y}}}(A\bar{t})$$, so
$$\mathbb{E}[e^{\bar{t}^TA^T\bar{\mathbb{Y}}}] = e^{\frac{1}{2}\bar{t}^TA^T\bar{\mu}}e^{\bar{t}^TA^TKA\bar{t}}$$
and
$$M_{\bar{\mathbb{X}}}(\bar{t}) = e^{\frac{1}{2}\bar{t}^TA^TKA\bar{t}} = e^{\bar{t}^TD\bar{t}} = \prod_{i=1}^n e^\frac{\lambda_i^2}{2} $$

Therefore $\mathbb{X}_i$'s are independent normal, and $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$.

#### Covariance

**Theorem** Let $$\bar{\mathbb{Y}} = A\bar{\mathbb{X}} + \bar{\mu}$$ be jointly Gaussian as in (2), and $$K$$ be a symmetric positive definite matrix as in (1). $$K$$ is the covariance matrix of $$\bar{\mathbb{Y}}$$

**Proof** First note that 
$$\mathbb{E}[\bar{\mathbb{Y}}] = A\mathbb{E}[\bar{\mathbb{X}}]+\bar{\mu} = \bar{\mu}$$
So the covariance matrix of $$\bar{\mathbb{Y}}$$ is
$$\mathbb{E}[(\bar{\mathbb{Y}}-\bar{\mu})(\bar{\mathbb{Y}}-\bar{\mu})^T] = \mathbb{E}[A\mathbb{X}\mathbb{X}^TA^T] = A\mathbb{E}[\mathbb{X}\mathbb{X}^T]A^T = ADA^T = K$$

#### Density Function

**Theorem** Let $$\bar{\mathbb{Y}}$$ be jointly Gaussian as in (2) and $$K$$ be a symmetric positive definite matrix as in (1). The joint density function of $$\bar{\mathbb{Y}}$$ is
$$f_\bar{\mathbb{Y}}(\bar{y}) = \frac{1}{\sqrt{(2\pi \det K)^n }} e^{-\frac{1}{2}(\bar{y} - \bar{\mu})^T K^{-1} (\bar{y} - \bar{\mu})} $$

**Proof** 

Let $$D$$ is the diagonal matrix mentioned above.
$$f_\bar{\mathbb{X}}(\bar{x}) = \frac{1}{\sqrt{(2\pi)^n }\sqrt{\lambda_1 \cdots \lambda_n}} e^{-\frac{1}{2}\bar{x}^T D^{-1} \bar{x}} $$
And note that 
$$\det K = \det ADAT = \det D = \lambda_1 \cdots \lambda_n$$ 
Because $$A$$ is orthonormal (hence $$\det A = \pm 1$$). Also, $$\bar{\mathbb{X}} = A^T(\bar{\mathbb{Y}}-\bar{\mu})$$, so
$$f_\bar{\mathbb{Y}}(\bar{y}) = \frac{1}{\sqrt{(2\pi \det K)^n }} e^{-\frac{1}{2}(\bar{y} - \bar{\mu})^T AD^{-1}A^T (\bar{y} - \bar{\mu})} \det A^T$$
And since this is probability density function, $$\det A^T = 1$$.