
## Regulation:
**DO NOT HAND IN LATE**

### An example
F = {f | f: N->N}
D = {g | g: N->N & g is C++ realizable}
s.t. |D|<|F|
_|D|=|N|_

## Set (Revision)

### Partial Ordering
- Reflexive: xRx
- Anti-symmetric: xRy AND yRx -> x=y
- Transitive: xRy AND yRz -> xRz
### Partial Ordering Set
_(S,R)_
#### Symbols:
- Partial Ordering ≤
- Strict Inequality <
- Reverse Inequality > ≥
#### Linear Ordering
- R: partial Ordering
- For all x,y ∈ S, xRy OR yRx

#### A crucial ordering
(Sn, ≤n) Linear Ordering
(a1, a2, ..., an)(b1, b2, ... bn) ∈ S1 * S2 ...

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
