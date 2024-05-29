Men beschouwt $n$ objecten met gegeven gewicht en gegeven winsten. Verder is ook de totale capaciteit $M$ van de knapsack gegeven. Er wordt gevraagd een invulling van de knapsack te zoeken, zodanig dat de totale winst maximaal is, en het totale gewicht < M.

### Backtracking algoritme
Eenvoudig algoritme waar alle $2^{n}$ mogelijke $n$-tallen stap voor stap te proberen. Wanneer $n$-tal gegenereerd is, wordt gecontroleerd of de oplossing aanvaardbaar is. 
#### pseudo
INPUT: $X_{l} = (x_{0}, ..., x_{l-1})$ in opbouw; huidig beste $Y$ met winst $P(Y)$ 
if $l >n$ then
	if $W_{n} \leftarrow \sum_{i=0}^{n-1} w_{i}x_{i} \leq M$ then
		if $P_{n} \leftarrow \sum_{i=0}^{n-1} p_{i}x_{i} > P(Y)$ then
			$Y \leftarrow X_{n}$; $P(Y) \leftarrow P_{n}$ 
 else
	 $x_{l} \leftarrow 1$; $Knapsack1(l+1)$ 
	 $x_{l} \leftarrow 0$; $Knapsack1(l+1)$


#### complexiteit
Er zij $2^{n} n$-tallen, controleren van $n$-tal kost $O(n)$, dus totale kost is $O(n2^{n})$

Dit algoritme is niet praktisch bruikbaar voor $n > 40$ 
We kunnen proberen takken die niet tot oplossingen kunnen leiden, uit de boom te snoeien zonder ze volledig uit te werken. Vb: als reeds $W_{l+1} > M$ dan, $X_{l}$ niet verder aanvullen.

### Knapsack2
INPUT: $X_{l} = (x_{0}, ..., x_{l-1})$ in opbouw; huidig beste $Y$ met winst $P(Y)$ 
if $(l > n)$ then
	$P_{n} \leftarrow \sum_{i=0}^{n-1} p_{i}x_{i}$ 
	if $P_{n} > P(Y)$ then
		$Y \leftarrow X_{n}$ 
		$P(Y) \leftarrow P_{n}$ 
else
	$x_{l} \leftarrow 1$ 
	$W_{l+1} \leftarrow \sum^{l}_{i=0} w_{i}x_{i}$ 
	if $W_{l+1} \leq M$ then
		$Knapsack2(l+1)$
	$x_{l} \leftarrow$;$Knapsack2(l+1)$ 

### Snoeifunctie voor Knapsack

#### rationalKnapsack als bounding function
Kies telkens object met beste winst/gewicht verhouding, voeg toe zolang capaciteit niet overschreven, op het einde aanvullen met deel van volgende object

INPUT: $(p_{0}, ..., p_{n-1}; w_{0},...,w_{n-1}; M)$ 
OUTPUT: optimale winst
sorteer objecten $p_{0} / w_{0} \geq ... \geq p_{n-1}/w_{n-1}$
$P \leftarrow 0$; $W \leftarrow 1$ 
for i form 1 to n-1 do
	$x_{i} \leftarrow 0$ 
for i form 1 to n-1 do 
	if $W + w_{i} \leq M$ then
		$x_{i} \leftarrow 1$; $W \leftarrow W + w_{i}$; $P \leftarrow P + p_{i}$
	else
		$x_{j} \leftarrow (M - W)/w_{i}$; $W \leftarrow M$;
		$P \leftarrow P + x_{i}p_{i}$ 
		return $P$ 



INPUT: $X_{l} = (x_{0}, ..., x_{l-1})$ in opbouw; huidig beste $Y$ met winst $P(Y)$ 
if $l > n$ then
	$P_{n} \leftarrow \sum_{i=0}^{n-1} p_{i}x_{i}$ 
	if $P_{n} > P(Y)$ then
		$Y \leftarrow X_{n}$ 
		$P(Y) \leftarrow P_{n}$ 
else
	$B_{l} \leftarrow P_{l} + RKnap(p_{l,...,n-1}; w_{l, ... , n-1};M-W_{l})$ 
	if $B_{l} > P(Y)$ then 
		$x_{l} \leftarrow 1$; $W_{l+1} \leftarrow \sum_{i=0}^{l} w_{i}x_{i}$
		if $W_{l+1} \leq M$ then
			$Knapsack3(l+1)$
		$x_{l} \leftarrow 0$; $Knapsack3(l+1)$ 