De __excentriciteit__ $e(v)$ van een top $v$ in een graaf $G$ is de afstand van $v$ naar een top die het verst van $v$ verwijderd is. $e(v) = max\{ d(u,v) | u \in V(G)\}$ 

De __straal__  van een samenhangende graaf $G$ is gedefinieerd als $rad(G) = min\{e(v) | v \in V(G)\}$ 

__diameter__ $diam(G) = max \{e(v) | v \in V(g)\}  = max\{d(u,v) | u,v \in V(g)\}$ 

__centrum__, de deelgraaf geïnduceerd door de toppen van G waarvan $e(v) = rad(G)$ 
### stelling
Zij $G$ een graaf. Dan geldt dat $rad(G) \leq diam(G) \leq 2rad(G)$ 


## Kortste paden algoritme van Dijkstra
- werkt via labeling strategie
- toppen krijgen voorlopig label = bovengrens voor afstand
- in elke stap: top met kleinste voorlopig label definitief gelabeld + labels buren aanpassen
### pseudocode
```
INPUT: gewogen G, n toppen, u0 in V(G) (booggewichten niet negatief)
OUTPUT: VA v in V(G), gewogen d(u0, v), en voorganger p(v) op evt. kortste u0-v-pad
S <- {u0}; S' <- V(G) - {u0}
l(u0) <- 0; l(v) <- oneindig,VA v in V(G) - {u0}
for all i from 0 to n-1 do
	{(A) Aanpassen labels}
	for all v in S' waarvoor uiv in E(G) do
		if l(v) > l(ui) + w(uiv) then
			l(v) <- l(ui) + w(uiv)
			p(v) <- ui
	{(B) Bepalen volgende top}
	bepaal lmin <- min{l(v)|v in S'}
	zij vj in S' een top met l(vj) = lmin
	d(u0, vj) <- l(vj)
	ui+1 <- vj
	{(C) Aanpassen S en S'}
	S <- S U {ui+1}; S' <- S'\{ui+1}
```

### complexiteit
(A) en (B) zijn het meest tijd rovend. Na uitvoer elke boog hoogstens 1x gebruikt in (A). Als $G$ $m$ bogen heeft, is $T(A) = O(m)$ . In (B) moet top met kleinste label worden bepaald dat zijn |S' - 1|  vergelijkingen. Stap (B) word dus n-1 keer uitgevoerd. $T(B) = O(n²)$. Aangezien $m \leq n(n-1)/2$ is, is $T = O(n²)$ 

Met prioriteitswachtlijnen kunnen we dit verbeteren naar $T = O(m log n)$, door de voorlopig gelabelde toppen te queue'en en hieruit het kleinste label te selecteren.



