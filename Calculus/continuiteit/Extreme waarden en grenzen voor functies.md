## Grenzen voor functies
Gegeven een functie $f$ en een deelverzameling $S \subset dom(f)$ van zijn domein
1. $\alpha \in \mathbb{R}$ is een **ondergrens** voor $f$ over $S$ als  $\alpha \le f(s)$ voor elke $s \in S$.
2. $\beta \in \mathbb{R}$ is een **bovengrens** voor $f$ over $S$ als  $f(s) \le \beta$ voor elke $s \in S$.
$f$ is **begrensd** als hij een boven- en een ondergrens heeft.

Stel $f$ is een functie en $S \subset dom(f)$ is een deelverzameling van zijn domein
1. Een waarde $\alpha \in \mathbb{R}$ is het **infimum** van $f$ over $S$ $\alpha = \displaystyle \inf_{x \in S} f(x)$ , als de grootste ondergrens voor $f$ over $S$ 
	1. voor elke $s \in S$, $\alpha \le f(s)$ en
	2. als $\alpha '$ een ondergrens voor $S$ is, dan is $\alpha ' \le \alpha$
2. Een waarde $\alpha \in \mathbb{R}$ is het **minimum** van $f$ over $S$ $\alpha = \displaystyle \min_{x \in S} f(x)$ , als het een ondergrens is  voor $f$ over $S$ dat gelijk is aan de waarde van $f$ voor een punt van $S$ 
	1. voor elke $s \in S$, $\alpha \le f(s)$ en
	2. voor enkele $s_{min} \in S$, $\alpha = f(s_{min})$. 
	We zeggen dat het een **minimum** bereik over $S$ als deze bestaat.
3. Een waarde $\beta \in \mathbb{R}$ is het **supremum** van $f$ over $S$ $\alpha = \displaystyle \sup{x \in S} f(x)$ , als de kleinste bovengrens voor $f$ over $S$ 
	1. voor elke $s \in S$, $f(s) \le \beta$ en
	2. als $\beta '$ een bovengrens voor $S$ is, dan is $\beta ' \le \beta$
4. Een waarde $\alpha \in \mathbb{R}$ is het **maximum** van $f$ over $S$ $\alpha = \displaystyle \max_{x \in S} f(x)$ , als het een bovengrens is  voor $f$ over $S$ dat gelijk is aan de waarde van $f$ voor een punt van $S$ 
	1. voor elke $s \in S$, $f(s) \le \beta$ en
	2. voor enkele $s_{max} \in S$, $\beta = f(s_{max})$. 
	We zeggen dat het een **maximum** bereik over $S$ als deze bestaat.

## Extreme waarden theorie
Stel $f$ is continu over het gesloten interval $[a,b]$. Dan bereikt $f$ zijn minimum en maximum in $[a,b]$: dus bestaan er punten zodat $s_{min}, s_{max} \in [a,b]$ zodat $f(s_{min}) \le f(s) \le f(s_{max})$  voor alle $s \in [a,b]$. 