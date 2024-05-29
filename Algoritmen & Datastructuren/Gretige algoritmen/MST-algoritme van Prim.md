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


## complexiteit
#### eenvoudige implementatie
kost $O(nm)$

#### efficiënte implementatie
- gebruikt prioriteitswachtlijnen
- kost reduceren tot $O(m log n)$