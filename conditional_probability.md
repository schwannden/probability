# Conditional Probability

First thing first, **conditional probability is probability!** As you will next see.

**Definition** Given probability space $$\{ S, \Sigma,  \mathbb{P}\}$$. let $$A, B$$ be two event in $$\Sigma$$. When we say the conditional probability of A given B, denoted by $$\mathbb{P}(A|B) $$, we mean the following value

$$\mathbb{P}(A\cap B)/\mathbb{P}(B)$$


So the conditional probability given B means the following function:

$$\mathbb{P}(x|B): \Sigma \to [0, 1] \text{ such that } \mathbb{P}(x|B) = \mathbb{P}(x\cap B)/\mathbb{P}(B)$$

Given this definition of conditional probability, we see:
1. $$\mathbb{P}(\emptyset|B) = \mathbb{P}(\emptyset\cap B)/\mathbb{P}(B) = \mathbb{P}(\emptyset)/\mathbb{P}(B) = 0$$
2. Given $$A_1, A_2, ... \in \Sigma$$, if $$A_1, A_2, ...$$ are mutually exclusive,

$$\mathbb{P}( \cup_{n=0}^\infty A_n |B ) = \mathbb{P}( (\cup_{n=0}^\infty A_n) \cap B ) /  \mathbb{P}(B)= \mathbb{P}( \cup_{n=0}^\infty (A_n \cap B) ) /  \mathbb{P}(B)$$

$$= \cup_{n=0}^\infty \mathbb{P} ( A_n \cap B ) / \mathbb{P}(B) = \sum_{n=0}^\infty \mathbb{P}(A_n | B)$$

So again, **conditional probability is probability!**

With the notion of conditional probability, we can define the notion of independence for events.


**Definition** We say A and B are independent if $$\mathbb{P}(A \cap B) = \mathbb{P}(A) \mathbb{P}(B)$$

**Remark**
* If $$A$$ and $$B$$ are independent event, $$\mathbb{P}(A|B) = \mathbb{P}(A)$$ which is very intuitive, because the probability of $$A$$ has nothing to do with B.
* Even if $$A \cap B = \emptyset$$, $$A, B$$ might not be independent.
* When $$\mathbb{P}(B) = 0$$, how we define $$\mathbb{P}(x|B)$$ is up the application. It's like it is meaningless to define what is $$0^0$$ unless we are under some application.