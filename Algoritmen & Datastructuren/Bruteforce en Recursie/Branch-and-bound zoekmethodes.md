Heel wat problemen waar gevraagd wordt een minimale of maximale configuratie van een of ander soort te bepalen. Deze kunnen veelal aangepakt worden door een backtracking zoekproces over een boom van alle mogelijkheden.

Dikwijls kunnen toppen uit een boom geëlimineerd worden.

### maximalisatieprobleem
Zij $X = (x_{0}, ..., x_{l-1})$ een partiële aanvaardbare oplossing voor een __maximalisatieprobleem__. We definiëren $P(X)$ als de grootst mogelijk winst van een aanvaardbare oplossing die en afstammeling van $X$ in backtrackboom is, m.a.w. de maximum winst over een aanvaardbare oplossing $X' = (x_{0}', x_{1}', ..., x_{n-1}')$ met $x'_{i} =x_{i}$ voor alle $i$.

Als $X =()$, dan $P(X)$ de optimale winst voor gegeven instantie van probleem is. Exact berekenen van $P(X)$ kan meestal enkel door het corresponderende deel van de backtrackboom te doorlopen. We kunnen wel een bovengrens voor $P(X)$ gebruiken om te snoeien. 

### bounding function
Wordt gedefinieerd als een reële functie $B(X)$, gedefinieerd op een verzameling van toppen uit de backtrackboom, die voldoet aan de eigenschap dat $B(X) \geq P(X)$ voor elke aanvaardbare oplossing in de deelboom met wortel $X$. 

Om te snoeien gaan we als volgt te werk: Zij $X = (x_{0}, ..., x_{l-1})$  de huidige partiële oplossing, en zij $P_{opt}$ de huidige grootste winst. Als $B(X) \leq P_{opt}$, dan weten we dat 
	$P(X) \leq B(X) \leq P_{opt}$ 
Dit betekent dat geen afstammeling van $X$ de huidige grootste winst kan verbeteren . We kunnen de deelboom $X$ dus snoeien

#### vereisten
Voor een goede __bounding function__ $B(X)$ zijn (1) eenvoudig en snel te berekenen (2) een goede benadering van $P(X)$ 