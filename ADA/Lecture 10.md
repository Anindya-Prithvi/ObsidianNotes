# Lecture -> 10
## Minimizing Weighted Completion Time
A scheduling problem
**Input**: Jobs $j_1,j_2\dots j_n,$ each job $j_i$ has length $l_i$ and weight $w_i$ (kind of priority)
**Output**: A schedule to minimize $\sum_{i=1}^nw_i\cdot C_i$ where $C_i$ is the completion time of the $i^{th}$ job.
Idea: Typical mini max problem (refer SML, LDA/FDA)
**Algorithm**: Sort the jobs in descending order of $\frac{w_i}{l_i}$
**Proof**: (Technique: Exchange argument/ WOP)
idea:
- Start with the greedy schedule- Call it $\sigma$
- Suppose it is not optimal - Let $\sigma*$ be another schedule which is optimal
- Arrive at contradiction by producing even better solution