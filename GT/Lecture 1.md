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

<table align="center" style="border: 0px solid black">
	<tr style="border: 0px solid black">
		<td style="border: 0px solid black">
<img src="https://i.upmath.me/svg/%5Cbegin%7Btikzpicture%7D%5Bnode%20distance%3D%7B25mm%7D%2C%20thick%2C%20main%2F.style%20%3D%20%7Bdraw%2C%20circle%7D%5D%20%0A%5Cnode%5Bmain%5D%20(1)%20%7B%24x_1%24%7D%3B%20%0A%5Cnode%5Bmain%5D%20(2)%20%5Bbelow%20left%20of%3D1%5D%20%7B%24x_2%24%7D%3B%0A%5Cnode%5Bmain%5D%20(3)%20%5Bbelow%20right%20of%3D1%5D%20%7B%24x_3%24%7D%3B%0A%5Cdraw%5B-%5D%20(1)%20to%20%5Bout%3D-100%2Cin%3D10%2Clooseness%3D1.25%5D%20(2)%3B%20%0A%5Cdraw%5B-%5D%20(2)%20to%20%5Bout%3D90%2Cin%3D180%2Clooseness%3D1.25%5D%20(1)%3B%0A%5Cdraw%5B-%5D%20(2)%20--%20(3)%3B%20%0A%5Cdraw%5B-%5D%20(3)%20--%20(1)%3B%20%0A%5Cend%7Btikzpicture%7D%20%0A" alt="\begin{tikzpicture}[node distance={25mm}, thick, main/.style = {draw, circle}] 
\node[main] (1) {$x_1$}; 
\node[main] (2) [below left of=1] {$x_2$};
\node[main] (3) [below right of=1] {$x_3$};
\draw[-] (1) to [out=-100,in=10,looseness=1.25] (2); 
\draw[-] (2) to [out=90,in=180,looseness=1.25] (1);
\draw[-] (2) -- (3); 
\draw[-] (3) -- (1); 
\end{tikzpicture} 
" />
		</td>
		<td style="border: 0px solid black">
<img src="https://i.upmath.me/svg/%5Cbegin%7Btikzpicture%7D%5Bnode%20distance%3D%7B25mm%7D%2C%20thick%2C%20main%2F.style%20%3D%20%7Bdraw%2C%20circle%7D%5D%20%0A%5Cnode%5Bmain%5D%20(1)%20%7B%24x_1%24%7D%3B%20%0A%5Cnode%5Bmain%5D%20(2)%20%5Bbelow%20of%3D1%5D%20%7B%24x_2%24%7D%3B%0A%5Cnode%5Bmain%5D%20(3)%20%5Bright%20of%3D1%5D%20%7B%24x_3%24%7D%3B%0A%5Cnode%5Bmain%5D%20(4)%20%5Bright%20of%3D2%5D%20%7B%24x_4%24%7D%3B%0A%5Cdraw%5B-%5D%20(1)%20--%20(2)%3B%20%0A%5Cdraw%5B-%5D%20(2)%20--%20(3)%3B%20%0A%5Cdraw%5B-%5D%20(3)%20--%20(1)%3B%20%0A%5Cdraw%5B-%5D%20(4)%20--%20(3)%3B%20%0A%5Cdraw%5B-%5D%20(4)%20--%20(1)%3B%20%0A%5Cdraw%5B-%5D%20(4)%20--%20(2)%3B%20%0A%5Cend%7Btikzpicture%7D%20%0A" alt="\begin{tikzpicture}[node distance={25mm}, thick, main/.style = {draw, circle}] 
\node[main] (1) {$x_1$}; 
\node[main] (2) [below of=1] {$x_2$};
\node[main] (3) [right of=1] {$x_3$};
\node[main] (4) [right of=2] {$x_4$};
\draw[-] (1) -- (2); 
\draw[-] (2) -- (3); 
\draw[-] (3) -- (1); 
\draw[-] (4) -- (3); 
\draw[-] (4) -- (1); 
\draw[-] (4) -- (2); 
\end{tikzpicture} 
" />
		</td>
	</tr>
