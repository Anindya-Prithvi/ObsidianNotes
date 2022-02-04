# Lecture->5
## The selection problem
Input: An array (arbitrary), an integer $i$  
Goal: Get $i^\text{th}$ smallest number or $i^\text{th}$ order statistic.  

We'll see a linear time selection algo.  

```haskell
Select(A, length n, i)
	base: do something idk
	else:
		1. Choose any element as pivot = p
		2. Partition A around p (just like quicksort)
		3. Let j: position of p now
		4. if j==i then return P
		5. if j>i: recurse: return Select(A[1..j-1],j-1,i)
		6. if j<i: recurse: return Select(A[j+1..n], n-j, i-j)
```

Runtime:  
We will analyze the worst case (i.e. we recurse on the larger subarray)  
- $T(n) = c.n + T[\max(n-j, j-1)]$
- Worst case: $c\cdot n+c\cdot (n-1)+c\cdot(n-2)\dots \in \mathcal O(cn^2)$

So... `epic algorithm fail`.
### How to choose a good pivot fast?
Here are two choices
- Median (Best!) : But ...aren't you solving the median problem xD
- [30%-70%] (Good enough)
	- Randomization: Choose pivot as any element *uniformly at random*
	- Theorem: RSelect works in *expected* $\mathcal O(n)$ time
	- Deterministic pivot selection:
		- Break array A into buckets of $5$ elements (i.e. $K=n/5$ groups)
		- Find median of each group = $e$ where $|e|=K$
		- pivot $p=\operatorname{Median}(e)$
		- Let's re-write the algo:  
		    ```haskell
		    DSelect(A,length n, i)
				base: idk
				else:
					1. Group A into chunks of 5
					2. e = set of medians from each
					3. p = DSelect( e, n/5 = K, K/2 )
					4. ...same as before
		    ```
		 - Runtime analysis: We have $T(n) = c\cdot n + T(n/5) + T(?)$
			 - Key lemma: Median of $e$ is bigger than (and also smaller than) atleast 30% of the set
			 - Proof:  
			    Visualize the array as a 2D grid.  
				![[ADA/Pasted image 20220204144057.png]]  
				Here, pivot is $9$. now, let's generalize.
			 
			 We have the recurrence $T(n)\leq c\cdot n+T(n/5)+T(0.7\cdot n)$