# Sigma Algebra

Before delving into the axioms of probability, we need to introduce sigma algebra and why we need it.

Let $$S$$ be a sample space, and an event is a subset of $$S$$. We know probability is a function that maps subset (event) of $$S$$ to [0,1]. But just what subsets are defined? i.e, what subsets are in the domain of probability function.

**Definition** Let $S$ be a set, and $\Sigma$ is a collection of subsets of $S$.  $\Sigma$ is a sigma algebra  iff
1. There exits some $A \subseteq S$ such that $A\in\Sigma$
2. If $$A \in \Sigma$$, then $$A^c \subset \Sigma$$
3. If $$A_1, A_2, ... \in \Sigma$$, then $$\cup_{n=1}^\infty \in \Sigma$$

Now we say this $$\Sigma$$ is the domain of probability function.

**Remarks**
* $2^S$ is obviously a sigma algebra
* All sigma algebra of $S$ is a subset of $$2^S$$
* For property 1 of sigma algebra, we can change it to: $$\emptyset \in \Sigma$$
* If $$A_1, A_2, ... \in \Sigma$$, then $$\cap_{n=1}^\infty \in \Sigma$$. This can be proved inductively

The purpose of $$\Sigma$$ is that it guarantees the existence of some normal operations of probability. For example, if $$\mathbb{P}$$ is a probability function, $\$mathbb{P}(A)$$ and $$\mathbb{P}(B)$$ exists, one would hope we can find $$\mathbb{P}(A \cup B)$$ by

$$\mathbb{P}(A \cup B) = \mathbb{P}(A) +  \mathbb{P}(B) - \mathbb{P}(A \cap B) \ \ \ \ \ \ \ \ \ \ \ \ (1)$$

The proof that you can find $$\mathbb{P}(A \cup B)$$ by (1) is easy once you assume the existence of $$\mathbb{P}(A \cap B)$$, but the existence of $$\mathbb{P}(A \cap B)$$ is often not guaranteed (i.e, $$(A \cap B)$$ might not be in the domain of $$\mathbb{P}$$ ). For example, given a dice, I tell you the probability of throwing out 1 or 3 or 4 is 0.1, and  the probability of throwing out 2 or 3 or 4 is 0.2, can you tell me the probability of throwing out 3 or 4? Of course not (I said of course, but you can prove it more rigorously by yourself)! The properties of sigma algebra guaranteed the existence of such probability, so we can freely use those classical operations about probability.