De wortel is de eerste actieve top. Tijdens elk stadium in het doorlopen worden alle toppen adjacent vanuit de huidige actieve top onderzocht op toppen die nog niet eerder bezocht zijn. M.a.w. breed zoek proces

## pseudocode
```
INPUT: graaf G = (V, E)
OUTPUT: labels l voor G, bogenverzameling B van breedte-eerst-woud, rij P met voor elke top zijn ouder in het woud
l(v) <- 0, VA v in V // kost O(n)
i <- 0; B <- null; Q <- null
for all v in V met l(v) = 0 do
	i <- i + 1; l(v) <- i
	Q.enqueue(v)
	while Q != null do // doet dit 2m keer, elke boog vanuit toppen
		w <- Q.dequeue()
		for all x in V met x ~ w en l(x) = 0 do
			i <- i+1; l(x) <- i
			B <- B U {wx}
			P[x] <- w
			Q.enqueue(x)
return S, P
```

## complexiteit
Wanneer BFS van een graaf $G$ met $n$ toppen en $m$ bogen gebeurt met de bedoeling om alle toppen systematisch te bezoeken. Dan wordt elke boog hoogstens 2x bekeken, eenmaal vanuit elk van zijn eindtoppen. Een geisoleerde top hoogstens 1 maal, dus $\Theta(n+m)$ 