# L(4)
- TONCAS: The obvious necessary condition also sufficient
## Maximal Path
- A maximal path in a graph G is a path P in G that is not contained in a longer path
	- When a graph is finite, no path can extend forever, so maximal (non-extendible) paths exist.
- A maximal path need not be maximum. A maximum path is a path of maximum length. Obviously, a graph G must have at least one maximum path, but there could be maximal paths of shorter length.
- Note that maximum path is global maximum.

## Proposition 5 (Characterization of Bipartite Graphs)
A graph with atleast two vertices is a bipartite if and only if it has no odd cycle.  
![[GT/Pasted image 20220129141624.png]]  
It is an if and only if proof, we shall prove the forward direction first.  
**FORWARD**  
Given: $G$ is bipartite, $|V(G)|\geq 2$  
RTP: $G$ has no odd cycles  
Proof:  
Let $k_1, k_2$ be a bipartition of $G$. Denote $v_i$ are vertices in $k_1$ and $v_j$ in $k_2$. Since it is a bipartite graph, the $2$ endpoints of any edge will be in $k_1$ and $k_2$. Any walk must lie alternately in the both partite sets.  Hence, any cycle C in G must be of the form:  
$C: u_1v_1u_2v_2\dots u_pv_pu_1$ with no repeated vertex except first and lat. Clearly this has even number of edges.  
**BACKWARD**  
Given: $G$ has no odd cycle, $|V(G)|\geq 2$  
RTP: G is bipartite  
Proof:  
We will proceed by (simple) induction on $n=|V(G)|$  
---- WHAT HAPPENED???

## Proposition 6
If every vertex of a graph $G$ has degree at least $2$, then $G$ contains a cycle.  
Proof: 
- Let $P$ be a maximal path in $G$, and let $u$ be an endpoint $P$
- Since $P$ cannot be extended, every neighbour of $u$ must already be a vertex of $P$
- Since $u$ has degree at least $2$, it has a neighbour $v$ in $V(P)$ via an edge not in $P$
- The edge $uv$ completes a cycle with the portion $P$ from $v$ to $u$