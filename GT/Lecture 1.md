# L(1)
## Overview
This was the first lecture of graph theory. The professor is super old and kind lol. Course summary: Proof based and fun questions. Cutoffs are absolute. For A, aim for 80%+ (cutoff at 75%). The remaining grades are out of question anyways. A very interesting thing which came up during the meet is the page rank algorithm.

## Defining graphs
- The normal way: A graph $G$ can be defined as a pair $(V,E)$, where $V$ is a set of vertices, and $E$ is a set of edges between the vertices $E \subseteq \{(u,v) | u, v \in V\}$. If the graph is undirected, the adjacency relation defined by the edges is _symmetric_, or $E \subseteq \{\{u,v\} | u, v ∈ V\}$ (sets of vertices rather than ordered pairs). If the graph does not allow _self-loops_, adjacency is [_irreflexive_](https://xlinux.nist.gov/dads/HTML/irreflexive.html).

- The formal way: A graph $G$ is a triplet consisting of:
	- A vertex set $V(G)$ (non empty)
	- An edge set $E(G)$, disjoint from the vertex set (could be empty)
	- A relation between an edge and a pair of vertices
	General notation: $|V(G)|=n, |E(G)|=m$. Please adhere to this xD.

A bit of imagery. Note, "we" define graphs such that the vertex set can never be empty. Also, for the scope of the course, our graph shall be finite.  
- Loop: An edge whose endpoints are equal  
- Multiple edges: Edges having same pair of endpoints  
- Simple graph: No loop or multiple edges.  
  ![[Pasted image svgtikz1Lec1.svg|100]]
  ![[Pasted image svgtikz2Lec1.svg|100]]  
- Finite Graph: a graph whose vertex set and edge set are finite
- Null Graph: a graph whose vertex set and edge set are empty
- Adjacent vertices: $v_j$ and $v_k$ are adjacent if edge $e_i$ is incident upon both $v_j$ and $v_i$.
- Degree: of a vertex $v_k$ is the number of edges incident upon it. Denoted using $d(v_k)$



## Proposition 1:
Let $G$ be a graph. Then, the sum of degrees of the vertices is twice the number of edges, i.e. 
$$\sum d(v)=2|E(G)|, v\in V(G)\tag{1}$$
Proof: Each edge contributes 2 degrees (to the vertices of $G$). To apply it on any graph, we declare that a loop contributes 2 degrees to the vertex.

## Adjacency Matrix
- Let $G=(V,E), |V|=n$ and $|E|=m$
- The adjacency matrix of $G$ written $A(G)$, is the $n\times n$ in which entry $a_{i,j}$ is the number of edges in $G$ with endpoints $\{v_i,v_j\}$.  

![[Pasted image svgtikz3Lec1.svg|150]]
$$\begin{array}{cc} &
\begin{array}{c c c c} w & x &y &z \\
\end{array}
\\
\begin{array}{c c c c}
w \\
x\\
y \\
z
\end{array}
&
\left[
\begin{array}{c c c c}
0 & 1 & 1 & 0\\
1 & 0 & \color{red}2 & 0\\
1 & \color{red}2 & 0 & 1\\
0 & 0 & 1 & 0\\
\end{array}
\right]
\end{array}$$

$G$ a simple graph then, adjacency matrix $A(G)$ is symmetric $(0,1)$ matrix. An **important result** for real symmetric matrices, they are orthogonally diagonalizable over $\mathbb R$.

## Incidence Matrix
Let $G=(V,E), |V|=n$ and $|E|=m$. The incidence matrix $M(G)$ is $n\times m$ matrix in which entry $m_{i,j}$ is $1$ if $v_i$ is an endpoint of $e_i$ and otherwise $0$.

$$\begin{array}{cc} &
\begin{array}{c c c c c} a & b &c &d &e \\
\end{array}
\\
\begin{array}{c c c c}
w \\
x\\
y \\
z
\end{array}
&
\left[
\begin{array}{c c c c c}
1 & 1 & 0 & 0 & 0\\
\color{red}1 & 0 &\color{red}1&\color{red}1& 0 \\
0 & 1 & 1 & 1 & 1\\
0 & 0 & 0 & 0& 1\\
\end{array}
\right]
\end{array}$$
