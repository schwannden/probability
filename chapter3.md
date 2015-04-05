# Random Variable

Sometimes we are not so interested in the sample space, we are more interested in the numerical property of the sample space. For example, if you record the different kinds and number of eagles that fly over Taiwan each day, the sample space consists of some vectors denoting the eagles observed each day.

For example, on June 14th, we add something to the sample space, namely,

$$( Crested Goshawk, Spilornis Cheela, Spilornis Cheela, Crested Goshawk )$$

because we observed a Crested Goshawk, followed by two Spilornis Cheela, then Crested Goshawk again.

But we might not be interested in the exact form of the record. We might be interested in only how many Crested Goshawk are observed on each day.

So we need a way to bring us from sample space to real number, and that thing is called random variable.

** Definition ** 
$$ \mathbb{X} \text{ is a random variable (r.v) if } \mathbb{X}: S \to \mathbb{R} $$
such that

$$\forall_{t\in\mathbb{R}}\{\mathbb{X}\leq t\}\in \Sigma\ \ \ \ \ \ \ \ \ \ \ (2)$$

where

$$\{\mathbb{X} \leq t\} \text{ means the set } \{x \in \mathbb{S} | \mathbb{X}(x) \leq t\}$$

So a random variable is a function from sample space to real number. But not all functions from sample space to real number is random variable. We need to be able to ask certain questions about this random variable. 

condition (2) means: if $$\mathbb{X}$$ is a random variable, I can ask: what is the probability that something happen, and it's value is smaller than $$t$$. So (2) restricts on the kind of question we can ask about random variable.

Also (2) restrict on the kind of questions we can ask, as the following remark states, we actually can ask just about any question that's realistic.

** Remark **
Let $$\mathbb{X}$$ be a random variable

(a) For $$A \subset \mathbb{R}$$, we denote the set $$\{ \mathbb{X} = A \}$$ as $$\{ x \in S | \mathbb{X}(x) \in A \}$$. And if $$\{ \mathbb{X} = A \}\in\Sigma$$, we say $$A$$ is "measurable."

(b) It can be proved that, 

$$\forall_{t\in \mathbb{R}} \ \ \ \ \ \ \{\mathbb{X} < t \},\ \{\mathbb{X} \geq t \},\ \{\mathbb{X} > t \} \text{ are all measurable}$$

(c) With (b), condition (2), we can prove all elementary intervals, namely $$(a, b), (a, b], [a, b), [a, b]$$, and any countable union or intersection of them, are also measurable.

** Definition ** We say two random variables $$\mathbb{X}$$ and $$\mathbb{Y}$$ are independent if,

$$\forall_{A\text{ measurable } }\mathbb{P}( \{\mathbb{X} = A\} \cap \{\mathbb{Y} = A\} ) = \mathbb{P}(\mathbb{X} = A)\mathbb{P}(\mathbb{Y} = A)$$

** Definition ** We say two random variables $$\mathbb{X}$$ and $$\mathbb{Y}$$ are identical if 

$$\forall_{x\in S}\ \mathbb{X}(x) = \mathbb{Y}(x)$$

** Definition ** We say two random variables $$\mathbb{X}$$ and $$\mathbb{Y}$$ are independent, identical distribution if they are independent and identical, denoted i.i.d. This is an acronym that will appear throughout the whole text.

