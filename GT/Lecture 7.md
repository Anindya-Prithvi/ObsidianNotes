# L(7)
## Graphic sequence
- List of non-negative numbers that is the degree sequence of some simple graph.
- A simple graph realizes $d$, i.e. a simple graph with degree sequence $d$.

Main question, how do we realize a degree sequence!  
- recursively,
- say sequence [3,3,3,3,3,2,2,1], now delete the first vertex
- [**2,2,2**,3,2,2,1], now reorder to make it graphic. [3,2,2,2,2,2,1] and delete one vertex, [**1,1,1**,2,2,1], and again, [2,2,1,1,1,1], [1,0,1,1,1], reorder [1,1,1,1,0], correct!
- Everyone is satisfied!
- Here's an illustration (move on paper to right, then reconstruct the original degree sequence towards left). May not be unique.  
  ![[GT/Pasted image 20220207134908.png]]
  
  ## Proposition 14
  For $n>1$, an integer list $d$ of size $n$ is graphic if and only if $d'$ is graphic where $d'$ is obtained from $d$ by deleting its largest element $\Delta$ and subtracting from its $\Delta$ next largest elements. The only $1$-element graphic sequence is $d_1=0$
  
  Proof:  
  - For n=1, the statement is trivial
  - For $n>1$, we first prove that the condition is sufficient
	  - Given $d$ with $d_1\geq\dots d_n$ and a simple graph $G'$ with degree sequence $d'$
