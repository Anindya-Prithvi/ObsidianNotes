# L(3)
Say, “Lalisa, love me, Lalisa, love me” (Hey!)  
Call me, “Lalisa, love me, Lalisa, love me” (Hey!)  
Oh-ooh, aljanh-a attitude  
mwol deo eojjeolagu, the loudest in the room (Hoo! Hoo!)

-- Digression
 ## Isomorphism
 An isomorphism (having the same shape/ structure preserving bijection) from a simple graph (generalizable) $G$ to a simple graph $H$ is a bijection $f:V(G)\to V(H)$ such that $uv\in E(G)$ if and only if $f(u)f(v)\in E(H)$  
 ![[GT/Pasted image 20220124134640.png]]  
 - We say "$G$ is isomorphic to $H$", written as $G\equiv H$
 - Isomorphism is an equivalence relation on the set of all graphs.
 - How to tackle if a graph is isomorphic?
	 - Use adjacency matrix representation and match (by simulataneously permuting rows and columns $R_1\leftrightarrow R_2$ and $C_1 \leftrightarrow C_2$ )
- *Section 1.1.35 has **special graphs** with small number of vertices*

### Labelled and unlabelled graphs. 
- We usually use letters to _label_ vertices, hence the notion of labelled graph. Unlabeled graphs refer to an isomorphism class (E.g. $K_n, C_n, K_{r,s}, P_n$ (the paths with n vertices). There is also a Peterson Graph which gets generalized. (Wolfram GP(x,y))
- No. of labelled graph given $n$ labels is $2^{n\choose 2}$ (Either choose or not choose edge).
- How many isomorphic among each other? No idea if $P$ or $NP$. It is however known the subgraph isomorphism is ***NP-complete***, i.e. whether a graph contains a subgraph isomorphic to a given graph.
- Section 1.1.31 has 11 isomorphism classes of graphs with $4$ vertices, whereas there are $64$ labelled graphs with $4$ vertices.
- Exercise: $G\equiv H$ if and only if $G'\equiv H'$

### Decomposition of graphs
- A graph is **self-complementary** if it is isomorphic to it's complement.
- A **decomposition** of a graph $G$ is a list of subgraphs of $G$ such that each edge occurs in precisely one of the subgraphs in the list. (A vertex can appear in one or more of the subgraphs, but need not occur in all)

## Automorphism
An automorphism of $G$ is a permutation of $V(G)$ that is an isomorphism from $G$ to $G$.
- A graph is called **vertex transistive** if for every pair $u,v\in V(G)$ there is an automorphism that maps $u$ to $v$.

## Connected and Disconnected
- Connected: There exists atleast one path between **any** two distinct vertices (for all pairs of vertices).
- Disconnected: Otherwise
- Example:  ![[GT/Pasted image 20220124142208.png]]
- 
## Components
- The components of a graph $G$ are its maximal connected subgraphs.
- A components is trivial if it has no edges.
- An isolated vertex is a vertex of degree 0. It is a component itself.
  ![[GT/Pasted image 20220124142510.png]] ![[Component-Wiki-Pseudoforest.svg]]
  
## Proposition 3:
Every graph with $n$ vertices and $k$ edges has at least $n-k$ components. (POG)
Proof:
- An $n$-vertex graph with no edges has $n$ components
- Each edge added reduces this by at most $1$
- If $k$ edges are added then the number of components is at least $n-k$

## Cut-edge, Cut-vertex
A cut-edge or cut-vertex of a graph is an edge or vertex whose deletion increases the number of components. Denote as $G-e$ or $G-v$ depending on edge or vertex of graph $G$ to be removed.  
![[GT/Pasted image 20220124211246.png]]

## Proposition 4:
An edge $e$ is a cut-edge if and only if $e$ belongs to no cycles.
Proof:
- Let $e=(x,y)$ be an edge in a graph $G$ and $H$ be the component containing $e$.
	- Since deletion of $e$ affects no other component, it suffices to prove $H-e$ is connected if and only if $e$ belongs to a cycle. (i.e. we prove the contrapositive)
- First suppose that $H-e$ is connected.
	- This implies $H-e$ contains an $x,y$ path
	- This path completes a cycle with $e$.
	- Now choose that e lies in a cycle $C$.
		- Choose $u,v \in V(H)$
			- Since $H$ is connected, $H$ has a $u,v$ path $P$
		- If $P$ does not contain $e$
			- Then $P$ exists in $H-e$
		- Otherwise ($P$ contains $e$)  
		  ![[GT/Pasted image 20220124213238.png]]
			- Suppose by symmetry that $x$ is between $u$ and $y$ on $P$
			- Now $H-e$ contains a $u,x$ path along $P$, an $x,y$ path along $C$, and a $y,v$ path along $P$
			- Putting together three paths we get a $u,v$ walk in $H-e$
			- By Proposition 2, this walk contains a path in $H-e$