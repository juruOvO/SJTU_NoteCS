## Multinominal theorem
$$
	\text{For arbitary real numver }x_{1},x_{2}\dots x_{m}, \text{ for }n\geq 1,\text{ coefficient of }x_{1}^{k_{1}}\dots x_{m}^{k_{m}}~(k_{1}+\dots+k_{m}=n)={n \choose k_{1},k_{2},\dots,k_{m}}
$$

## Newton's generalized binominal theorem
$$
\text{Let }{r\choose k}=\frac{r(r-1)\dots(r-k+1)}{k!}=\frac{(r)_{k}}{k!},\text{where r is arbitary, k is an integer and k>0}
$$
$$
\text{If x and y are real numbers with }\mid x\mid>\mid y\mid,
(x+y)^{r}=\sum_{k=0}^{\infty}{r\choose k}x^{r-k}y^{k}
$$


## Strling subset numbers
- The first Strling number: ${n\brack k}$ (non-empty cycles)
- The second Strling number: nonempty sets  ${n\brace k}$ ${n\brace 2}=2^{n-1}-1$ ${n\brace m}=k{n\brace k-1}+{n-1\brace k-1}$
${n\brack k}\geq{n\brace k}$
${n\brack 1}=(n-1)!$
$\sum_{k=0}^{n}{n\brack k}=n!$
$$
{n\brack k}=(n-1){n-1\brack k}+{n-1\brack k-1}
$$
## Partition of number
$P_{k}(n)$
e.g., $P_{2}(7)=\{\{1,6\},\{3,4\},\{2,5\}\}$
$$
\begin{cases}
 x_{1}+\dots+x_{k}=n\\
 x_{1}\geq\dots x_{k}\geq 1\\
\end{cases}
$$
$$
P_{k}(n)=P_{k-1}(n-1)+P_{k}(n-k)
$$

Why?
$$
\begin{cases}  
 x_{k}=1\\
x_{k}>1, then x_{1}-1+\dots+x_{k}-1=n-k
\end{cases}
$$

$\sum_{k=1}^{m}P_{k}(n)=P_{m}(n+m)$

**_Counting Problem Reference_** [Twelvefold_way](en.wikipedia.org/wiki/Twelvefold_way)

## Inclusive-exclusive
### Inclusive-exclusive principle
$$
\mid\Cup_{i=1}^{n}A_{i}\mid=\sum_{\emptyset\neq I\subseteq\{1,2,\dots,n\}}(-1)^{\mid I\mid-1}\mid\Cap_{i\in I} A_{i}\mid
$$
$$
\begin{align}
Pf.
\text{数学归纳法}
\end{align}
$$
### Application
- 错排
	$D(n)=n!-\mid A_{1}\cup\dots\cup A_{n}\mid$
	$\lim_{n->\infty}D(n)=n/e$
	

