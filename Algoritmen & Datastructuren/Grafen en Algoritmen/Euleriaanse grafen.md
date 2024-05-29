__Euleriaans spoor__ is een spoor of circuit dat alle bogen bevat
__Euleriaans circuit__ is een gesloten spoor dat alle bogen bevat

#### Stellingen 
zij G samenhangende multigraaf
- $G$ is euleriaans als en slechts als de graad van elke top even is
- $G$ is traverseerbaar als en slechts als $G$ 2 toppen heeft met oneven graad


Een samenhangende multigraaf $G$ bevat een euleriaans spoor als en slechts als $G$ precies 2 toppen met oneven graad heeft. 
### bepalen Euleriaans Circuit
```
INPUT: samenhangende graaf G, elke top heeft even graad
OUPUT: euleriaans circuit C in G
start in een willekeurige top v
construeer een  circuit C (dit eindigt in v)
while bogen in G\C do 
	kies een top w in C met een ongebruikte boog
	start in w
	construeer een circuit C' van ongebruikte bogen
	voeg C' tussen in C bij w
return C
```
