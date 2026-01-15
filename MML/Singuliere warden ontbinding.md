=> deze laat toe om elke matrix $A$ te schrijven als een product van 3 matrices
$$
A_{n \times m} = U_{n \times n} \mathcal{E}_{n \times m} V^\intercal_{m \times m}
$$
In deze ontbinding zijn $U$ en $V$ orthogonale matrices.

$\mathcal{E}$ is een diagonaalmatrix met op de diagonaal elementen
$$
\mathcal{E}_{i,i} = \sigma_i
$$
### eigenschappen
- Elementen van $\mathcal{E}$ die niet op de diagonaal staan zijn gelijk aan nul
- $\sigma_i$ zin de __singuliere waarden__ van $A$
- Kolommen van $U$ zijn 'links singuliere vectoren' van $A$
- Kolommen van $V$ zijn 'rechts singuliere vectoren' van $A$

## Zuinige SVD
Wanneer $A$ een 'lange smalle' matrix is $(n > m)$, dan heeft $A$ hoogstens $m$ singuliere waarden verschillend van nul
-> In dit geval zijn enkel de eerste $m$ kolommen van $U$ van belang

Dus wanneer $n > m$ 
$$
A_{n \times m}  = \hat{U}_{n \times m} \hat{\mathcal{E}}_{m \times m} V^\intercal_{m \times m}
$$
Voor $\hat{U}$ is het belangrijk op te merken dat enkel de kolommen orthonormaal zijn. dus
$$
\hat{U}^\intercal \hat{U} = I_{m \times m}
$$
maar 
$$
\hat{U} \hat{U}^\intercal \neq I_{n \times n}
$$
## Uitwendig product
=> alternatieve manier om product van 2 matrices te berekenen
- werkt enkel als $a$ en $b$ evenveel componenten bevatten
$$
\begin{bmatrix}
\vert \\\
a \\\
\vert
\end{bmatrix}
\begin{bmatrix}
- & b^\intercal & -
\end{bmatrix}
$$
Op plaats $(i,j)$ van het resultaat komt het product van de $i$-de component van $a$ en $j$-de component van $b$
Dit is het uitwendig product
### Matrix product
-> een algemeen matrix product $AB$ kan steeds worden uitgedrukt als de som van uitwendige producten van kolommen van $A$ en de rijen van $B$

## Lage rang benadering
Door een matrixproduct te bekijken als een som van uitwendige producten kunnen we de zuinige SVD ook als volgt neerschrijven
$$
A = \sum^{m}_{j=1} \sigma_j u_j v_j^\intercal = 
\sigma_1 u_1 v_1^\intercal + \dots + \sigma_m u_m v_m^\intercal
$$
Als we de som afbreken na $r$ termen, krijgen we een benadering van $A$. Dit is een som van matrices elk van rang $r$
-> Deze is de beste benadering van rang $r$ voor $A$

Deze afwijking wordt gemeten met __Frobenius-norm__ 
maw
$$
\tilde{A}_{n \times m} = \tilde{U}_{n \times r} \tilde{\mathcal{E}}_{r \times r} \tilde{V}_{m \times r}^\intercal
$$

## Eckart - Young
De beste benadering van rang $r$ van een matrix $A \in \mathbb{R}^{n \times m}$ met $n \ge m$ wordt gegeven door
$$
A_r = \sum^{r}_{j=1} \sigma_j u_j v_j^\intercal = 
\sigma_1 u_1 v_1^\intercal + \dots + \sigma_r u_r v_r^\intercal
$$
- Als $B \in \mathbb{R}^{n \times m}$ een andere matrix is van hoogstens rang $r$ dan geldt:
$$
||A - A_r ||_F < ||A-B||_F
$$
### Frobenius-norm
Het symbool $||A||_F$ staat voor de __Frobenius-norm__ van de matrix $A$
=> men beschouwt alle elementen van $A$ als een lange vector met $n \times m$ elementen en men berekent de 'gewone' norm
