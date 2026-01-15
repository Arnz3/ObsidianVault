## orthogonale vectoren
We noemen een verzameling vectoren $q_1$ tem $q_n$ __orthonormaal__ als elk paar vectoren __orthogonaal__ is en als de lengte van elke vector gelijk is aan 1.
$$
q_i \cdot q_j = 0 \vert i \neq j
$$
en 
$$
q_i \cdot q_i = ||q_i||^2 = 1,  \forall i \in \{1,2,\dots, m\} 
$$
### eigenschappen
- Een verzameling orthonormale vectoren is steed lineair onafhankelijk
- Als $q_1$ tem $q_m$ een orthonormale basis is voor een vectorruimte, dan worden de coördinaten tov die basis van een vector $a$ behorend tot die vectorruimte gegeven door de inwendige producten
	- $q_i \cdot a$ voor $i \in \{1,2,\dots,m\}$
- anders
	- $a=(q_1\cdot a)q_1 + (q2 \cdot a)q_2 + \dots + (q_m \cdot a) q_m$

Als men een aantal orthonormale vectoren als kolommen toevoegt aan een matrix $Q$ dan is
$$ 
Q^\intercal Q = I
$$
Enkel als $Q$ een vierkante matrix is geldt ook
$$
QQ^\intercal = I
$$
- Een orthogonale matrix is inverteerbaar en de inverse matrix is gelijk aan de getransponeerde matrix:
$$
Q^{-1} = Q^\intercal
$$
- Als $Q$ een orthogonale matrix is dan geldt voor alle vectoren $x$ en $y$ in $\mathbb{R}^n$ dat 
$$
||x|| = ||Qx||
$$
en
$$
x \cdot y = Qx \cdot Qy
$$
## Projectie op orthonormale basis
Als de vectoren $a_1$ tem $a_m$ tot $\mathbb{R}^n$ behoren en lineair onafhankelijk zijn, dan wordt de projectie op $span \{a_1, a_2, \dots, a_m\}$ bepaald door ene projectiematrix $P \in \mathbb{R}^{n \times n}$
$$
P = A(A^\intercal A)^{-1} A^\intercal
$$
Als $q_1$ tem $q_m$ een orthonormale basis is van de deelruimte waarop we willen projecteren, dan vereenvoudigt de projectiematrix:
$$
P = Q(Q^\intercal Q)^{-1} Q^\intercal = Q(I)^{-1}Q^\intercal = QQ^\intercal
$$
Om de coördinaten tov de vector $q_1$ tem $q_m$ te vinden van de loodrechte projectie van $b \in \mathbb{R}^n$. Gebruiken we volgende formule
$$
x = (A^\intercal A)^{-1} A^\intercal b
$$
die vereenvoudigt tot
$$
x = Q^\intercal b
$$
wat een vector is in $\mathbb{R}^m$

## Gram-schmidt methode
=> vinden van een orthonormale basis
- 1 We construeren de vector $e_1$ tem $e_m$ volgens:
	- start met $e_1 = a_1$
	- vervolgens $e_2$ tem $e_m$ aan de hand van
$$
e_i = a_i - \frac{e_1 . a_i}{e_1 . e_1}e_1 
- \frac{e_2 . a_i}{e_2 . e_2}e_2
- \frac{e_{i-1} . a_i}{e_{i-1} . e_{i-1}}e_{i-1}
$$
- 2 vervolgens wordt $e_i$ genormaliseerd
$$
q_i = \frac{1}{|| e_i ||}e_i, \forall i \in \{1, 2, \dots, m\}
$$
