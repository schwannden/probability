# Statistics

First recall the two definitions

**Definition**
Suppose we have a random variable with p.d.f $$f(x, \theta)$$ where $$\theta$$ is an unknown vector, we then call $\theta$ a parameter and the set of $\theta$'s possible values, denoted $$\Theta$$, is called the parameter space

**Definition**
For a random sample $$X_1, ..., X_n$$, any function $$g(X_1, X_2, ..., X_n): $$ independent of parameter $$\theta$$ is called a statistics.

Let $$\mathbb{X} \sim f$$ be a random variable, if we know p.d.f $$f$$, then we know everything we want with that random variable. The problem in statistics is that we have a random point from $$\{ f(x, \theta) | \theta\in\Theta \}$$ where function $f$ is known but parameter $$\theta$$ is unknown. Statistics wants to predict $$\theta$$. The method for predicting $\theta$ is called statistical inference. In the later text of this book, I shall refer "a random point from $$\{ f(x, \theta) | \theta\in\Theta \}$$" simply by "a random point from $$f(x, \theta)$$" for brevity.

Two kinds of statistical inference are called **estimation** and **hypothesis testing**. Estimation means we try to guess the value of $$\theta$$, hypothesis testing might not care about $$\theta$$, but test the the result of some experiment against the hypothesis. The key in hypothesis testing how sure can we know for certain, that the conclusion draw from the experiment is correct.

More formally, we categorize estimation into

(1) **Point estimate**: given $$X_1, ..., X_n$$, what is the function for estimating $$\theta$$ based solely on $$X_1, ..., X_n$$.

(2) **Interval estimate**: Given $$\alpha\in[0, 1]$$, find statistics $$T_1(X_1, ..., X_n)$$ and $$T_2(X_1, ..., X_n)$$ with $$\alpha = \mathbb{P}_{\theta}( T_1 \leq \theta \leq T_2 )$$

Point estimation is meaningless if we don't have interval estimation, because we need to be able to argue how good is the estimation. Put in other words, after point estimation gives us $$\hat{\theta}$$, we need interval estimation to tell us how close is this $$\hat{\theta}$$ compared to real $$\theta$$. That is what interval estimation does. Interval estimation introduces the notion of **confidence**. Confidence is the value $$\alpha$$ in (2). So interval estimation is, no matter how large is your confidence, we can tell you an interval such that the probability that $$\theta$$ lies within that interval is your confidence. This interval is called **confidence interval**. And of course, a good estimation has a smaller confidence interval for a given confidence.

And more formally, hypothesis testing is that given $$\theta_0 \subset \mathbb{R}$$ and hypothesis $$H: \theta \in \theta_0$$, find a rule to decide the acceptance of rejection of $$H$$. We will have more to say about interval estimation later.


