Gegeven is een complete gewogen graaf $G$ met $n$ toppen. Men is opzoek naar een hamiltoniaanse cykel in $G$ met kleinste gewicht.

## algoritme
Maak eerste een minimale-kost opspannende boom $T$ in $G$. Vervolgens wordt een diepte-eerst doorlopen van $T$ uitgevoerd, deze bepaalt de volgorde van de toppen en maakt de cykel $C$. 

### eigenschap
Voor een gewogen complete graaf $G$ is het gewicht van een hamiltoniaanse cykel van $G$ bekomen door ETSPGreedy minder dan tweemaal het gewicht van een minimale hamiltoniaanse cykel van $G$.

#### bewijs
$w(T) \leq w(C_{min})$ 
DFS ~ euleriaans circuit $H$ met $w(H) = 2w(T)$ 
$w(C) \leq w(H)$ door driehoeksongelijkheid

## psuedo
```
INPUT: gewogen complete graaf G met n >= 3 toppen, die voldoet aan de driehoeksongelijkheid
OUTPUT: hamiltoniaanse cykel C met laag gewicht in G
bepaal een minimale-kost opspannende boom T in G
doe een diepte-eerste doorlopen van T; dit geeft een volgorde vi1, ..., vin
C <- vi1, vi2, ... , vin, vi1
```
