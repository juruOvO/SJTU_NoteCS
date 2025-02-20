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
Let there are n-1 lines in the plane:
For L(n) and L(n+1),
In Zone X, intersection of L(n) and L(n+1) exists -> split in 4
In other Zones, 
1) 