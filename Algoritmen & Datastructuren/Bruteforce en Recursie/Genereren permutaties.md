## permutaties van lengte 4
```
INPUT: rij (a0, a1, a2, a3)
OUTPUT: alle permutaties van deze rij
for elk getal uit de rij do 
	zet getal op 4e positie
	for elk getal uit de rij do 
		zet getal op 3d positie
			for elk getal uit de rij do
				zet getal op 2e positie
				zet reseterende getal op 1e positie
```

## permutaties van willekeurige lengte
```
INPUT: rij (a0, ..., an-1)
OUTPUT: alle permutaties van deze rij
for elk getal uit de rij do
	zet getal op de positie n 
	genereer alle permutaties van de overblijvende (n-1) getallen
```