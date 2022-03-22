# Lecture->8
Lecture slides turned black, sus.
Today's agenda is sequence alignment  
Recall the "Edit Distance problem".  
- Levenshtein 1966
- Needleman-Wunsch 1970
	- score: cost of mismatches + cost of gap (for a specific perfect alignment)
	- Applications: diff and autocorrect, speech recognition, PB (course)

## Sequence alignment problem
**Input:** Two strings $X=x_1x_2x_3\dots x_m$ and $Y=y_1y_2y_3\dots y_n$ where each $x_i,i=1,2,\dots m$ and $y_j,j=1,2\dots n$
**Cost:** $\alpha_{a,b}\geq 0$ if $a$ is aligned with $b$, $\alpha_{gap}\geq0$ if some character is aligned with a gap ($-$)
**Output:** Two strings $\hat{X}=X+\text{gaps}, \hat{Y}=Y+\text{gaps}$  of equal length say $;$ so as to minimize $\displaystyle{\sum_{r=1}^{l}\alpha_{\hat{x_r},\hat{y_r}}}$ 

### The DP Approach
Key Step: identify the subproblems, think about optimal soln
Structure of Optimal: 
- Possibilities of end points, $x_m$ aligned with $y_n$ , gap aligned with $y_n$ and $x_m$ aligned with gap. (Note, gap gap can be removed lol)
- Optimal substructure
	- Define $X' = X-x_m, Y'=Y-y_n$
	Case1. Optimal solution of $(X',Y')$ is induced by optimal solution of $(X,Y)$
	Case2. Optimal solution of $(X',Y)$ is induced by the opt. of $(X,Y)$
	Case3. Optimal solution of $(X,Y')$ is induced by the opt. of $(X,Y)$
- Subproblems:
	$P(X_i,Y_j)$: Optimal cost of the alignments of strings $X[1,2,\dots i], Y[1,2\dots j]$for all $i=0,1,\dots m, j=0,1,\dots n$
- Recurrence:
	  $$P(X_i,Y_j)=\min
	  \begin{cases}
	  P(X_{i-1},Y_{j-1})&+\alpha_{x_i,y_j}\\
	  P(X_{i-1},Y_{j})&+\alpha_{gap}\\
	  P(X_{i},Y_{j-1})&+\alpha_{gap}\\
	  \end{cases}$$
	  Base cases:
	  $P(X_i,\phi) = \alpha_{gap}\cdot i\forall i\in [m]$
	  $P(\phi,Y_j) = \alpha_{gap}\cdot j\forall j\in [n]$
- Pseudocode
   ```ts
   let P:int[m+1][n+1]
   Align(X,Y)
	   forall i=0..m, P[i,0] = i*alpha_gap
	   forall j=0..n, P[0,j] = j*alpha_gap
	   for i=1..m:
		   for j=1..n
			   P[i,j] = recurrence
		return P[m,n]
   ```
- Time $\Theta(mn)$ , Space $\Theta(mn)$
- Reconstruction: Along diag