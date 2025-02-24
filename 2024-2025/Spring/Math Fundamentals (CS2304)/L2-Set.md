### Chain & Independent set
___

####  最长链长度 = 最小反链划分数 (Mirsky's theroem)
##### pf.
trivial, $\omega(P)\leq t$
For
A1 = the min elem set of S
Ai = the min elem set of S\{A1 U A2 ... A(i-1)}
... Am
only need to prove: $/omega(P)>=m$
It's trivial to construct a chain with len of m
$m<=/omega(P)$
Q.E.D
#### 推论：
	α(P)*ω(P)>=|S|

### Erdos-Szekeres引理：
_任意含有$n^2+1$个元素的实数序列，$x_{1},x_{2},...,x_{n^2+1}$中都含有一个长度为$n+1$的单调子序列。_
pf. 
对于$(x_{1},...,x_{n^2+1})$,设$I=\{1,2,...,n^2+1\}$

### DIlworth's theroem
_$P=(S,\preceq)$,
$max\{\mid A\mid \colon \text{A is independent set of P}\}=min\{\text{P chain partition}\}$_
pf.
_Induction on $\mid P\mid$_
Suppose $\mid P\mid > 0$,

