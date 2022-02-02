# L(5)
## Eulerian graphs
- A graph is Eulerian if it has a **closed** trail passing through **all** the __edges__ exactly once. For convenience consisting of trival components is regarded as Eulerian.  
- A closed trail is a **circuit** when we do not specify the first vertex but keep the list in cyclic order.
- An Eulerian circuit or Eulerian trail in a graph is a circuit or trail containing all the edges.
- *Even graph* is a graph with vertex degrees only even.
- A circuit $(V(5))$ but not a cycle. (However every cycle is a circuit)  
  ![[GT/Pasted image 20220201222748.png]]
  
## Theorem 1 (Euler-1735)
A graph $G$ is Eulerian if and only if it has at most one non-trivial component and its vertices all have even degree.

Proof: (Necessity)
- Suppose $G$ has an eulerian circuit $C$
- Each passage of $C$ through a vertex uses two incident edges
- And the first edge is paired with the last at the first vertex
- hence every vertex has even degree
- Also, two edges can be in the same trail only when they lie in the same component.

Proof: (Sufficiency)
- Assuming that the condition holds, we obtain an Eulerian circuit using induction on the number of edges, $m$
- Basis step: $m=0$. A closed trail consisting of one vertex suffices.
- Inductive step: $m>0$.
	- When even degrees, each vertex in the nontrivial component of $G$ has at least $2$ degree.
	- The nontrivial component has a cycle $C$ (Proposition 6, graph with even degree)
	- Let $H$ be the graph obtained from $G$ by deleting $E(C)$
	- Since $C$ has $0$ or $2$ edges at every vertex, each component of $H$ is also an even graph.
	- Since each component is also connected and has fewer than $m$ edges, we can apply the induction hypothesis to conclude that each component of $H$ has an Eulerian circuit.
	- To combine these into an Eulerian circuit of $G$, we traverse $C$, but when a component of $H$ is entered for the first time we detour along an Eulerian circuit of that component.
	- This circuit ends at the vertex where we began the detour. When we complete the traversal of $C$, we have completed an Eulerian circuit of $G$.  
	  ![[GT/Pasted image 20220201221114.png]]
  
### Corollary 1.1
Let G be a connected graph with exactly two vertices of odd degree, say u and v. Then G has an eulerian trail that starts at u and ends at v.

### Corollary 1.2
Every connected non-trivial even graph decomposes into cycles.

## Order and size
- Order of graph $G$, written $n(G)$, number of vertices in $G$
- Size of graph $G$, written $e(G)$, number of edges in $G$.
- $[n]$ indicates the set $\{1,2,3,...n\}$

## Degree
- The degree of a vertex $v$ in a graph $G$, noted as $d(v)$, number of incided edges (loops count twice).
- Maximal degree is $\Delta (G)$
- Minimal degree is $\delta (G)$

## Regular
- $G$ is regular if $\delta(G)=\Delta(G)$
- $G$ is $k$-regular if common degree is $k$.
- The neighbourhood of $v$, written $N_g(v)$ or $N(v)$ is the set of vertices adjacent to $v$. A vertex is self-adjacent if it has a loop. Here is a $3$-regular graph.  
  ![[GT/Pasted image 20220201222334.png]]
  
## Proposition 7
If $G$ is a simple graph in which every vertex has degree at least $k$, then $G$ contains a path of length at least $k$. If $k\geq2$, then $G$ also contains a cycle of length at least $k+1$.

Proof:
- Let $u$ be an endpoint of a maximal path $P$ in $G$
- Since $P$ does not extend, every neighbour of $u$ is in $V(P)$.
- Since $u$ has at least $k$ neighbours and $G$ is simple, $P$ therefore has at least $k$ vertices other than $u$ and has length at least $k$.
- if $k\geq2$, then the edge from $u$ to its farthest neighbour $v$ along $P$ completes a sufficiently long cycle with the portion of $P$ from $v$ to $u$.

## Proposition 8
If $k>0$, then a $k$-regular bipartite graph has the same number of vertices in each partite set.  

Proof:  
- Let $G$ be an $X,Y$- bipartite graph.
- Counting the edges according to their endpoints in $X$ yields $e(G)=k|X|$.
- By symmetry $e(G)=k|Y|$, and the result follows.

## Proposition 9
The minimum number of edges in a connected with $n$ vertices is $n-1$.

Proof:  
- Every graph with $n$ vertices and $k$ edges has at least $n-k$ components.
- If $n-k=1$, we are done. Hence every $n$-vertex graph with fewer than $n-1$ edges has at least two components and is disconnected.
- The contrapositive of the second point completes the proof.
