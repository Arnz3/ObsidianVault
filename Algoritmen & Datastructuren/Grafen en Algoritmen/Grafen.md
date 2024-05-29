## Definities
- een __graaf__ heeft toppen en bogen
- __adjacente toppen__: verbonden door een boog
- __graad__ van de top is aantal buren
- __orde__ van de graaf is aantal toppen
- __grootte__ van de graaf is het aantal bogen

Een graaf met orde $n$ en grootte $m$ is een $(n,m)$-graaf

$V(G)$ = toppenverzameling 
$E(G)$= bogenverzameling

#### andere
__dichte graaf__: als de meeste toppen aanwezig zijn
__multigraaf__: toppen kunnen door meer dan 1 boog verbonden worden
__simpele graaf__: graaf zonder multibogen

__gerichte graaf__: alle bogen zijn gericht (pijlen)
__gewogen graaf__: elke boog heeft een getal, dit is het gewicht

__nabuurschap__ van een top $v$ van een graaf $G$ wordt gedefinieerd als $N_{g}(v) = {u \in V(G) | vu \in E(G)}$

__geïsoleerde top__ is een top met graad 0
__eind top__ is de top met graad 1


## Euler
Zij $G$ een graaf met $n$ toppen en $m$ bogen
Zij $V(G) = { v_{1}, ...,v_{n} }$
dan: $\sum_{i=1}^{n} deg(v_{i}) = 2m$ 

Wanneer de som van de graden van de toppen berekend wordt, wordt elke boog 2x meegeteld, eenmaal van elk van zijn 2 incidente toppen.

#### begrippen
__wandeling__ van $v_{0}$ naar $v_{i}$ is een afwisselende rij van toppen en pijlen, als eind = begin (gesloten wandeling).
__spoor__ wandeling zonder herhalende bogen, aka circuit
__pad__ wandeling zonder herhalende toppen, aka cykel

__Acyclische graaf__ graaf zonder cykels, aka __woud__
__boom__ samenhangende graaf die geen cykels bevat.



