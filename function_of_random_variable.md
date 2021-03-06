# Function of Random Variable

Let $$\mathbb{X}$$ be a random variable, and $$\mathbb{Y} = g(\mathbb{X})$$ is a real valued function of $$\mathbb{X}$$.

**example 1**
If $$\mathbb{X} \sim normal(\mu, \sigma^2)$$, then $$\mathbb{Y} = \frac{\mathbb{X}-\mu}{\sigma} \sim normal(0, 1)$$.

**proof 1** For the following proof, we appeal to c.d.f. Let $$\mathbb{X} \sim F_X$$ and $$\mathbb{Y} \sim F_Y$$, then
$$F_Y(y) = \mathbb{P}( \frac{\mathbb{X}-\mu}{\sigma} \leq y ) = \mathbb{P}( \mathbb{X} \leq \sigma y + \mu ) = F_X( \sigma y + \mu )$$
$$\Rightarrow f_Y(y) = F_Y'(y) = \frac{\mathrm{d}}{\mathrm{d}y}F_X( \sigma y + \mu ) = \sigma f_X(  \sigma y + \mu ) = \frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}$$

**proof 2** For the following proof, we appeal to m.g.f. Let $$\mathbb{X} \sim F_X$$ and $$\mathbb{Y} \sim F_Y$$, then
$$M_X(t) = \mathbb{E}[e^{tX}] = e^{\mu t + \frac{\sigma^2}{2}t^2}$$
$$M_Y(t) = \mathbb{E}[e^{t\frac{X-\mu}{\sigma}}] = e^\frac{-\mu t}{\sigma} \mathbb{E}[ e^\frac{tX}{\sigma}] = 
e^\frac{-\mu t}{\sigma}e^{\mu \frac{t}{\sigma} + \frac{\sigma^2}{2}(\frac{t}{\sigma})^2} = e^\frac{t^2}{2}$$

And by the uniqueness property of moment generating function
$$\mathbb{Y} \sim normal(0, 1)$$

**example 2**
If $$\mathbb{X} \sim gamma(\alpha, \lambda)$$, then $$\mathbb{Y} = 2 \lambda \mathbb{X} \sim \chi(2 \alpha)$$.

**proof 1**
Let $$\mathbb{X} \sim gamma(\alpha, \lambda)$$,  $$\mathbb{Y} = 2 \lambda \mathbb{X}$$
$$f_Y(y) = F_Y'(y) = \frac{\mathrm{d}}{\mathrm{d}y} \mathbb{P}( \mathbb{X} \leq \frac{y}{2 \lambda} ) = \frac{\mathrm{d}}{\mathrm{d}y} F_X( \frac{y}{2 \lambda} ) = \frac{1}{2 \lambda} f_X( \frac{y}{2 \lambda} )$$
$$= C (\frac{y}{2})^{\alpha-1} e^{-\frac{y}{2}} \sim \chi^2(2\alpha)$$

**proof 2**
Let $$\mathbb{X} \sim gamma(\alpha, \lambda)$$,  $$\mathbb{Y} = 2 \lambda \mathbb{X}$$
$$M_X(t) = \mathbb{E}[e^{tX}] = (1-\frac{t}{\lambda} )^{-\alpha}$$
$$M_Y(t) = \mathbb{E}[e^{2 \lambda t \mathbb{X}}] = (1-2 t)^{-\alpha}$$
so
$$Y \sim gamma(\frac{1}{2}, \frac{2\alpha}{2}) = \chi^2(2\alpha)$$



