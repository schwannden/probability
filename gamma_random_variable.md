# Gamma random variable
## Introducing gamma function
**Definition** The $$gamma function$$ is defined as
$$\Gamma(x) = \int_0^{\infty} t^{x-1}e^{-t} \mathrm{d}t\ \ \ \ \ \ \ \ \ \ (1)$$
for all $$x > 0$$

Note that $$\Gamma$$ converge if and only if $$$x>0$, as the following analysis shows:

If $$x>0$$,
$$\lim_{t\rightarrow\infty} \frac{t^{x-1}e^{-t}}{e^{-t/2}} = 0$$

this means

$$ \exists_m \forall_{t\geq m}  t^{x-1}e^{-t} \leq {e^{-t/2}} $$

And by comparison test, $$\int_m^{\infty} t^{x-1}e^{-t} \mathrm{d}t$$ exists.

Now if $$x > 1$$,  $$\int_0^m t^{x-1}e^{-t} \mathrm{d}t$$ is just a definite integral, so $$\Gamma$$ converges for $$x>1$$. If $$x=1$$, $$\Gamma(1) = 1$$ by directly evaluating the indefinite integral.

If $$x<1$$, $$t^{x-1}e^{-t} \leq t^{x-1}$$, and we know $$\int_0^m t^{x-1} \mathrm{d}t$$ converges iff $$x-1>-1$$, i.e, $$x>0$$. By comparison test, we know $$\Gamma$$ converges for $$x>0$$.

If $$x=0$$, integration by part shows $$\Gamma$$ diverge, then comparison test can show that for all $$x<0$$ $$\Gamma$$ diverge.

**Some properties of $$\Gamma$$:**
1. for all $$0<x<\infty$$, $$\Gamma(x+1) = x\Gamma(x)$$
2. $$\Gamma(n+1) = n!$$
3. Convexity of $$\Gamma$$: $$\log \Gamma$$ is convex on $$(0, \infty)$$
We say a real function $$f$$ is convex on $$A$$ if and only if for every $$x, y\in A$$, and $$\lambda \in [0.1]$$, $$f(\lambda x + (1-\lambda)y) \leq \lambda f(x) + (1-\lambda)f(y)$$

(a) can be shown with integration by part, and (b) can be shown by first find out $$\Gamma(1)=1$$, then apply (a). for (c), we need Holder's inequality:

If $f$ and $$g$$ are Riemann integrable real functions on $$[a, b]$$, for any $$p$$, $$q$$ s.t $$\frac{1}{p} + \frac{1}{q} = 1$$
$$|\int_a^b fg\ \mathrm{d}\alpha| \leq {\int_a^b |f|^{\frac{1}{p}}\mathrm{d}\alpha}^p {\int_a^b |g|^{\frac{1}{q}}\mathrm{d}\alpha}^q\ \ \ \ \ \ \ \ \ \ (2) $$


With this inequality, 
$$\Gamma(\frac{x}{p} + \frac{y}{q}) = 
\int_0^\infty t^{\frac{x}{p} + \frac{y}{q} - 1}e^{-t} \mathrm{d}t = 
\int_0^\infty (t^\frac{x-1}{p}e^{-\frac{t}{p}}) (t^\frac{y-1}{q}e^{-\frac{t}{q}}) \mathrm{d}t \leq \Gamma(x) ^ {\frac{1}{p}} \Gamma(y) ^ {\frac{1}{q}}$$

Therefore
$$\log\Gamma( \frac{x}{p} + \frac{y}{q} ) \leq \frac{1}{p}\log\Gamma(x)+ \frac{1}{q}\log\Gamma(y)$$ 

Now it is actually very cool that these 3 properties uniquely determines $$\Gamma$$, as the following theorem shows.

**theorem 1** 
Let $$f$$ be a real function defined  on $$(0, \infty)$$, such that:

(a) for all $$0<x<\infty$$, $$f(x+1) = xf(x)$$ 

(b) $$f(1) = 1$$

(c) $$\log f$$ is convex on $$(0, \infty)$$

