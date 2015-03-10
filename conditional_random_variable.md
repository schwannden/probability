# Conditional Random Variable

Just like in probability, We want to see what happens if probability of an event is conditioned on some other event, we want to know about conditioning random variable.
First thing first, ** conditional random variable is random variable! **

** Definition ** Let $$\mathbb{X}, \mathbb{Y}$$ be two random variable. When we say the conditional random variable of $$\mathbb{X}$$ given $$\mathbb{Y} = y$$, denoted by $$\mathbb{X}|{\mathbb{Y}=y} $$, we mean the random variable that has the following c.d.f:

$$F_{X|Y}(x|Y=y) = \frac{\mathbb{P}( \{\mathbb{X} \leq x\} \cap \{\mathbb{Y} = y\} )}{\mathbb{P}(\mathbb{Y} = A)} $$

And we call this $$F_{X|Y}(x|Y=y)$$ the conditional c.d.f of $$\mathbb{X}$$ given $$\mathbb{Y} = y$$

In chapter 4, we will see if two random variables has joint c.d.f, there is a formula for calculating $$F_{X|Y}$$.


