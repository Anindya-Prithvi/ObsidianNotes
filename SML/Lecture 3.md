# Lecture tHr33
More revision. 
## Covariance 
$$cov[x,y] = \mathbb E_{x,y} [\{x-\mathbb E[x]\}\{y^T-\mathbb E[y^T]\}]$$
so we define it for only one variable $X$,
$cov(X)=\frac{1}{N-1}\displaystyle\sum_{i=1}^N[X_i-\mu_X][X_i-\mu_X]^T$
where $\mu_X=\mathbb E[x]\in\mathbb R^{d\times1}$

## The Gaussian Distribution
$$\mathcal{N}(x|\mu,\sigma^2)=\dfrac{1}{\sqrt{2\pi\sigma^2}}e^{-\dfrac{(x-\mu)^2}{2\sigma^2}}$$

Looks like everyone is a fan of `$\mathcal$`
Here, $\mathbb E[x]=\mu, \operatorname{var}[x]=\sigma^2$

But in this non-binary world there are a lot of things. Presenting multivariate Gaussian (duh)

$$\mathcal{N}(x|\mu,\Sigma^2)=\dfrac{1}{(2\pi)^\frac{D}{2}|\Sigma|^{\frac12}}e^{-\dfrac{\overbrace{(x-\mu)^T}^{1\times d}\Sigma^{-1}(x-\mu)}{2}}$$

where obviously $\Sigma=cov(X)$

When $d>N, \Sigma$ is not a full rank matrix (max $N$). So $\Sigma^{-1}$ PSD.

- $r^2=(x-\mu)^T\Sigma{-1}(x-\mu)$ is called a Mahalanobis distance from $x$ to $\mu$. Imagine.
- volume of hyperellipsoid corresponding to a Mahalanobis distance $r$  
  $V=V_d|\Sigma|^{\frac12}r^d$ where $V_d$ is the volume of a $d$-dimensional unit-hemisphere.
- Higher the determinant for a fixed $r$ and $d$, higher the scatter. For covariance matrices of independent variables, the determinant is large and thus scatter is more.

Idk what's happening anymore lol.

Now we will do **Bayesian Decision Theory**