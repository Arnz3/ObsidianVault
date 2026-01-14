## Lineaire transformatie
Een transformatie is een __lineaire transformatie__ wanneer die rechte lijnen transformeert in andere rechte lijnen.
### wiskundige eigenschappen
- Het beeld van een som is de som van de beelden
	$L(v + w) = L(v) + L(w)$
- Wanneer men een vector schaalt, schaalt het beeld met dezelfde scalar
	$L(\alpha v) = \alpha L(v)$

## Matrix-vector product
Een matrix-vector product tussen een matrix $A$ en een vector $v$ kan berekend worden als het aantal kolommen van $A$ gelijk is aan het aantal componenten van $v$.

$$
\begin{bmatrix}
\mid & \mid & & \mid \\\
a_{1} & a_{2} & \dots & a_{n} \\\
\mid & \mid & & \mid
\end{bmatrix}
\begin{bmatrix}
v_{1} \\\ v_{2} \\\ \vdots \\\ v_{n}
\end{bmatrix}
=
v_{1}
\begin{bmatrix}
\vert \\\ a_{1} \\\ \vert
\end{bmatrix} +
v_{2}
\begin{bmatrix}
\vert \\\ a_{2} \\\ \vert
\end{bmatrix} +
\dots +
v_{n}
\begin{bmatrix}
\vert \\\ a_{n} \\\ \vert
\end{bmatrix} 
$$
## Matrix product
### eigenschap
het matrix product is associatief. Dit betekent dat
$$
A(BC) = (AB)C
$$
Voor alle matrices waarvoor de uitdrukking is gedefinieerd
__niet commutatief!__
$$
AB \neq BA
$$
### Transponeren van een matrix
Elke matrix kan getransponeerd worden
=> rijen en kolommen van plaats verwisselen
$$
(A^\intercal)^\intercal = A
$$
### inwendig product als matrixproduct
$$
a \cdot b = a^\intercal b
$$
### eigenschappen
- matrixproduct is links en recht distributief tov $+$ 
	- $A(B+C) = AB + AC$
	- $(B+C)A = BA + CA$
- Voor elk reëel getal $\alpha$ geldt dat 
	- $\alpha(AB) = (\alpha A) B = A(\alpha B)$ 
- Matrixproduct interageert met het transponeren van matrices
	- $(AB)^\intercal = B^\intercal A^\intercal$

## inverse van een matrix
Als $A \in \mathbb{R}^{n \times n}$ een vierkante matrix is waarvoor een matrix $B$ bestaat waar geldt:
$$
AB = I_n = BA
$$
Dan zeggen we dat matrix $A$ inverteerbaar is en dat $B$ de inverse matrix is van $A$, wat we noteren als 
$$
B = A^{-1}
$$
De __rang__ van een matrix is het aantal lineaire onafhankelijke kolommen van die matrix
### Eigenschappen
- Een vierkante matrix $A \in \mathbb{R}^{n \times n}$ is inverteerbaar als en slechts als de rang van de matrix $A$ gelijk is aan $n$
- A is inverteerbaar als de determinant niet gelijk is aan nul
- Als $A$ en $B$ inverteerbare matrices zijn in $\mathbb{R}^{n \times n}$, dan is hun product inverteerbaar en er geldt:
	- $(AB)^{-1} = B^{-1} A^{-1}$

De inverse van een $2 \times 2$ matrix bestaat als de discriminant niet nul is en wordt gegeven door
$$
A^{-1} = \frac{1}{ad-bc} 
\begin{bmatrix} 
d & -b \\\ -c & a
\end{bmatrix}
$$

