Gegeven een reeks punten in het vlak, bepaal het puntenpaar dat het dichtst bij elkaar ligt.

## werkwijze
- vlak opsplitsen door verticale lijn
- kleinste afstand is minimum van 
	- kleinste afstand $d_{l}$ ts. 2 punten links
	- kleinste afstand $d_{r}$ ts. 2 punten rechts
	- kleinste afstand $d_{c}$ ts. een punt link en punt rechts

### bepalen $d_{c}$ 
zij $d = min(d_{l}, d_{r})$ 
- enkel strook van breedte $2d$ bekijken
- exhaustief alle punten in strook bekijken

```
INPUT: punten (p1, ... , pm) in 2d-strook
OUTPUT: dichtste (pk, pl) met d(pk, pl) < d
dmin <- d
for i from 1 to m-1 do
	for all j waarvoor yj > yi do
		if |yj - yi| > d then
			break {ga naar volgende pi}
		else if d(pi, pj) < dmin then
			dmin <- d(pi, pj)
			k <- i en l <- j
if dmin < d then
	return k & l 
``` 

