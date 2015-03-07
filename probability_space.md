# Probability Space


Probability space is a three tuple
$$ \{ S, \Sigma,  \mathbb{P} \} $$

where $$S$$ is sample space, $$\Sigma\subseteq 2^S$$ is sigma algebra, and $$\mathbb{P}: \Sigma \to [0, 1]$$ is the probability function such that,

1. $$\mathbb{P}(\emptyset) = 0$$
2. Given $$A_1, A_2, ... \in \Sigma$$, if $$A_1, A_2, ...$$ are mutually exclusive 
 ( $$ \forall_{i\neq j} A_i \cap A_j = \emptyset$$ ) then $$\mathbb{P}( \cup_{n=0}^\infty A_n = \sum_{n=0}^\infty \mathbb{P}(A_n)$$

**Definition** We say two events A and B are independent if $$\mathbb{P}(A\cap B) = \mathbb{P}(A)\mathbb{P}(B)$$

This notion of independence is really the one thing that makes probability a different field of study from analysis. Note in general, $$\mathbb{P}(A\cap B) = \mathbb{P}(A)\mathbb{P}(B)$$ is not something as a result of a proof, it is usually assumed as premise of a problem, because independence gives probability many useful and convenient properties. 