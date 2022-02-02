# Lecture 5
## How do we align sequences?
![[PB/Pasted image 20220202103204.png]]  
Both are different sequences. We find the highest scoring such alignment (using dynamic programming) by sliding.  
![[PB/Pasted image 20220202103441.png]]  
The goal is to get to better score (in terms of alignment) but also as per permissive evolution.

### Dayhoff's Algorithm
- Dayhoff(1978) created a "base dataset" to learn from
- 34 protein "superfamilies" grouped into 71 phylogenetic trees
- Range of conservation