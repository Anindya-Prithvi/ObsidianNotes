## Gradient Dissent
$\min_{x,y}(x^2+y^2)=f(x,y)$
We have the gradient $\nabla f=\begin{bmatrix}2x\\2y\end{bmatrix}$
So ($n=$ learning rate),
$x_{new}\leftarrow x_{old}-n(\delta f/\delta x)$ and $y_{new}\leftarrow y_{old}-n(\delta f/\delta y)$
i.e. we are going AGAINST the gradient.