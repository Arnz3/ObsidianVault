## stelsel van lineaire vergelijkingen
Een stelsel lineaire vergelijkingen 
$$
Ax = b
$$
is oplosbaar als en slechts als $b$ behoort tot de __kolomruimte__ van $A$
$$
b \in Col(A)
$$
$$
b \in span\{a_1, a_2, \dots, a_n \}
$$
## Gaussische eliminatie
=> stelsel omvormen tot equivalente bovendriehoeksmatrices
- dit aan de hand van elementaire rijoperaties
- daarna is achterwaartse substitutie mogelijk

## LU matrixdecompositie
We beschouwen vierkante stelsels
-> Gaussische eliminatie rechtstreeks toegepast op $A$
- steeds een pivot element ($\neq 0$ ), waaronder we nullen wensen.
- pivot element op rij $i$ is $a$ en we wensen een element op rij $j$, in dezelfde kolom $k$  ($=b$) de waarde 0 te geven, dan:
	- $R_j \leftarrow R_j - (b/a) R_i$
- equivalent met $E_{i,k}$ 
- het volledige proces is dus
$$
E_{i,j} \cdot E_{k,l} \cdot A = U
$$
- Door alle elementaire matrices te inverteren kunnen we dit ook schrijven als 
$$
A = E_{i,j}^{-1} \cdot E_{k,l}^{-1} \cdot U
$$
of 
$$ 
A = LU
$$
### met rijverwisseling
-> LU-decompositie faalt wanneer pivot element 0 is
- oplossing: wisselen van rijen
_Voorbeeld_
$$
P_{13}A = 
\begin{bmatrix}
0 & 0 & 1 \\\
0 & 1 & 0 \\\
1 & 0 & 0 
\end{bmatrix}
\begin{bmatrix}
0 & 4 & 1 \\\
1 & 2 & 1 \\\
3 & 8 & 1 
\end{bmatrix}
= 
\begin{bmatrix}
3 & 8 & 1 \\\
1 & 2 & 1 \\\
0 & 4 & 1 
\end{bmatrix}
$$
$P_{13}$ is de eenheidsmatrix met de eerste en derde rij verwisselt
-> we wisselen na uitwerken opnieuw om zo groot mogelijk pivot element te hebben
$$
U = E_{32}P_{23}E_{21}P_{13}A
$$
### eigenschap
Voor elke inverteerbare vierkante matrix $A$ bestaat er een permutatiematrix $P$, een benedendriehoeksmatrix $L$ en een bovendriehoeksmatrix $U$ zodat
$$
PA=LU
$$

## Oplossen van stelsels
We wensen volgend stelsel op te lossen $Ax = B$
- Door LU weten we dat $PA = LU$
- dus $PAx = Pb \iff LUx = Pb$
Los eerst op met voorwaartse substitutie
$$
Ly = Pb
$$
Vervolgens gebruik je door achterwaartse substitutie
$$
Ux = y
$$
## De inverse matrix
De inverse matrix van een niet-singuliere vierkante matrix $A \in \mathbb{R}^{n \times n}$ is de matrix $X$ waarvoor geldt dat
$$
AX = I_n \iff
\begin{bmatrix}
\vert & \vert && \vert \\\
x_1 & x_2 & \dots & x_n \\\
\vert & \vert && \vert 
\end{bmatrix}
= I_n
$$

Dit betekent dat $Ax_i = i$- de kolom van $I_n$
Het vinden van de inverse matrix $A$ is het oplossen van $n$ stelsels met telkens $A$ dezelfde matrix en rechterleden kolommen van eenheidsmatrix

## Determinant
=> karakteristiek getal van elke vierkante matrix
- Determinant driehoeksmatrix = product diagonaal
- Determinant vierkante matrix -> via LU-decompositie
$$
det(AB) =det(A) det(B)
$$
$$
A = LU \iff det(A) = det(L)det(U)
$$
$det(L) = 1$ want elementen op diagonal = 1
$det(U) =$ elementen op de diagonaal
$$
det(A) = det(U)
$$
## strijdige stelsels
=> aantal vergelijkingen is groter dan aantal onbekenden

we kunnen proberen en benadering $x^*$ te vinden zodat
- $Ax^*$ zo dicht mogelijk bij $b$

Aangezien $Ax^*$ behoort tot de kolomruimte van $A$ zoeken we de vector zo dicht mogelijk bij $b$
- Dit is uiteraard dan de orthogonale projectie van $b$ op de vectorruimte $span\{col(A)\}$ 

We weten dat $A^\intercal A$ een belangrijke rol speelt bij orthogonale projectie:
$$
Ax = b
$$
$$
A^\intercal Ax = A^\intercal b
$$
Als we aannemen dat de kolommen van $A$ lineair onafhankelijk zijn dan is $A^\intercal A$ inverteerbaar en 
$$
x^* = (A^\intercal A)^{-1} A^\intercal b
$$
