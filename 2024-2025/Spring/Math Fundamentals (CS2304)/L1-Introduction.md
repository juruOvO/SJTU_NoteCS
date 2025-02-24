
## Regulation:
**DO NOT HAND IN LATE**

### An example
$$
\begin{gather}
F=\{f\mid f\colon \mathbb{N}\to\mathbb{N}\}\\
D=\{g\mid g\colon\mathbb{N}\to\mathbb{N}\wedge\text{g is C++ realizable}\}\\
\text{s.t. }\mid D\mid<\mid F\mid\\
\mid D\mid=\mid\mathbb{N}\mid\\
\end{gather}
$$

## Set (Revision)

### Partial Ordering
- Reflexive: $xRx$
- Anti-symmetric: $xRy\wedge yRx\to x=y$
- Transitive: $xRy\wedge yRz\to xRz$
### Partial Ordering Set
$(S,R)$
#### Symbols:
- Partial Ordering $\leq\text{ }\preceq$
- Strict Inequality $<\text{ }\prec$
- Reverse Inequality $>\text{ }\geq\text{ }\succ\text{ }\succeq$
#### Linear Ordering
- R: partial Ordering
- $\forall x,y\in S\colon xRy \vee yRx$

#### A crucial ordering
$(S_{n},\preceq_{n})$ Linear Ordering
$(a_{1},\dots,a_{n})(b_{1},\dots,b_{n})\in S_{1}\times \dots \times S_{n}$

**Lexicographic ordering**

### Immediate predecessor
- x < y
- NOT(Exists z) x < z < y
### Hasse Diagram
...

### Minimal/Maximal element

### Smallest/Largest element

_S / L elem -> Min / Max elem_

eg: finite PO set -> min elem exists
	pf. 
		Suppose none -> infinite.

### Linear extensions:
_For finite PO set, (S,≤) -> (S,≤') s.t. x ≤ y -> x≤y'_
pf. **Induction**
	n=1, true.
	finite PO set -> min elem exists.
	delete min elem: S' |S'|=n-1
	Using S' to construct linear extension PO. (RU{(x0,y)})
	_Commonly, there are more than one linear extensions._