then $$f$$ is uniquely determined. This says, $$f$$ is $\Gamma$, since $\Gamma$ satisfies all three properties.

**proof** Let $$\varphi$ be $\log f$$. first note $$\varphi(x+1) = \varphi(x) + \log(x)$$. Since $$\varphi$$ is convex, 
$$\forall n \in \mathbb{N}\ \forall x \in (0, 1)$$
$$ \varphi(n+1)-\varphi(n) \leq\frac{\varphi(n+1+x)-\varphi(n+1)}{x} \leq\varphi(n+2) - \varphi(n+1) $$
$$\Rightarrow x \log(n) \leq \varphi(x) + \log x(x+1)...(x+n)-\log(n!) \leq x \log(n+1)$$
$$\Rightarrow 0 \leq \varphi(x) - \log( \frac{n^xn!}{x(x+1)...(x+n)}) \leq x \log( 1+\frac{1}{n} )$$

Now by squeezing theorem, $$\lim_{n \to \infty}\log( \frac{n^xn!}{x(x+1)...(x+n)}) = \varphi(x)$$ on $$(0, 1)$$.
By the continuity of $$\log$$,  $$\lim_{n \to \infty}\frac{n^xn!}{x(x+1)...(x+n)} = f(x)$$ on $$(0, 1)$$. And by (a), $$f(x)$$ is uniquely determined on $$(0, \infty)$$.

The by-product of this proof is that we know $$\frac{n^xn!}{x(x+1)...(x+n)} \to \Gamma(x)$$ point wise (at least) on $$(0, 1)$$. If we plug in x = 1, we find $$\frac{n n!}{(n+1)!} \to 1 = \Gamma(1)$$ too!

**Theorem 2** There is a relationship between gamma and beta function, namely
$$B(x, y) = \frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}$$

**proof** Note that $$B(1, y) = \frac{1}{y}$$ by direct integration. $$\ \ \ \ \ \ (3)$$

Also note,  $$B(x+1, y) = \int_0^1 t^{x}(1-t)^{y-1}\mathrm{d}t = \int_0^1 (\frac{t}{1-t})^{x}(1-t)^{x+y-1}\mathrm{d}t =$$
 (integration by part)
$$[\frac{-1}{x+y}t^x(1-t)^y]_{t=0}^1 + \int_0^1 \frac{x}{x+y}t^(x-1)(1-t)^(y-1) \mathrm{d}t = \frac{x}{x+y}B(x, y)$$
So $$B(x+1, y) = \frac{x}{x+y}B(x, y)\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (4)$$

For any $$p$$, $$q$$ such that $$\frac{1}{p} + \frac{1}{q} = 1$$, and for any $$x_1, x_2$$ such that $$\frac{x_1}{p} + \frac{x_2}{q}>0$$, we can apply Holder's inequality (equation (1))to obtain, 
$$B( \frac{x_1}{p} + \frac{x_2}{q}, y ) = \int_0^1 t^{\frac{x_1-1}{p}} (1-t)^{\frac{y-1}{p}} t^{\frac{x_2-1}{q}} (1-t)^{\frac{y-1}{q}}\mathrm{d}t $$
$$\leq {\int_0^1 t^{x_1-1} (1-t)^{y-1} \mathrm{d}t} ^ {\frac{1}{p}} {\int_0^1 t^{x_2-1} (1-t)^{y-1}\mathrm{d}t}^{\frac{1}{q}} = B(x_1, y)^{\frac{1}{p}}B(x_2, y)^{\frac{1}{q}}$$

so $$\log B$$ is convex with respect to x.$$\ \ \ \ \ \ \ \ (5)$$

Now for every y fixed, let $$f(x) = \frac{\Gamma(x+y)}{\Gamma(y)}B(x, y)$$
By (5), and convexity of $$\log \Gamma$$, $$\log f$$ is also convex. Also, $$\ \ \ \ \ \ \ \ \ \ (6)$$

