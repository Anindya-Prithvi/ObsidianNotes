# L(2)
## Complement (Simple Graph)
Complement of $G$: The complement $G'$ of a simple graph $G$:
- $V(G')=V(G)$
- $E(G')=\{uv|uv\notin E(G)\}$: Every edge is determined by it's endpoints $(u,v)$.

## Subgraph
- $V(H)\subseteq V(G)$ and $E(H)\subseteq E(G)$ and,
- The assignment of endpoints to edges in $H$ is the same as in $G$.
- Induced subgraph: Whenever the vertices of $H(G)$ have **all** the edges in $E(G)$ corresponding to all vertices $H(G)$.

## Clique and Independent Set
- Complete Graph: A simple graph whose vertices are pairwise adjacent.
- We use the notation $K_n$ to denote a complete graph of $n$ vertices.
	- $n\choose2$ edges
	- Complement of $K_n$ is trivial (has no edges)
	- Induced subgraph: smaller or equal complete graph
- A **Clique** in a graph is a set of pairwise adjacent vertices (a complete graph). (more like a complete subgraph)
- An **Independent set** in a graph: a set of pairwise non-adjacent vertices.
- Example:
	-	$\{x,y,u\}$ is a clique in $G$
	-	$\{u,w\}, \{v,y\}$ is an independent set.
	-	![[Pasted image 20220119141532.png]]
	-	Question: The largest possible independent set? [Later]
	-	Question: The largest clique in a graph? (Not an interesting problem though lol)

## Bipartite Graphs
- A graph $G$ is bipartite if $V(G)$ is the union of two disjoint independent sets called partite sets of $G$.
- Also: The vertices can be partitioned into two sets such that each set is independent
- The Matching Problem
- The Job Assignment Problem
- Complete bipartite graph

## Path and Cycle
- Path: A sequence of distinct vertices such that two consecutive vertices are adjacent.
- Cycle: A closed path (Only repeated vertex is the first which is same as last)

## Walk and Trail
- A walk of length $k$ is sequence of $v_0,e_1,v_1,e_2\dots,e_k,v_k$ of vertices and edges such that $e_i=v_{i-1}v_i$ for all $i$.
	- A trail is a walk with NO repeated edge
	- A path is a walk with no repeated vertex
	- A $U,V$-walk or $U,V$-trail has first vertex $U$ and last vertex $V$ and these are the endpoints
- A walk is closed if it has length at least one and its endpoints are equal.
	- A cycle is closed trail in which "first=last" is the only repetition
	- A loop is a cycle of length one

## Proposition 2
Every $u,v$-walk contains a $u,v$-path
Proof:
- Use induction on the length of a $u,v$-walk $W$.
- Basis step: $l=0$
	- Having no edge, $W$ consists of a single vertex ($u=v$)
	- This vertex is a $u,v$-path of length $0$.
- Induction step : $l\geq1$
	- Suppose that the claim holds for walks of length less than $l$
	- If $W$ has no repeated vertex...
