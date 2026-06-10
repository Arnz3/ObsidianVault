=> PCA, techniek om de dimensie van data te reduceren en tegelijkertijd zoveel mogelijk info in de data te behouden
- vind een orthonormale basis $c_1$ tem $c_n$ zodat elk datapunt $x \in \mathbb{R}^n$ kan geschreven worden als lineaire combinatie van deze basis vectoren
- coëfficiënten worden gegeven door de inwendige producten van $c_i$ en $x$
- Om de dimensie te reduceren projecteren we elke punt $x$ op de deelruimte opgespannen door de eerste $r$ basisvectoren $c_1$ tem $c_r$ waarbij de waarde $r$ wordt vastgelegd door de gene die de PCA uitvoert
-> werkt meestal op gecentreerde data

### richting
-> verschillende richtingen hebben en grotere of kleinere reconstructiefout
- men zoekt de kleinste reconstructiefout
- we definiëren de reconstructiefout als het gemiddelde van de afstanden tussen de originele punten en hun projecties

## totale variabiliteit
De totale variabiliteit van een dataset is de som van de kwadraten van de singulier waarden.

### Eigenschap
Voor een gecentreerde datamatrix $X \in \mathbb{R}^{m \times n}$ bestaande uit $m$ datapunten waarbij elk datapunt bestaat uit $n$ numerieke attributen worden de principale richtingen $c_1$ tem $c_n$ gegeven door de rechts singuliere vectoren van $X$. Deze principale richtingen zijn zodanig dat voor elke $r$ tussen 1 en $n$ er geen $r$-dimensionale deelruimte bestaat die een strikt kleinere reconstructie fout heeft dan de deelruimte opgespannen door $c_1$ tem $c_r$

M.a.w. als $\tilde{x}^{(i)}$ de loodrechte projectie is van $x^{(i)}$ op de deelruimte opgespannen door $c_1$ tem $c_r$ en $a^{(i)}$ de loodrechte projectie is van $x^{(i)}$ op een andere deelruimte met dimensie $r$ dan geldt:
$$
\frac{1}{m} \sum^{n}_{i=1} ||x^{(i)} - \tilde{x}^{(i)} ||^2 
\le
\frac{1}{m} \sum^{n}_{i=1} ||x^{(i)} - a^{(i)} ||^2
$$
## Moore-Penroose pseudoinverse
We willen de voorwaarden voor een inverteerbare matrix loslaten
=> we definiëren een (links) pseudoinverse die een matrix 'zo goed mogelijk' inverteert
$$
A^{-1} Ax = x
$$
$\forall x$ willen we we kijken of we een matrix $A^+$ kunnen vinden waarvoor geldt:
- $A^+ Ax = x$ voor zoveel mogelijk vectoren $x$

We kijken enkel naar vectoren die niet afgebeeld worden op nul door $A$, omdat het onmogelijk is de originele vector $x$ terug te vinden door toepassen van $A^+$

### berekenen
De SVD laat toe om elke matrix te schrijven als het product van een orthogonale, een diagonaalmatrix en een tweede orthogonale matrix. De orthogonale matrices zijn steeds inverteerbaar
Dus als 
$$
A = U\Sigma V^\intercal
$$
Dan definiëren we de __Moore-Penroose pseudoinverse__ als
$$
A^+ = U\Sigma^+ V^\intercal
$$
waarbij de pseudoinverse $\Sigma^+$ van $\Sigma$ wordt gegeven door:
1. $\Sigma$ te transponeren
2. Elke singuliere waarde $\sigma_i (\neq0)$ te vervangen door $\frac{1}{\sigma_i}$
