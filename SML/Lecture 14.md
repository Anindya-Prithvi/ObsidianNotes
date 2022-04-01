**Question:** What if you take several sub-datasets, compute $\hat f_k$ for each of them and compute the average?

$\hat f_{avg}(x)=x^2 E(w_2)+xE(w_1)+E(w_0)$
where $E$ is for expectation. $M=2$ the degree of polynomial.

## Bias-Variance Tradeoff
- For higher $M$: $\hat f_{avg}$ can fit into data that require degree M or less.
- Variance $\frac{1}{n-1}\sum(\hat{f_i}(x)-E(\hat f))^2$ is large
- $\hat f_i$ may be quadratic meanwhile the expectation may be quad, linear or const.
- Bias: Will be small as $E(\hat{f})$ approximately equals true $f$
- For lower M, we observe underfitting.
- But variance small (less degree of freedom for functions xD) and bias large (linear could never model quadratic).

We use cross-validation to figure out best M.
![[Pasted image 20220330223731.png]]


## Gaussian Process
$$\begin{bmatrix}y_1\\y_2\\\vdots\\y_n\end{bmatrix}\sim\mathcal N\left(\begin{bmatrix}0\\0\\\vdots\\0\end{bmatrix},\begin{bmatrix}K_{11}&\dots\\\vdots&\ddots\\&&K_{nn}\end{bmatrix}\right)$$
Similarity function $K(a,b)$
$$K(x_i,x_j)=K_{ij} = \sigma^2 e^{\frac{-||x_i-x_j||_2^2}{2l^2}}$$
Here $l$ is the width of the gaussian kernel, $\sigma$ max of kernel, both unknown.

$P(y^*|x,y)\sim \mathcal N(\mu^*,\sigma^*)$ where we want the prediction for $y^{*}$ 
This is a conditional distro on $y^*$ given all other info.
![[Pasted image 20220330232147.png]]

![[Pasted image 20220330232254.png]]
Last y is $y^*$

So we get a whole ass confidence interval
![[Pasted image 20220330232400.png]]
