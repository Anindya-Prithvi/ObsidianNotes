# Lecture->3
![[ADA/Pasted image 20220128134320.png|400]]

## Divide and Conquer Algorithms
1. Divide (break into several parts)
2. Conquer (Solve the smallest solvable)
3. Combine (subproblems)

### Counting Inversions in an Array
Input: $1,3,5,2,4,6$  
Output: $3$  
Inversion pairs: $(3,2),(5,2),(5,4)$ {kind of like bubble sort}  
Golden Benchmark to get inversions: Sorted array (ascending)  
Trivial algorithm = $\mathcal O(n^2)$  
Today: $\mathcal O(n\log n)$  
Q. Can we output all inversions in same time above? No, total $O(n^2)$ possible invs.

- Key Ideas
	- Suppose $A$ is divided in to $X$ and $Y$ (possibly in the middle)
	- An inversion pair $(i,j)$ is :
		1. Left inversion : Both $(i,j)$ in $X$
		2. Right inversion : Both $(i,j)$ in $Y$
		3. Split inversion : $i$ in $X$ and $j$ in $Y$
	- Using recursion get $(1), (2)$ and after you get the results, count split inversions.
	- Here's the pseudo code  
	```py
	CountInv(array& A, length n):
		if n==1 return 0
		X = A[1,2,...n/2], Y=A[n/2+1,...,n]
		x = CountInv(X,n/2)
		y = CountInv(Y,n/2)
		x = CountSplitInv(X,n/2)
		return x+y+x
	```
	- Now, since split inversions wont be affected if we sort each X and Y (along the recursive calls) it'll get easier to count inversions. We will use this to count split inversions while merging. `count += (n/2 - i + 1)` where $i$ is the iterator of $X$ and we are using the combine/merge function. This takes advantage of sorting.