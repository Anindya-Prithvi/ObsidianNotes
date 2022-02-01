# Lecture->4
## Closest pair of points in 2D
Input: A set of points with $2$ coordinates  
Distance $(d)$ between two points is *Euclidean distance* in $2D$  
Output: $(a,b): d(a,b)$ is minimum  
Assumption: All points have $x$ and $y$ coordinates (Non distinct left as exercise)  

**The 1-D case:**  
Sort the given points, and linearly traverse. So complexity $\mathcal O(n\log n)$

**Back to 2D:**  
$P_x$ be the set sorted by x-coordinate  
$P_y$ be the set sorted by y-coordinate (independent of other coordinate)  
Now we choose the median using P_x. Then we have two sets, Q,R on left and right of the median (assume median on Q).  

Recursion:  
1. Compute $Q_x,Q_y,R_x,R_y$
2. $(p_1,q_1)=\operatorname{ClosestPair}(Q_x,Q_y)$
3. $(p_2,q_2)=\operatorname{ClosestPair}(R_x,R_y)$
4. Generate the sets $Q_x,Q_y,R_x,R_y$ in $\mathcal O (n)$ time [Exercise]
5. $(p_3,q_3)=\operatorname{ClosestSplitPair}(Q,R)$
6. get minimum of all $3$

ClosestSplitPair:
1. Our search space will be restricted to $\pm \delta$ where  
  $\delta=\operatorname{min}(\operatorname{ClosestPair}(Q),\operatorname{ClosestPair}(R))$
2. Note that this may not return a correct answer if the closest split pair does not lie in our restricted search space.
3. Calculations, we'll make it $\mathcal O(n)$; now assume the set $S$ is the set of points contained in the predefined region.
4. Compute $S_y$ (sorted by $y$ coordinate) in linear time.
5. Traverse the list and apply the 1D algorithm but lookahead **seven** points instead of **one**. So complexity $\mathcal O(7n)\subseteq\mathcal O(n)$.
	- Proof of correctness of **seven**
	- We use the fact that our search space is restricted by $\pm\delta$ and what is $\delta$
	- Therefore each box below will have at most one point  
	   ![[ADA/Pasted image 20220201144330.png]]
	 - And also the box height is restricted by delta.
	 - bdmtish, drumroll, so, we only need to compare with points which may be in these boxes. Therefore a linear algo.