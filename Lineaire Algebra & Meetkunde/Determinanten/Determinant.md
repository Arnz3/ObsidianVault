Een determinant is een afbeelding met de eigenschappen: 
__D-1__ $f(\mathbb{I}_{n}) = 1$ 
__D-2__ $f(A)$ verandert van teken als men in de matrix $A$ twee rijen van plaats wisselt;
__D-3__ $f$ is lineair in de eerste rij

#### extra eigenschappen
Een afbeelding $f: \mathbb{R}^{n \times n} \to \mathbb{R} : A \mapsto f(A)$ die aan de eigenschappen D-1, D-2 en D-3 voldoet, voldoet eveneens aan de volgende eigenschappen:
__D-4__ $f$ is lineair in rij $i$ voor elke $i \in \{1, 2, ..., n\}$;
__D-5__ als er in de matrix $A$ een nulrij is, of als er twee gelijke rijen zijn in $A$, dan is $f(A) = 0$ 

Als $f: \mathbb{R}^{n \times n} \to \mathbb{R} : A \mapsto f(A)$ een determinantafbeelding is , dan geldt:
1. als $A$ een driehoeksmatrix is, dan is $f(A)$ gelijk aan het product van de diagonaalelementen in $A$ ($f(A) = \prod^{n}_{i=1}(A)_{ii}$)
2. $A$ is inverteerbaar als en slechts als $f(A) \neq 0$
3. $f(A \cdot B) = f(A).f(B)$ voor elke twee matrices $A$ en $B$ in $\mathbb{R}^{n \times n}$
4. $f(A^{T}) = f(A)$ 
##### gevolg
1. Als een 'determinantafbeelding' $f$ bestaat, dan volgt dus dat $f(A)$ volledig bepaalt/determineert of de matrix $A$ al dan niet inverteerbaar is. 
2. Als $f$ een determinantafbeelding is, en de matrix $A$ is inverteerbaar, dan is $f(A^{-1}) = \frac{1}{f(A)}$ 

#### cofactoren & minoren 
Zij $A$ een $(n \times n)$-matrix. Voor elke $i,j \in \{1,...,n\}$ is.
- de $ij$-de __cofactor__ $C_{ij}$ van $A$ het geheel van de termen in de formule van $det(A)$ waarin $a_{ij}$ optreedt, na afzonderen van $a_{ij}$,
- de $ij$-de __minor__ van $A$ de $((n-1) \times (n-1))$-matrix $M_{ij}$, verkregen door uit $A$ de $i$-de rij en $j$-de kolom te schrappen.

### adjunctmatrix
Voor een vierkante matrix $A \in \mathbb{R}^{n \times n}$ vormen we de matrix
adj($A$)$= (C_{ij})^{T}_{1 \leq i \leq n,1\leq j \leq n} =$ de getransponeerde van de cofactorenmatrix,  
die we de __adjunctmatrix__ of __toegevoegde matrix__ van $A$ noemen.
(ookwel getransponeerde cofactoren matrix)


Als de matrix $A \in \mathbb{R}^{n \times n}$ inverteerbaar is, met andere woorden als $det(A) \neq 0$, dan geldt dat 
$A^{-1} = \frac{1}{det(A)} adj(A)$

