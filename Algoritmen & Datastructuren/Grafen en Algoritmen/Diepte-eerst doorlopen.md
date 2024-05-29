gegeven: graaf $G = (V, E)$, start top $v \in V$ 
1. Alle toppen systematisch doorlopen door steeds zo diep mogelijk verder te gaan
2. bij doodlopende top wordt op de stappen teruggekeerd


## pseudocode
```
INPUT: graaf G = (V, E)
OUPUT: labeling dfi(v) voor toppen v in V met df indices
for all v in V do
	dfi(v) <- 0 ("onbezocht")
i <- 0
for all v in V do
	if dfi(v) == O then
		DFS(v)
```
#### recursieve hulpmethode DFS(v)
```
i <- i + 1
dfi(v) <- i
for all w in V: w ~ v do
	if dfi(w) == 0 then
		DFS(w)
```
