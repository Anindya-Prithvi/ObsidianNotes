# Lecture -> 15
- Cuts in a graph (combinations of vertices thrown in 2 buckets). Number of cuts given $n$ vertices $2^{n-1}-1$ .
- **Cut property**: Consider any cut $(S,V-S)$. Then atleast the cheapest edge crossing $S$ is part of the MST.
   Zhe proof: Say edges of form $(uv)$ with weights $\{2,3,4,5\}$ with vertex $u$ in $S$ and $v$ in $V-S$. 
   Say an arbitrary edge (except the one with lowest cost) from these is chosen to create a MST. 
   ![[ADA/Pasted image 20220401135145.png]]
   Now, the moment we choose the least weighted edge, we see a cycle. Finn.
   
**NOTE**: We do not claim that the two vertex sets as a result of a cut will be connected. Why?


## Kruskal's Algorithm
*naive* and greedy (F)
```ts
T = {}
edges.sort(increasing=True)
for i in [1..m]
	if T union {e_i} does not form a cycle
		T=T union {e_i}
```
**Runtime:** For the sorting part $\mathcal O(m\log n)$ . Notice a simple graph. For the cycle detection part run a DFS with time complexity $\mathcal O(n)$. $n$ because it is a tree so edges have the same order. Therefore the loop has total complexity of $\mathcal{O}(nm)$. 

**Correctness** (Kruskal produces a MST)
Proof: Say it does not produce a spanning tree.
1. No cycle? (But see `if` conditions)
2. A vertex is not connected. But it will always pick atleast an edge (therefore not creating a cycle), therefore spanning tree.
3. Minimality: Using the cut property
   ![[ADA/Pasted image 20220401141719.png]]
   Also since sorted, we can add the least weighted edge. Finn
___
*A faster method*

Universe $P = \{p_1,p_2,p_2\dots p_n\}$, Set system $S_1,S_2\dots,S_k$ s.t. they are disjoint and $P=S_1\bigcup S_2\bigcup S_3\dots\bigcup S_k$
So, we can create a routine to find whether $p_i$ belongs to which set. Then we apply a cycle detection if they belong to the same set. Finally, a union to continue the tree.

So, let's make a data structure.
The idea, maintain an array, with elements as $p_i$ such that each can host a pointer. In case of a union, we change pointer of the smaller set to the larger set. So we will always have a ***leader***. So, the find operation can easily follow the pointers and return the leader.

**Claim:** The max length of any chain with $n$ nodes is $\leq \log_2 n$
Using induction. For $n=2$ it is definitely 1.
Suppose we have a set with $n$ nodes formed by $n_1\bigcup n_2$. WLOG, $[n_1]\leq[n_2]$.
So, length of chain of $n_1\leq \log_2 n_1$ and $n_2\leq \log_2 n_2$ . So length of longest chain $=\max(\log_2 n_2, \log_2 n_1 +1)$. Argue that $\log_2n_2\leq\log_2(n_1+n_2)$ , therefore the maximum chain turns to be $\log_2 n$.

Finn.

We are going to $\log^*$ idk tf it is.