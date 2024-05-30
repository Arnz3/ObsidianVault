Telkens kleinste boog toevoegen, op voorwaarde dat graaf nog steeds acyclisch is.

## pseudocode
```
INPUT: gewogen G = (V, E) met n toppen en m bogen
OUTPUT: bogenverzameling Et van MST T in G
sorteer E zo dat w(ei1) <= ... <= w(eim)
Et <- null; k <- 0
while |Et| < n-1 do 
	k <- k+1
	if (Et U {eik}) is acyclisch then
		Et <- Et U {eik}
return Et
```

## correctheid
Algoritme van Kruskal levert minimale-kost opspannende boom voor samenhangende gewogen graaf.

__bewijs__
- zij $T$ opspannende boom door Kruskal
- nummer bogen $T$ als $e_{1}, ... e_{n-1}$ zodat $w(e_{1}) \leq ... \leq w(e_{n-1})$
- onderstel $T$ geen MST
- zij $T'$ een MST, zoveel mogelijk bogen gemeen met $T$
- zij $e_{i}$ eerste boog  $\notin T'$ (wel $\in T$)
- $T' + e_{i}$ heeft cykel $C$, zij $e_{0} \in C$ en $\notin T$
- $T' + e_{i} - e_{0}$ is opspannend boom $T''$
- $w(T'') = w(T') + w(e_{i}) - w(e_{0}) \Rightarrow w(e_{i}) \geq w(e_{0})$ (omdat $T'$ een MST)
- Kruskal kiest $e_{i}$ en niet $e_{0}$, maar $e_{0}$ kan wel $\Rightarrow w(e_{i}) \leq w(e_{0})$
- dus $w(e_{i}) = w(e_{0})$, en $T''$ is MST
- maar $T''$ meer bogen gemeen met $T$ dan $T'$ (contradictie)
 
## Implementatie
Hoe controleren dat boog toevoegen cykel zou vormen?

- woud bestaat uit meerdere componenten
- bogen tussen toppen in $\neq$ componenten zijn toegelaten
- bogen tussen toppen in $=$ component zijn niet toegelaten
- voor elke top bijhouden: kleinste top uit zijn component

![[Pasted image 20240530131916.png]]

## complexiteit
- sorteren bogen volgens stijgend gewicht
	- kost $O(m log n)$
- bijhouden woud en controle op cykels
	- kost $O(n²)$
- totale kost $O(m log n + n²)$ 