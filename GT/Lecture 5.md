# L(5)
## Eulerian graphs
- A graph is Eulerian if it has a **closed** trail passing through **all** the __edges__ exactly once. For convenience consisting of trival components is regarded as Eulerian.  
- A closed trail is a **circuit** when we do not specify the first vertex but keep the list in cyclic order.
- An Eulerian circuit or Eulerian trail in a graph is a circuit or trail containing all the edges.
- *Even graph* is a graph with vertex degrees only even.
- A circuit (V(5)) but not a cycle. (However every cycle is a circuit)  
  ![[Pasted image 20220131134522.png]]
  
## Theorem 1 (Euler-1735)
A graph $G$ is Eulerian if and only if it has at most one non-trivial component and its vertices all have even degree.
  
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
- The neighbourhood of $v$, written $N_g(v)$ or $N(v)$ is the set of vertices adjacent to $v$. A vertex is self-adjacent if it has a loop.  
  ![[Pasted image 20220131143708.png]]
  
## Proposition 7
If $G$ is a simple graph in which every vertex has degree at least $k$, then $G$ contains a path of length at least $k$. If $k\geq2$, then $G$ also contains a cycle of length at least $k+1$.