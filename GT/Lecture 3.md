# Lecture 3!
Say, “Lalisa, love me, Lalisa, love me” (Hey!)  
Call me, “Lalisa, love me, Lalisa, love me” (Hey!)  
Oh-ooh, 알잖아 attitude  
뭘 더 어쩌라구, the loudest in the room (Hoo! Hoo!)


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
- No. of labelled graph given $n$ labels is $2^{n\choose 2}$ (Either choose or not choose edge).
- How many isomorphic among each other? No idea if $P$ or $NP$. It is however known the subgraph isomorphism is ***NP-complete***, i.e. whether a graph contains a subgraph isomorphic to a given graph.
- Section 1.1.31 has 11 isomorphism classes of graphs with $4$ vertices, whereas there are $64$ labelled graphs with $4$ vertices.
- Exercise: $G\equiv H$ if and only if $G'\equiv H'$

### Decomposition of graphs
- A graph is **self-complementary** if it is isomorphic to it's complement.
- A **decomposition** of a graph $G$ is a list of subgraphs of $G$ such that each edge occurs in precisely one of the subgraphs in the list.

## Automorphism
An automorphism of $G$ is a permtation of $V(G)$ that is an isomorphism from $G$ to $G$.
- A graph is called vertex transistive if for every pair $u,v\in V(G)$ there is an automorphism that maps $u$ to $v$.

## Connected and Disconnected
- Connected: There exists atleast one path between **any** two distinct vertices (for all pairs of vertices).
- Disconnected: Otherwise
- Example:  ![[GT/Pasted image 20220124142208.png]]

## Components
- The components of a graph $G$ are its maximal connected subgraphs.
- A components is trivial if it has no edges.
- An isolated vertex is a vertex
  ![[GT/Pasted image 20220124142510.png]]
  
## Proposition 3:
Every graph with $n$ vertices and $k$ edges has at least $n-k$ components.
