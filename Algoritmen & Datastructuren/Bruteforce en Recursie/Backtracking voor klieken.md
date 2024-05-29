### bepalen van klieken
Een __kliek__ is een verzameling toppen die complete deelgraaf in $G$ induceert
een __maximale kliek__ is een kliek die geen deelverzameling van andere kliek is
Een __maximum kliek__ is de grootst mogelijke kliek

#### bepalen van alle maximale klieken
We doen dit via backtracking algoritme, we gaan stap voor stap een kliek in opbouw aanvullen. We houden terwijl de verzameling bij waarmee kan uitgebreid worden.
##### algoritme
INPUT: $X$ = kliek in opbouw; $N_{l}$ = verzameling van toppen die met alle toppen van $X$ adjacent zijn; $C_{l}$ = verzameling van _grotere_ toppen die met alle toppen die met alle toppen van $X$ adjacent zijn
if $C_{l} = \emptyset$ then
	$X$ is maximale kliek als $N_{l} = \emptyset$ 
else
	for all $x \in C_{l}$ do 
		$X \leftarrow X \cup \{x\}$ 
		$N_{l+1} \leftarrow N_{l} \cap$ buren van $x$
		$C_{l+1} \leftarrow C_{l} \cap$ buren van $x$ groter dan $x$ 
		$AllCliques(l+1)$
		$X \leftarrow X \setminus \{x\}$ 

#### bepalen maximum klieken
Eenvoudige aanpassing van $AllCliques$, we houden enkel de grootste kliek bij.
##### bounding function
Zij $X_{l} = \{x_{0}, ..., x_{l-1}\}$ huidige kliek in opbouw
Zij $C_{l}$ = te beschouwen toppen bij uitbreiding $X_{l}$ 
Zij $X'_{l} = \{x_{0}, ..., x_{l-1}, ..., x_{j}\}$ uitbreiding van $X$|ell
dan moet $\{x_{l}, ... x_{j}\}$ kliek in $G[C_{l}]$ zijn
met $G[C_{l}]$: deelgraaf van $G$ geïnduceerd door $W \subset V$ 

Er geldt
	 $B(X) = l + ub(l)$ is een bounding function
 met 
 $mc(l)$: grootte van maximum kliek in $G[C_{l}]$ 
 $ub(l)$: bovengrens voor $mc(l)$ 
##### size bound
Eenvoudige observatie
- $mc(l) \leq |C_{l}|$ 
- kunnen hoogstens alle toppen uit $C_{l}$ toevoegen aan $X$ 
$B(X) = l + | C_{l}|$ 

##### bovengrens door topkleuringen
$\omega(G) \leq \chi(G)$ met $\chi(G)$ chromatisch getal van $G$ 

#### gebruik in bounding function
##### sampling bound
- Eerst kleuring voor ganse graaf bepalen (gretig)
- in elke stap
	- tellen hoeveel kleuren in $G[C_{l}]$ gebruikt worden
##### greedybound
- in elke stap 
	- kleuring voor $G[C_{l}]$ bepalen (gretig)
Vaak te duur in praktijk