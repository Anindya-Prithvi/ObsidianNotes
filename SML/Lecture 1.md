# Lecture sigmoid(infinity)
Below is a big overview (But I already know everything here lol so nothing "new")
## Classification
Predicting a discrete random variable $Y$ from another random variable $X$.
- Consider data $(X_1, Y_1),\dots,(X_n, Y_n)$ where $X_i=(X_{i1}, X_{i2},\dots,X_{id}) \in \mathcal{X} \subset \mathbb{R}^d$  
  is a $d$-dimensinoal vector and $Y_i$ takes values in some finite set $\mathcal{Y}$. A **classification rule** is a function $h:\mathcal{X}\to\mathcal{Y}$. When we observe a new $X$ we can predict $Y$ to be $h(X)$.
- $Y=\{0,1\}$ binary classification , rest maybe named as multiclass classification

### Loss Function
Say $y(x,\vec w)=w_0+w_1x+w_2x^2+\dots+w_Mx^M=\displaystyle\sum_{j=0}^M w_jx^j$
- $E(w)=\frac12\sum_{n=1}^N \left\{y(x_n,w)-t_n\right\}^2$ : Sum of squares error function

### Over-fitting
When training loss function is low but on testing it becomes high.
![[Pasted image 20220126185719.png]]

### Regularization
This is just adding a term in the loss function to penalize when the magnitude of $\vec w$ is high. There is Lasso and Ridge regression (L1, L2). Lasso has sum of absolute values instead of sum of magnitude. Infact you may define your very own lol.
- $\tilde E(w)=\frac12\sum_{n=1}^N \left\{y(x_n,w)-t_n\right\}^2+\frac{\lambda}{2}||w||^2$

Remaining class on reviing probability (class 10th level lmao)

## Reference books
- Hastie, Tibshirani, Friedman Elements of Statistical Learning
- Murphy Machine Learning: a Probabilistic Perspective
- Duda: Pattern Classification

## Evaluation
- Assignment (50%) - 5, This is pretty pog, I love the course ig
- Quiz (20%) - 3
- Midsem (15%)
- Endsem (15%)
- All mandatory

## Grade cutoffs
- 91-100 A/A+ : Stupid course smh, hate the course (unless jsksksks)
- 81-90 A-
- 71-80 B

## Further Reading
- Theoretical : AISTATS, ICML, JMLR, NeurIPS
- Systems+Theory: CVPR, ICCV, ECCV, AAAI, IEEE Transactions