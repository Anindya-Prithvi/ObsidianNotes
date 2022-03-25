# Lecture -> 12
## Stable matching (/marriage)
**Input:** $n$ wizards and $n$ wands.
Each wizard has a preference list,
Each wand has a preference list. May generalize to $m,n$ (however it is not guaranteed $\exists$ a stable matching).  
**Output:** A stable matching  
**Stability:** 
Unstable when for some matching $M$ there are two candidates who might *cheat* on each other (both side should hold).
Stable if no unstable lol.

### The algorithm (Gale-Shapely):  
[From the wiki](https://en.wikipedia.org/wiki/Gale%E2%80%93Shapley_algorithm#Algorithm)  
**Initialize:** All wizards $w\in W$ and wands $v\in V$ are unmatched.
**Iterate:**  
while $\exists\ w, w\not\xrightarrow{}v$ and not tried every wand:  
- assign wand if wand is single,
- check stable matching (i.e. check with wand if it's okay) and assign ($w'$ is now unmatched),
- reject (i.e. $w$ remains unmatched)

**Observations**:
1. Each wizard tries a wand in decreasing order of preference
2. Each wizard tries each wand at most once.
3. Once a wand has a holder, it never becomes free (it just gets a new wizard). However a wizard is dobee, they may become *free*.

**Note:** If the position of wands and wizards were flipped we may get a different stable matching. (move to bottom of the page)

**Termination:** Using observation 2, we see that $n$ wizard can try at most $n$ wands. Therefore, by $\mathcal{O}(n^2)$ we shall be done.

### Proofs of correctness:
1. **Output is a Perfect Matching.**  
   Proof: Suppose GS does not output a perfect matching, then $\exists$ some $w$ who is free. Since we have $n$ wizards as well as wands, $\exists$ some $v$ which is also free. Also implies, $v$ has not been tried, i.e. the algorithm has not terminated.
2. **Output is a Stable Matching**
   Proof: Suppose $w,v$ is unstable (for the sake of contradiction)
   - Case 1, $w\not\xrightarrow{tried}v$. This means that $w\xrightarrow{}v'$ which is at a lower priority, however this contradicts obeservation 1.
   - Case 2, $w\xrightarrow{tried}v$. However, then $v$ would have already captured $w'$ using observation 3. Even if $w$ came by, $w$ shall be rejected or $w$ gets the wand preliminarily but later forfeits their ownership.

We might consider the stable roommate problem i.e. pair $n$ people given everyone has a preference list of $n-1$ remaining candidates. A stable matching may not exist.  
In our setting, a stable matching shall always exist as shown above.  

Now, size of input is $\mathrm{N}=2n^2\in\mathcal{\Theta}(n^2)$, then in terms of size of the input, our algorithm is just $\mathcal{O}(\mathrm{N})$.

To implement efficiently,  
For each wand $v$, $\mathrm{Pref[v]}$, we generate a converse preference list which essentially is $w\mapsto v$, so whenever a wizard is trying a wand, we can fetch their preference in constant time.

### Which Stable-Matching does GS find?
Here are a few definitions lol.
- **Valid wand:** Wand $v$ is a valid wand for wizard $w$ if $v$ can be assigned to $w$ in *some* stable matching.
- **Wizard Optimal Matching:** A stable matching where *every* wizard gets the best possible valid wand.

**Theorem:** GS produces a Wizard Optimal Matching. Therefore a unique stable matching.  
**Proof:** Khud karlo  
**Corollary:** GS produces a wand pessimal matching.