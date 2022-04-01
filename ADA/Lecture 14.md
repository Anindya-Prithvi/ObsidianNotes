# Lecture -> 14
## Application 1 of DFS
**Checking 2-Edge Connectivity**
(Finding cut-edges or bridge-edges)

Naive: Repeat for every edge $e,$ $G'=G-{e}$ is connected? Runtime is $\mathcal{O}(E(V+E))$

Smarter: Just one DFS!
Recall DFS *tree* and back edges.
![[ADA/Pasted image 20220329140049.png]]
- Make a DFS tree, plot the back edges
- Note, for any edge $e\leftarrow (uv)$ , if $\exists$ a back edge from subtree of $v$ to ancestor of $v$ then $uv$ is not a bridge edge.
- dbe: deepest back edge

```ts
Check-2EC(v)
	visited[v] = 1;
	arr[v] = time++;
	dbe = arr[v];
	for (all w in neighbourhood of v):
		if !visited[w]:
			dbe = min(dbe, Check-2EC[w]);
		else:
			dbe = min(dbe, arr[w])
	if dbe = arr[v] then "report and abort"
	return dbe
```
- [not correct above] Take care of always true else condition for `uv` case (neighbourhood)
- another error (didnt understand)
Runtime, same as DFS lol.

## Application 2 of DFS
**Checking Planarity of graphs**
(Ref. graph theory for def. of planar graph)
Read about it
Runtime is linear, POG

## Minimum Spanning Tree
- Recall weighted graph and minimum sum of weight, priority Q
