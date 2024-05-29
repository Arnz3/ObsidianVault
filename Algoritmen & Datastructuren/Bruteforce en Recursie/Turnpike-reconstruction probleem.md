Gegeven $n$ punten $p_{1}, ..., p_{n}$ gelegen op de x-as. Noem de $x_{i}$ de $x$-coördinaat van het punt $p_{i}$.
Verder veronderstellen we dat $x_{1} = 0$ en dat de punten in volgorde van links naar rechts gegeven zijn.

## complexiteit
Deze $n$ punten bepalen $m = n(n-1)/2$ mogelijke afstanden $d_{1}, ..., d_{m}$ tussen elk paar punten; deze afstanden zijn van de vorm $|x_{i} - x_{j}|$, met $i \neq j$. Het is duidelijk dat, de gegeven verzameling punten, de verzameling afstanden kan _geconstrueerd_ worden in $O(n²)$ tijd. 

## Omgekeerd probleem
Gegeven afstanden $d_{j}$, reconstrueer punten $x_{i}$, onderstel steeds $x_{1} = 0$ 

### algoritme
__Probleem:__ recursief op te lossen
- bepaal punten $D = \{ d_{1}, ... , d_{k}\}$ met $x_{1} ... x_{i}$ en $x_{j} ... x_{n}$ reeds ingevuld $(d_{1} \leq ... \leq d_{k})$ 
__Backtracking algoritme
- als $x_{i+1} = x_{n} - d_{k}$ mogelijk, bepaal punten voor $D'$ en $x_{1} ... x_{i+1}$ en $x_{j}...x_{n}$ 
- als $x_{j-1} = x_{1} + d_{k}$ mogelijk, bepaal punten voor $D'$ en $x_{1} ... x_{i}$ en $x_{j-1}...x_{n}$ 
__Stopgeval:__ $D = \emptyset$ 
__Oproepen met__ $x_{1} =0$ en $x_{n} = d_{m}$ ingevuld
### complexiteit
Er is momenteel nog geen enkel algoritme gekend dat gegarandeerd werkt in polynomiale tijd. Het algoritme dat we hier gezien hebben, vraagt meestal $O(n² log n)$ uitvoeringstijd, maar wordt in het slechtste geval exponentieel.  