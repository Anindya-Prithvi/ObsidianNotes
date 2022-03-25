# Lecture -> 13
- Revision of introductory GT (Tree, path, cycle, components, DS to store graphs)
## DFS with timestamp (next lec.)
- Maintain a struct with Time stamp of arrival and departure for each vertex. Initialize to $\infty$ (disconnected components)
- Arrival time is the first arrival at that vertex
- Departure time is the last we will see that vertex (i.e. all possible sub-paths have been explored)
- A DFS tree (formed by $n-1$ vertices, consider incidence of edge on vertex *only for a connected graph)
- Tree edge (used in DFS) and back edge (useless)
- An illustration  
   ![[ADA/Pasted image 20220325141504.png]]
- **Property:** Ancestor relationship (only for *undirected DFS tree*). For a back-edge to exist. If $(u,v)$ is a backedge then either of them must be an ancestor of the other.
	- For a directed graph, there shall be no need of ancestory. lol

```ts
visited: boolean[]
visited[v] = 0 forall v
arrival: number[]
departure: number[]
time: number = 0

function DFS(v){
	visited[v] = 1;
	arrival[v] = time++;
	for (w: adjlist of v)
		if (!visited[w]) DFS(w);
	departure[v] = time++
}	
```

Time complexity arguments:
- We traverse the adjacency list of any vertex exactly once.
- So we see any edge $e$ only once.
- And for initializers we have order $\mathcal{O}(V)$
- Final complexity is $\mathcal{O}(V+E)$, linear time.