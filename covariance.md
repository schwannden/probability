# Covariance, Variance of Sums, and Correlations

**Definition** Let $$\mathbb{X}, \mathbb{Y}$$ be two random variables. The **covariance** of $$\mathbb{X}, \mathbb{Y}$$ is defined as
$$\mathbb{E}[(\mathbb{X} - \mathbb{E}[\mathbb{X}])(\mathbb{Y} - \mathbb{E}[\mathbb{Y}])]$$

Simple rearrangement shows $$cov( \mathbb{X}, \mathbb{Y} ) = \mathbb{E}[\mathbb{X}\mathbb{Y}] - \mathbb{E}[\mathbb{X}]\mathbb{E}[\mathbb{Y}]$$

**Definition** the **correlation** of $$\mathbb{X}, \mathbb{Y}$$, $$\rho_{XY}$$ is
$$\frac{cov( \mathbb{X}, \mathbb{Y} )}{\sqrt{var(X)}\sqrt{var(Y)}}$$

**Property** or covariance
1.  if $$\mathbb{X}$$ and $$\mathbb{Y}$$ are independent, $$cov( \mathbb{X}, \mathbb{Y} ) = 0$$
2. $$var(\sum_{i=1}^n X_i) = \mathbb{E}[(\sum_{i=1}^n X_i - \mathbb{E}[\sum_{i=1}^n X_i])^2]$$
$$= \sum_{i=1}^n \mathbb{E}[ (X_i - \mathbb{E}[X_i])^2 ] - \sum_{i!=j}\mathbb{E}[ (\mathbb{X}_i - \mathbb{E}[\mathbb{X}_i])(\mathbb{X}_j - \mathbb{E}[\mathbb{X}_j]) ]$$
$$= \sum_{i=1}^n var(X_i) + 2 \sum_{i<j}cov(X_i, X_j)$$
3. By (b), if $$X_1, ..., X_n$$ are independent, $$var(\sum_{i=1}^n X_i) = \sum_{i=1}^n var(X_i)$$


