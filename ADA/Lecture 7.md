# Lecture->7
## Knapsack problem
Input: 
- A knapsack of size $W>0$ (integer)
- $n$ different indivisible iterms
- item $i$ has weight $w_i>0$ and value $v_i>0$ (ints)

Goal: To fill the knapsack (without overloading) to maximise total value.

### DP based attempt 1
$\operatorname{OPT}[i]$: optimal solution considering items $\{1,2,3\dots i\}$ and knapsack of size $W$.

Case 1: item $i$ is not part of the solution $\operatorname{OPT}[i]$, so $\operatorname{OPT}[i]=\operatorname{OPT}[i-1]$

Case 2: item $i$ is part of the solution $\operatorname{OPT}[i]$
- inclusion of $i$ does not mean that we need to reject $i-1$.
- But, we also cannot reduce to $\operatorname{OPT}[i-1]$, we need to pack as much value as possible in knapsack of size $W-w_i$ and we are not watching this param.

## DP based attempt 2
$\operatorname{OPT}[i,w]$: optimal solution considering items $\{1,2,3\dots i\}$ and knapsack of size $W$.

Case 1: item $i$ is not part of the solution $\operatorname{OPT}[i,w]$, so $\operatorname{OPT}[i]=\operatorname{OPT}[i-1,w]$

Case 2: item $i$ is part of the solution $\operatorname{OPT}[i]$, then $\operatorname{OPT}[i,w]=\operatorname{OPT}[i-1,w-w_i]+v_i$ when $w\geq w_i$.

Base case: $\operatorname{OPT}[0,w]=0\ \forall \ w\in[W]$

So, we can polish this.

## Recursive (with memoization)
```py
M[i,w]: 2D array of size nxW, initialized to -1
def Knap(i,w):
	if M[i,w]==valid return M[i,w]
	if i==0: M[i,w]=0 #base case
	elif wi>w: M[i,w]=Knap(i-1,w)
	else M[i,w]=max(Knap(i-1,w), Knap(i-1,w-1)+vi)
	return M[i,w]
```

## Dynamic (iterative) Algorithm
(Does not use additional stackspace so probably better)
```py
M[i,w]: 2D array of size (n+1)x(W+1), init -1
def Knap(n,W):
	for w = 0 to W: M[0,w] = 0 #base case
	for i = 1 to n:
		for w = 0 to W:
			if wi>w: M[i,w] = M[i-1,w]
			else: max(M[i-1,w], M[i-1,w-1]+vi)
	return M[n,W]
```
Runtime $\mathcal O(nW)$ which is pseudopolynomial