Een __binaire zoekboom__ is een binaire boom die voldoet aan __ordeningseigenschap__ dat voor elke top $X$ uit de boom alle sleutels in de linkerboom kleiner zijn dan de sleutel van $X$, terwijl alle sleutels in de rechterdeelboom groter zijn dan de sleutel van $X$. 
## bewerkingen
### zoeken in binaire zoekboom
Het zoeken start in de wortel $w$:
- als $x = w.x$ : gevonden
- als $x < w.x$ verder zoeken in linkertak
- als $x > w.x$ verder zoeken in rechtertak

### toevoegen aan binaire zoekboom
1. opzoeken van afwezige sleutel $x$
	-> zoekpad loopt dood in blad
2. toevoegen van sleutel $x$ 
	-> aan einde van doodlopend pad

### verwijderen uit binaire zoekboom
__drie gevallen__
1. verwijderen blad
	-> geen probleem
2. top met 1 kind
	-> herstel link tussen grootouder en kleinkind
3. top met 2 kinderen
	-> vervang sleutel in top door kleinste uit rechterboom
	-> verwijder dit kleinste uit rechterdeelboom 

## complexiteit
__Voor elke bewerking__
- volgt pad van wortel tot evt. in blad
- \# stappen ~ diepte van boom
__Diepte van binaire zoekboom__
- $O(logn)$ in beste geval
- $O(n)$ in slechtste geval
- $O(log n)$ in gemiddelde geval
__Verdere bedoeling__
- boom gebalanceerd houden, met diepte $O(log n)$ 
