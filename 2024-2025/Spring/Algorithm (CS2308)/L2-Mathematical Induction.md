## Base Principle:
1. P(n) is true (n=1).
2. For each n, n>1, P(n-1) is true -> P(n) is true
3. Conculution: For all n ∈ N, P(n) is true.

## Strong Inducion:
1. P(n) is true when n=1.
2. For each n, n>1, for every k<n P(k) is true -> P(n) is true.
3. Conclusion: ...

## Another Form of Induction:
1. P(n) is true when n=1,2
2. For every n>2, P(n-2)->P(n)
3. Conclusion: ...

## Another Form of Induction II:
1. P(1)
2. For n>1 AND n=2^k (k∈Z), P(n/2)->P(n)
3. Conclusion: For every n=2^k (k∈Z), P(n)


## Example
### Plane Split Problem
_How many zone can there be when a plane is split by n lines?_
Let there are n-1 lines in the plane:
For L(n) and L(n+1),
In Zone X, intersection of L(n) and L(n+1) exists -> split in 4
In other Zones, 
1) No effect
2) Split by L(n)
3) Split by L(n+1)
So assume L(n) has been added, then when L(n+1) is added, 
(n-1) + 2 zones are added.

**The induction method handles the Increasing Rate of function**
**Guess and prove**

### Coloring Porblem (2 Colors)
_Prove_
n=1 (1 line) P(1) is true.
Suppose k<n, P(k) is true,
For L(n),
Let colors on one side of L(n) hold, colors on the other side transverse,
For R1,R2 (R1 and R2 touch),
1. If R1, R2 are on different sides, true.
2. Otherwise, also true (transverse)

### Adding Problem
_Triangle:
1 = 1
3+5 = 8
7+9+11 = 27
...
Prove: Sum of Line(i) = i^3_
1. (i+1)^3 - i^3 = 3i^2 +3i +1
2. The last num of L(i+1) is ?
3. ...

**The Problem Can Be Done In Several Steps**

### Inequation Problem
_Prove: 1/2 + 1/4 + ...+ 1/2^n < 1_
n = 1 , true
if P(n) is true,
P(n+1):
1/2 + 1/2(1/2 + 1/4 + ...) < 1

**Consider The FIRST Item**

### Euler Formula
_V+F=E+2_
1. F=1
	V+1=E+2
	V=1, T
	V=n T (Suppose)
	E = n-1
	When V = n+1, T
2. F=n
	Suppose T
	When F=n+1
	f is enclosed by circuit
	...

**Nesting Induction (Mutiple Params)**

### Graph Problem
_G = (V,E), G is a directed graph, prove that:
Exists an independent set (in which every two points are not adjecent) S(G),
that every node in G can be reached from a node in S(G) via a path (len <= 2)_
n<3, T

