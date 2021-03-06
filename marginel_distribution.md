# Marginal Distribution
If random vector $$\bar{X}$$ has a joint c.d.f $$F_{\bar{X}}(\bar{x})$$, denoted $$\bar{X} \sim F_{\bar{X}}(\bar{x})$$ then each of $$X_i's$$ has a p.d.f (p.m.f) and c.d.f called \textbf{marginal p.d.f}( denoted $$f_{X_i}$$ ) and \textbf{marginal c.d.f}( denoted $$F_{X_i}$$ ).
$$F_{X_i}(x) = 
  \begin{cases}
   \sum_{\bar{x} | \bar{x_i} \leq x} f_{\bar{X}}(\bar{x})  & \text{if }\bar{X}\text{ is discrete} 
   \int_{-\infty}^{\infty}... \int_{-\infty}^{x_i}...\int_{-\infty}^{\infty} f_{\bar{X}}(\bar{x}) \mathrm{d}x_n ...\mathrm{d}x_i...\mathrm{d}x_1 & \text{if }\bar{X}\text{ is continuous}
  \end{cases}
$$
$$f_{X_i}(x) = 
  \begin{cases}
   \sum_{\bar{x} | \bar{x_i} = x} f_{\bar{X}}(\bar{x})  & \text{if }\bar{X}\text{ is discrete} 
   F_{X_i}'(x) & \text{if }\bar{X}\text{ is continuous}
  \end{cases}
$$

If you recall the definition of independent random variable, you'll see that if $$X_1, X_2, ..., X_n$$ are independent random variable, the joint c.d.f. and p.d.f can be calculate as term-by-term product, i.e, 
$$F_{\bar{X}}( \bar{x} ) = F_{X_1}(x_1)F_{X_2}(x_2)...F_{X_n}(x_n)$$
$$f_{\bar{X}}( \bar{x} ) = f_{X_1}(x_1)f_{X_2}(x_2)...f_{X_n}(x_n)$$


