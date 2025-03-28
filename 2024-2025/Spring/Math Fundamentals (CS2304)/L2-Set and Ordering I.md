### Chain & Independent set
___

####  最长链长度 = 最小反链划分数 (Mirsky's theroem)
$\text{Pf.}$
$$
\begin{gather}
\text{Trivial,}\omega(P)\leq t\\
\text{For,}\\
A_{1} = \text{the min elem set of S}\\
A_{i} = \text{the min elem set of} S\setminus\{A_{1}\cup A_{2} \cup ... \cup A_{i-1}\}\\
... A_{m}\\
\text{Only need to proove}\colon\omega(P)\geq m\\
\text{It's trivial to ocnstruct a chain with len of m}\\
m\leq\omega(P)\\
\mathcal{Q.E.D}\\
\end{gather}
$$
#### 推论：
- $\alpha(P) \cdot \omega(P) \geq \mid S\mid$
- $\alpha(P)\text{,}\omega(P)\text{之一至少为}\sqrt{\mid S\mid}$

### Erdos-Szekeres引理：
_任意含有$n^2+1$个元素的实数序列，$x_{1},x_{2},...,x_{n^2+1}$中都含有一个长度为$n+1$的单调子序列。_
pf. 
对于$(x_{1},...,x_{n^2+1})$,设$I=\{1,2,...,n^2+1\}$
在集合$I$上定义关系$\preceq \colon i\preceq j \text{当且仅当}(i<j)\wedge (x_{i}\leq x_{j})$
$(I,\preceq)$ 是偏序集
- $\omega(I,\preceq)>n\colon$ 非递减子序列 $x_{i1}\leq x_{i2}\leq ... \leq x_{im}$
- $\alpha(I,\preceq)>n\colon$ 递减子序列

### DIlworth's theroem
_$P=(S,\preceq)$,
$max\{\mid A\mid \colon \text{A is independent set of P}\}=min\{\text{P chain partition}\}$_
$\text{Pf.}$
$$
\begin{gather}
\text{Induction on }\mid P\mid,\\
\text{Suppose }\mid P\mid >0,\\
\text{Let }\mu = \text{max size of anti-chain}\\
\text{Only need to prove P can be partitioned by }\mu\text{chains.}\\
\text{Let C be the maximal chain of P.}\\
\end{gather}
$$

**Case 1:**
Every anti-chain in P\C has $\leq \mu -1$ elems, then by induction, 
P\C can be partitioned into $\mu -1$ chains. Done.
**Case 2:**
There still exists  an anti-chain $A=\{a_{1},...,a_{\mu}\}$ in P\C
$P^{-} = \{x \in P \colon x\preceq a_{i} \text{ for some i}\}$
$P^{+} = \{x \in P \colon x\succeq a_{i} \text{ for some i}\}$
Note that, 
- $P=P^{-}\cup P^{+}$
- $A=P^{-}\cap P^{+}$
- $x_{p}\notin P^{-}$
then, $P^{-}$can be partirioned into $\mu$ chains. (Induction on $P^{-}$ and $P^{+}$)



