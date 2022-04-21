# Boosting [XGboost etc/ADAboost in class]
- To boost performance of weak classifiers (which perform slightly better than random.
- We will weigh the misclassfied points (say 1/n where n: sample)
- $D=\{x_i,y_i\}_{i=1}^{n}, y_i\in\{1,0\}$ , and weights $w_i=\frac1n$ . Train, then re-weigh the misclassified. Say 5 misclassied, then weight = 1/5. Now learn again.
- Say we train $m$ such classifiers, then the final $f(x)=\operatorname{sign}\left[\sum_{j=1}^{m}\alpha_j h_j(x)\right]$ where $\alpha_j=\frac12\log\left(\frac{1-L_j}{L_j}\right)$ and updating weights $w_i\leftarrow w_i\cdot e^{2\alpha_j}\ \ \forall\text{misclassified}$ 
- $\forall j\in [1..m]$ learn $h_j\leftarrow \min_H L_j$ where H is the class of the *classifiers*. $L_j=\dfrac{\sum_{i=1}^n w_i \mathbb{I}(y_i\neq h_j(x_i))}{\sum_i w_i}$ the loss where $\mathbb{I}$ (identifier func?) is 1 when classifier is correct, else 0.