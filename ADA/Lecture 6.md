# Lecture->6
We shall begin DP now. Who doesn't like DP ;)

## First example
**Input**: A set of balls arranged in a row; each ball has a weight  
**Output**: Pick balls of maximum possible total weight; No two adjacent balls can be picked

E.g. [2,5,6,4,3,5], pick as much as you can but maximize the weight.  
It's easy to see how a greedy one would fail as always.  

Let's try something different, here are some observations:
1. Iff last ball is not part of the optimal solution, then Optimal solution = Optimal solution with the last ball removed from input (strictly smaller than input)
2. Iff Last ball is part of the optimal solution so the second last ball cannot be, then Optimal solution = Optimal solution with last 2 balls removed + weight of last ball

Formal recurrence:  
Let $\mathrm{opt[i]}$: The optimal solution with balls $\{b_1,b_2,\dots b_i\}\forall i=0,1,2\dots$ (Subproblem definition).  
$\mathrm{opt[0]=0, opt[1]=weight(1)}$ (assuming balls are positive, in case of generalizing with negative, just change the base case)  
$\mathrm{opt[i]}=\begin{cases}\mathrm{opt[i-1]}&case1\\\mathrm{opt[i-2]+weight(i)} & case 2\end{cases}$

Trivial proof of case 1 and case 2.  
Now, say balls are $b_1,b_2\dots b_n$, then the optimal solution can either have $b_n$ or not have it at all. If we try both, we have the recursive solution as $T(n)=T(n-1)+T(n-2)+c$ which is the fibonacci/exponential complexity.

We also observe here that in the recursion, the distinct calls are only $n$ (since `SelectBalls(n-i)`). If we memo(r)ise and look up in $\mathcal O(1)$, we're done.

Solution 1: Using some recursion with lookup
```py
Tab: Array of size n (memoization)
def SelectBalls(b1,b2,b3...bn):
	if Tab[n] is valid return Tab[n] else:
	if n==0, Tab[n] = 0,
	elif n==1, Tab[n] = weight of b1,
	else:
		w1 = SelectBalls(b1,b2,...bn-1)
		w1 = SelectBalls(b1,b2,...bn-2)+weight(bn)
		Tab[n]=max(w1,w2)
```

Solution 2: Linear time (bottom up) iterative
```py
Tab: Array of size n+1
def Selectballs(b1,b2...bn):
	Tab[0] = 0
	Tab[1] = b1
	for i = 2,3,...n:
		Tab[i] = max(Tab[i-1], Tab[i-2]+weight(bi))
	return Tab[n]
```

Finn.
