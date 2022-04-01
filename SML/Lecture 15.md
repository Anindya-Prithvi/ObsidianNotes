## Regularization
To reduce overfitting (/reduce model complexity)

L.S.R. (Least squares reg.), we can regularize as

$\min(||Y-X^TW||_2^2+\alpha W^TW)$
so, now our solution is $W=(X^TX+\alpha I)^{-1}XY$

- Hyperparameter optimize $\alpha$ or use CV?

$L_2$ regularizer -> Ridge regression, Tikhonov reg, weight decay
$L_1$ -> Lasso regression

Say, $f(w) = ||Y-X^TW||_2^2, g(w)=\alpha W^TW$
so, we minimize $\min_w{f(w)+g(w)}$
same as $\min_w e^{f(w)}\cdot e^{g(w)}$ 
exploit monotonicity, take negative
$\max(e^{-[f(w)+g(w)]})$

So, the $e^{-g(w)}$ would look like gaussian, whereas incase of $L_1$ it has a sharp peak but also dies out easily. (May also use as an advantage, feature extraction) -> promotes sparsity

## Deep Learning
### Perceptron
- Collect input
- Linearly weigh
- add bias
- get the $\operatorname{sgn}$ of hole thing (classifier)
