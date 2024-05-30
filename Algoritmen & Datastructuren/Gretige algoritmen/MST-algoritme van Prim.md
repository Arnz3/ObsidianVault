voorlopige boom telkens uitbreiden met kleinste boog die top uit boom verbindt met top buiten boom

## pseudocode
```
INPUT: gewogen G =(V,E) met n toppen en m bogen
OUTPUT: bogenverzameling Et van MST T van G
zij x0 willekeurige top van G
Vt <- {x0}; Et <- null
while |Et| < n-1 do 
	zij e' = x'y' een boog zodat w(e') = min{w(e)|e=xy,x in Vt,y in V\Vt}
	Vt <- Vt U {y'}
	Et <- Et U {e'}
return Et
```

## correctheid
Algoritme van prim levert minimale-kost opspannende boom voor samenhangende gewogen graaf
#### bewijs
Zij $G$ de graaft met $n$ toppen en zij $T$ de boom die geleverd wordt door _MSTPrim_. Het is gemakkelijk in te zien dat $T$ een opspannende boom van $G$ is. 
- Stel $T$ geen MST van $G$
- zij $H$ MST van $G$ met max aantal bogen gemeenschappelijk met $T$
- $e_{j}$ de boog die in stap $j$ wordt toegevoegd aan $T$. 
- $e_{i}$ de eerste boog van $T$ die niet tot $H$ behoort. 
- De graaf $H + e_{i}$ bevat unieke cykel $C$. 
- $C$ bevat ook boog $e_{0}$ die $U$ en $V_{T} - U$ verbindt, met U toppen verzameling deelgraaf
- Dan is $T' = H + e_{i} - e_{0}$ een opspannende boom.
- $w(e_{i}) \leq w(e_{0}),$ zodat $w(T') \leq w(H)$ 
- aangezien $H$ MST is, ook $T'$ een MST
- maar $T'$ meer bogen gemeenschappelijk met $T$ dan $H$ (contradictie)

## complexiteit
#### eenvoudige implementatie
kost $O(nm)$

#### efficiënte implementatie
- gebruikt prioriteitswachtlijnen
- kost reduceren tot $O(m log n)$