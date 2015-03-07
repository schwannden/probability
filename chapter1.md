# The Notion of Relative Frequency

The notion of relative frequency can be treated as our starting point of understanding probability. If an experiment has some possible outcomes, but we don't know which outcome will happen (often this property is called "undetermined"). Now how do we define the probability that a particular outcome occur?

One approach is called relative frequency. If we repeat the experiment independently for N times, and obtain our first relative frequency $$f_1$$

$$f_1 = \frac{\text{number of times a particular event happen}}{N}$$

It is hoped that, if we calculate this repeatedly, with $$f_n$$ be the nth relative frequency, $$\lim_{n\to\infty}\frac{\sum_{i=1}^n f_i}{n} \text{ will converge to a number p}$$. We call this $$p$$ the probability that this particular event happen.

This approach is very intuitive, but the difficulty with this approach is its ambiguity in many aspects, for example:

1. How large should N be?
2. How do we know if the limit exists?
3. How do we know if the limit converges to a single point of a set of point?
4. How fast will relative frequency converge? If it converges too slow, is it still probability?

Relative frequency is a good idea, but it is hard to make precise when it comes to proving things mathematically. This is why we need the axiomatic approach ---- we no longer care about the meaning of probability, but the consequence of probability. We no longer ask what is probability, we ask if something has a probability, what properties will this probability have?

This way of studying probability is called an **axiomatic** approach. It has become a very popular approach for mathematicians to solve problems. You define the consequences of something (called **axioms**), and if you think these consequences make sense, you derive everything from these simple and basic facts. Physicists use this approach too, but in their world they call it **laws**, like the three laws of Newton. You can not explain it, you simply accept it. And if one day, a brilliant person find these laws (axioms) unacceptable, and came up with a whole new set of laws (axioms) that explain the world better, then bravo! We got ourselves another Einstein!

An important thing to realize at first is, even though we take the axiomatic approach in this book (rather than a philosophical approach), in the very end, these axioms can prove a theorem called **the law of large number**. The law of large number basically says that relative frequency will indeed converge to probability. So these axioms **make sense**!