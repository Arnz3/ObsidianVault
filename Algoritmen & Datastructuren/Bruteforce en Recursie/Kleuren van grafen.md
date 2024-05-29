__Kleuren van een graaf__ is toekennen van kleuren aan toppen zodanig dat adjacente toppen verschillende kleur hebben.

__k-kleuring__ kleuring van $k$ kleuren bevat
__Chromatisch getal__  $\chi(G)$, kleinste $k$ waarvoor $k$-kleuring bestaat

__Een complete graaf__ is een graaf van met de eigenschap $\chi(K_{n}) = n$ 
__Een bipartiete graaf__ is een graaf met de eigenschap $\chi(G) = 2$ 

__Een cykelgraaf__ heeft eigenschappen, $\chi(C_{n}) = 2$ voor even $n \geq 4$, $\chi(C_{n}) = 3 voor oneven $n \geq 3$ 

### Klieken
Een __Kliek__ in graaf $G$ is een deelverzameling toppen zodat elk paar toppen verbonden is door een boog
Het __kliekgetal__ $\omega(G)$ is het aantal toppen in de grootst mogelijke kliek
$\omega(G) \leq \chi(G)$ 

### Planaire grafen
Een __planaire graaf__ kan getekend worden zonder snijdende bogen.
Elke planaire graaf kan gekleurd worden met ten hoogste 4 verschillende kleuren

### algoritme
Gretig algoritme voor het kleuren van grafen
INPUT: graaf $G$ met $V = \{v_{1}, ..., v_{n}\}$ 
OUTPUT: kleuring $col(v_{i}), \forall v_{i} \in V$ 
for i from 1 to n do
	sorteer de kleuren van de reeds gekleurde toppen die adjacent met $v_{i}$ zijn, in niet-dalende volgorde, en zij $L_{i}$ de corresponderende lijst
	$c \leftarrow 1$ 
	while kleur c behoort tot lijst $L_{i}$ do
		$c \leftarrow c +1$
	$col(v_{i}) \leftarrow$ kleur $c$ 
return $col(v_{i}), \forall v_{i} \in V$ 