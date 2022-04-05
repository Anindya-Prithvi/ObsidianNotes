# Lecture -> 16
## Patch compression in Union DS
- Modify find such that the nodes directly point to the leader after reaching it.
- **Theorem:** $m$ Find/Union operations can be doe in $\mathcal{O}(m\log^*n)$ time.
	- $\log^*n=$ no. of times you take $\log$ to make the input close to 1.

## Shortest paths in directed graphs
- $\cdot2^{n-2}+1$ total paths. Consider starting and ending points, so the remaining $n-2$ vertices may or may not be included. And, another with direct path.
- For our algorithm $\mathbb{D}\text{ijkstra}$, we assume all *edge lengths are non-negative.*
- We maintain 2 sets, $S$ containing the vertices for which the shortest path has been frozen, and $V-S$ for which shortest path might be modified.
- Initially $S$ has the start vertex. We can freeze the neighbour with least edge weight (since non negative)
- Then, at each step shift the vertex $w$ with minimum $d[w]$ to $S$. Where $d[v]$ is just the least or computed distance (which maybe just a tight upper bound) to vertex $v$ from start. Note, once chosen, the vertex is now in the frozen set.
	-  $\forall$ outgoing edges from $W$ to neighbour $v'$ in $V-S$
			Update $d[v'] = \min(d[v'], d[w]+l_{wv'})$
- The pseudocode
  $$\begin{flalign*}
  &d[v]=+\infty\  \forall\  v\in s; d[s]=0\\
  &\text{H = Min-Heap(V, d[ ])}\\
  &\mathrm{while}(H\neq null)\{\\
  &\ \ \ \ \ \ w=\mathrm{deletemin}(H)\\
  &\ \ \ \ \ \ \forall \text{outgoing edges (w,v) to H}\\
  &\ \ \ \ \ \ \ \ \ \ d[v]=\min(d[v], d[w]+l_{wv})\\
  &\ \ \ \ \ \ \ \ \ \ \text{Update H (but not unnecessarily)}\\
  &\}
  \end{flalign*}$$
- Runtime analysis
	  1. Takes $\mathcal{O}(V\log V)$ : We call heapify $v$ times.
	  1. $\mathcal{O}(E\log V)$ : Since inner loop runs at most $E$ many times and inserting new edge(or updating in the minheap)
	  2. Remember to augment the DS with auxilliary strucures to get $d[v]$ easily (Minheap by default only gives access to min element)
- Proof of correctness (why was dijksrta right):
	- wtf?