# Regression
Given $(\mathbf x_i,y_i)$ where $\mathbf x_i = (x_1,x_2\dots)$  and $y_i\in\mathbb{R}$ a label for a data point.
We need to find the function $\hat f\approx f:X\mapsto Y$

### Linear regression
Say $\hat f(x)=w_1x+w_0$, then $\hat y_i=w_1x_i+w_0$ the predicted value from the new function, then make $\hat y_i\approx y_i$

So, $\operatorname{err}_i=\phi(\hat y_i, y_i)$
where $\phi$ be distance or divergence
We already know, for $\phi$
$\phi(a,b)=\phi(b,a), \phi(a,a)=0$ and triangle ineq.
For **divergence** $\phi(a,b)$ may or may not be $\phi(b,a)$

$\hat Y = X^T W$
where, $X=\begin{bmatrix}x_1&x_2\dots&x_n\\1&1\dots&1\end{bmatrix}$ , $W=\begin{bmatrix}w_1\\w_0\end{bmatrix}$ and $\hat Y=\begin{bmatrix}\hat{y_1}\\\hat{y_2}\\\vdots\\\hat{y_n}\end{bmatrix}$ and $Y=\begin{bmatrix}{y_1}\\{y_2}\\\vdots\\{y_n}\end{bmatrix}$ .
We get $\phi(Y,\hat Y)=||Y-\hat Y||_2^2$ , i.e. $l_2$ norm. the sum of squares of all values of vector. The $l_1$ norm is sum of all abs. values in the vector.

Therefore we have $\phi(Y,\hat Y)=(Y-\hat Y)^T(Y-\hat Y)=Y^TY-Y^T\hat Y-\hat Y^TY+\hat Y^T\hat Y$ 

Now substitute $\hat Y$ and minimize w.r.t. $W$ (by getting derivative = 0)
Finally we'd get $W=(X^TX)^{-1}XY$

But how far will linear algebra help :trollblob: