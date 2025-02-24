### Chain & Independent set

####  最长链长度 = 最小反链划分数
##### pf.
	trivial, $/omega(P)<=t$
	For $/omega(P)>=t$,
		A1 = the min elem set of S
		Ai = the min elem set of S\{A1 U A2 ... A(i-1)}
		... Am
		only need to prove: $/omega(P)>=m$
		It's trivial to construct a chain with len of m
		$m<=/omega(P)$
		Q.E.D
