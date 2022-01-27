- Notating partite graphs $G=(A\cup B,E)$ where each $A,B$ represent a partite set. For $n$-partite it could be $A,B,C...$
- These are also questions from West's book
- Handshaking lemma $\displaystyle\sum_{i=1}^n deg(v_i)=2m$
1. $K_{1,1}$ or $K_2$ is the only complete bipartite graph which is also a complete graph.
2. $G$ vertex set has all $(0,1),(0,0),(1,0),(1,1)$ has vertices. Two vertices are adjacent if they are 1 unit apart. Therefore it is bipartite. Now, generalize it to k-tuple i.e. $(0,0,0,0,0,1,0,0,0,0,0)$ and solve. 
	- We may have an edge between two vertices only when their parity differs. (parity: number of ones)
	- Since parity can either be 0 or 1, (i.e. odd or even), it creates two sets, which are now bipartite. (btw, it's not complete bipartite (000 \noedge 111))
	- [WILD] You can also apply induction, $P(1)$ is true, assume $P(k)$, in case of $P(k+1)$ you'll find that there two sets (one with $k+1^{th}$ element as $0$ and other being $1$) 
3. When $G$ is a simple graph (with m edges and n vertices). Let $G-v_i$ have $m_i$ edges. Then
	- $m=\frac{1}{n-2}\displaystyle\sum_{i=1}^n m_i$ because each edge involves two vertices, so each edge will appear exactly $n-2$ types for all $G-v_i$ when $i=1,\dots,n$
	- $deg(v_i)=\left(\frac{1}{n-2}\sum_{j=1}^n m_j\right)-m_i$ pretty obvious.  
	- Or, use handshaking lemma (Long ass tho)
4. Decanting problem: not solved (make all states and join...nothing much)
5. Using rectangular blocks whose entries are all equal, write down an adjacency matrix for $K_{r,s}$.  
    0 matr, 1 matr  
	1 matr, 0 matr,  
	where first is $r\times r$ and $4$th is $s\times s$
6. k-regular graphs, pretty self explanatory