$$f(1) = \frac{\Gamma(1+y)}{\Gamma(y)}B(1, y) \stackrel{by (3)}{=} y\frac{\Gamma(y)}{\Gamma(y)}\frac{1}{y} = 1\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ (7)$$

and 

$$f(x+1) = (x+y)\frac{\Gamma(x+y)}{\Gamma(y)}B(x+1, y) \stackrel{by (4)}{=} xf(x) \ \ \ \ \ \ \ \ (8)$$

By \textbf{theorem 1}, (6), (7), and (8) shows $$f(x) = \Gamma(x) = \frac{\Gamma(x+y)}{\Gamma(y)}B(x, y)$$, so $$B(x, y) = \frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}$$

## Gamma distribution
**Definition** We say a continuous r.v $$\mathbb{X}$$ is a gamma r.v with parameters $$\lambda, \alpha$$, denoted $$\mathbb{X} \sim gamma(\lambda, \alpha)$$, if
$$
 \mathbb{X} \sim f(x) =
  \begin{cases}
   \frac{1}{\Gamma(\alpha)}\lambda(\lambda x)^{\alpha-1}e^{-\lambda x} & \text{if } x > 0 \\
   0       & otherwises
  \end{cases}
$$

**Property** If $$\mathbb{X} \sim gamma(\alpha, \lambda)$$, $$\mu = \frac{\alpha}{\lambda}, \sigma^2 = \frac{\alpha}{\lambda^2}$$

**Proof 1** By definition

**Proof 2** By moment generating function
First note that $$D_t f(x)e^{xt} = \frac{1}{\Gamma(\alpha)}\lambda x(\lambda x)^{\alpha-1}e^{(t-\lambda) x}$$ is continuous on $$(-\lambda, \lambda ) \times [0, \infty)$$, we can apply m.g.f method.

The moment generating function
$$M_x(t) = \mathbb{E}[e^{\mathbb{X}t}] = \int_0^\infty \frac{1}{\Gamma(\alpha)} \lambda (\lambda x)^{\alpha-1} e^{(t-\lambda)x} \mathrm{d}x $$
$$= \frac{\lambda^\alpha}{(\lambda-t)^\alpha}\int_0^\infty \frac{1}{\Gamma(\alpha)} (\lambda-t) ((\lambda-t) x)^{\alpha-1} e^{(t-\lambda)x} \mathrm{d}x = (\frac{\lambda}{\lambda-t})^\alpha$$

There is a connection between gamma and Poisson r.v that often appears in the analysis of computer networks, namely:

**Theorem** 
If $$\mathbb{N} \sim poisson(\lambda t)$$ be the number of events happen during time $$[0, t]$$, let $$T_n$$ denote the time it takes for the nth event to happen, then $$T_n \sim gamma(n, \lambda)$$

**proof** $$T_n \sim F_n(t) = \mathbb{P}( \mathbb{N} \geq n ) = \sum_{k=n}^\infty \frac{(\lambda t)^k}{k!}e^{-\lambda t}$$ because the time at which nth event happens $$\leq t$$ if and only if $$\geq$$ n events happened in $$[0, t]$$. We can differentiate a power series by differentiating it term by term as long as $$x$$ lies in the radius of convergence. I.e, if $$\sum f_n(x) $$ converges in an open disk containing x, then $$ \frac{\mathrm{d}}{\mathrm{d} x} ( \sum f_n(x) ) = \sum f'_n(x) $$. Since radius of convergence for $$\sum_{k=n}^\infty \frac{(\lambda t)^k}{k!}e^{-\lambda t}$$ is $$\infty$$, we know

$$f_n(t) = F'_n(t) = \sum_{k=n}^\infty \lambda\frac{(\lambda t)^{k-1}}{(k-1)!}e^{-\lambda t}  - \sum_{k=n}^\infty \lambda\frac{(\lambda t)^k}{k!}e^{-\lambda t} = \lambda\frac{(\lambda t)^{n-1}}{(n-1)!}e^{-\lambda t} \sim gamma(n, \lambda)$$


