# Lecture->2
## Analysis: The recurrence method
$T(n)=$ Runtime of Algorithm $1$ for multiplying two $n$-digit numbers  
Base Case : $n=1, T(n) = c$ : Multiplying two single digit numbers  
Recurrence (for $n>1$) : Express $T(n)$ as the runtime of recursive calls + additional work which maybe done in that call.

Recursively compute each $ac,bd,bc,ad$, work in this step $$\begin{align}
T(n)&=\overbrace{4T\left(\frac{n}{2}\right)}^{\text{computing ac,bd,bc,bd}}+\overbrace{c_1\cdot n}^{\text{Adding 4 n/2 (+padded) digit no.s}}\\
T(1)&=\underbrace{c}_{\text{Base case}}\\
\end{align}$$

Karatsuba's Algorithm (more like optimization) ($a+b$ may have $\frac{n}{2}+1$ digits)
$$\begin{align}
T(n)&=\overbrace{3T\left(\frac{n}{2}\right)}^{\text{n/2+1 but ignore}}+\overbrace{(c_2+c_3)\cdot n}^{\text{Adding a+b, multiplying each other}}\\
T(1)&=\underbrace{c}_{\text{Base case}}\\
\end{align}$$

### Master Method / Master Theorem
A 'Black-box' method to solve many common recurrences in Algorithm design (especially DAC)

**Assumption**: All the recursive calls are made on subproblems of equal size. (If not, use the proof we will do now)

**Assumption (for proof)**: Both constants $c$ are equal.

$$\begin{align}
T(n)&={aT\left(\frac{n}{b}\right)}+{c\cdot n^d}\\
T(1)&\leq c\\
\end{align}
$$

$$a\geq1,b\geq1,c,d\geq0$$
$a$ = Number of recursive calls  
$b$ = Shrinkage factor of subproblem size  
$d$ = Affects the runtime of the additional work  (outside recursion)

Master Theorem (Simpler Version): Prof. says no need to *remember*
$$T(n)=\begin{cases}
\mathcal{O}(n^d\log n),& \text{if }a=b^d\\
\mathcal{O}(n^d),& \text{if }a<b^d\\
\mathcal{O}(n^{\log_ba}),& \text{if }a>b^d\\
\end{cases}$$

Example: Mergesort, $T(n)=2T(n/2)+c\cdot n$ so $a=2,b=2,d=1$, so case 1. $T(n)=\mathcal{O}(n\log n)$

Example: Binary search, $T(n)=T(n/2)+c\cdot n^0$, so $a=1,b=2,d=0$, so case 1. $T(n)=\mathcal{O}(\log n)$

Example: Multiplication algorithm1, $T(n)=4T(n/2)+c_1 n$, so $a=4,b=2,d=1$, so case 3. $\mathcal{O}(n^{\log_42})$

Example: Multiplication algorithm (Karatsuba), $T(n)=3T(n/2)+c_1 n$, so $a=3,b=2,d=1$, so case 3. $\mathcal{O}(n^{\log_32})$

- The calculator uses Strassen Schonenhage: $\mathcal{O}(n\log n \log \log n)$ 
- New proposed solution: $\mathcal{O}(n\log n)$ 

## Proof of master theorem (Simpler version)
**Assumtions**:  
	1. $n$ is a power of $b$ (the shrinkage factor)  
	2. Base case: $T(1) = c$ (same as $n^d$)  

**Main technique**: 
- Recursion Trees (eww)
	- Levels: $\boxed{\log_b n+1}$
	- Subproblems at level $j$: $\boxed{a^j}$
	- Subproblem size at level $j$: $\boxed{\dfrac{n}{b^j}}$
	- *Total* work done outside recursive calls at level $j$:  $\boxed{a^j\cdot\left(\dfrac{n}{b^j}\right)^d\cdot c}=n^d\left(\dfrac{a}{b^d}\right)^j\cdot c$  
	  Should be intuitive from the above equation, Good = $a$, bad = $b^d$, in the end we just sum it all.
	- So, work is sum of total work across all levels$$\sum_{j=0}^{\log_b n+1}n^d\left(\dfrac{a}{b^d}\right)^j\cdot c$$
