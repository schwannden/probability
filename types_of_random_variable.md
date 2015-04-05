# Types Of Random Variable

Some times we want to know the probability when a random variable have a certain value. For example, if you toss a coin, and we let $$\mathbb{X}$$ be a random variable such that it is 1 if the coin is head, and 0 otherwise. It is fairly understandable that we would want to know $$\mathbb{P}(\mathbb{X} = 1)$$ or $$\mathbb{P}(\mathbb{X} = 0)$$. But sometimes it is not so intuitive to tell people the exact meaning of $$\mathbb{P}(\mathbb{X} = a)$$, where $$a$$ is some constant. For example, if you are predicting tomorrow's average temperature, what is the probability that it will be exactly 20 degree Celsius? Supposedly it is very unlikely because it might be 20.0000001, 19.9999999 or 
maybe some other not-so-close answer. But you won't say it is impossible either, because there is always a chance that it turns out to be exactly 20 degree. The problem here, is that this random variable (tomorrow's average temperature) takes on infinitely many values. Although some values are more likely than the others, every single point is very unlikely.

This is when we need to distinguish very clearly the two kind of different random variables, discrete and continuous. And we use different approaches to define what does it mean by $$\mathbb{P}(\mathbb{X} = a)$$.