</table>

- Finite Graph: a graph whose vertex set and edge set are finite
- Null Graph: a graph whose vertex set and edge set are empty
- Adjacent vertices: $v_j$ and $v_k$ are adjacent if edge $e_i$ is incident upon both $v_j$ and $v_i$.
- Degree: of a vertex $v_k$ is the number of edges incident upon it. Denoted using $d(v_k)$



## Proposition 1:
Let $G$ be a graph. Then, the sum of degrees of the vertices is twice the number of edges, i.e. 
$$\sum d(v)=2|E(G)|, v\in V(G)$$
Proof: Each edge contributes 2 degrees (to the vertices of $G$). To apply it on any graph, we declare that a loop contributes 2 degrees to the vertex.

## Adjacency Matrix
- Let $G=(V,E), |V|=n$ and $|E|=m$
- The adjacency matrix of $G$ written $A(G)$, is the $n\times n$ in which entry $a_{i,j}$ is the number of edges in $G$ with endpoints $\{v_i,v_j\}$.
<table align="center">
	<tr>
		<td style="border: 0px solid black">
<img src="https://i.upmath.me/svg/%5Cbegin%7Btikzpicture%7D%5Bnode%20distance%3D%7B25mm%7D%2C%20thick%2C%20main%2F.style%20%3D%20%7Bdraw%2C%20circle%7D%5D%20%0A%5Cnode%5Bmain%5D%5Blabel%3D%7B%5Csmall%20w%7D%5D%20(1)%20%7B%7D%3B%20%0A%5Cnode%5Bmain%5D%5Blabel%3D%7B%5Bxshift%3D-1em%2C%20yshift%3D-1em%5D%20x%7D%5D%20(2)%20%5Bbelow%20of%3D1%5D%20%7B%7D%3B%0A%5Cnode%5Bmain%5D%5Blabel%3D%7B%5Csmall%20y%7D%5D%20(3)%20%5Bbelow%20right%20of%3D1%5D%20%7B%7D%3B%0A%5Cnode%5Bmain%5D%5Blabel%3D%7B%5Csmall%20z%7D%5D%20(4)%20%5Bright%20of%3D3%5D%20%7B%7D%3B%0A%5Cdraw%5B-%5D%20(1)%20--%20node%5Bxshift%3D-0.6em%5D%7Ba%7D%20(2)%3B%20%0A%5Cdraw%5B-%5D%20(1)%20--%20node%5Byshift%3D0.7em%5D%7Bb%7D%20(3)%3B%20%0A%5Cdraw%5B-%5D%20(3)%20--%20node%5Byshift%3D0.6em%5D%7Be%7D%20(4)%3B%20%0A%5Cdraw%20(2)%20to%20%5Bout%3D40%2Cin%3D170%2Clooseness%3D0.95%5D%20node%5Byshift%3D0.6em%5D%7Bc%7D%20(3)%3B%20%0A%5Cdraw%20(3)%20to%20%5Bout%3D240%2Cin%3D10%2Clooseness%3D0.65%5D%20node%5Byshift%3D-0.6em%5D%7Bd%7D%20(2)%3B%20%0A%5Cend%7Btikzpicture%7D%20%0A" alt="\begin{tikzpicture}[node distance={25mm}, thick, main/.style = {draw, circle}] 
\node[main][label={\small w}] (1) {}; 
\node[main][label={[xshift=-1em, yshift=-1em] x}] (2) [below of=1] {};
\node[main][label={\small y}] (3) [below right of=1] {};
\node[main][label={\small z}] (4) [right of=3] {};
\draw[-] (1) -- node[xshift=-0.6em]{a} (2); 
\draw[-] (1) -- node[yshift=0.7em]{b} (3); 
\draw[-] (3) -- node[yshift=0.6em]{e} (4); 
\draw (2) to [out=40,in=170,looseness=0.95] node[yshift=0.6em]{c} (3); 
\draw (3) to [out=240,in=10,looseness=0.65] node[yshift=-0.6em]{d} (2); 
\end{tikzpicture} 
" />
		</td>
	</tr>
	</table>
	

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