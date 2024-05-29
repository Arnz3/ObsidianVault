Hierbij gaat men sorteren door omwisselen, naast elkaar staande element uit de rij worden met elkaar vergeleken en worden verwisseld als ze niet in de goede volgorde staan. 

## pseudocode

```
INPUT: een rij (a1, ..., an)
OUTPUT: de rij in stijgende volgorde
for i from n to 2 do
	for j from 1 to i - 1 do 
		if aj > aj+1 then 
			verwissel aj en aj+1
```


## complexiteit

_BubbleSort heeft tijdscomplexiteit T(n) = 0(n²)_

Het aantal vergelijking $C(n)$ in **Bubblesort** is hetzelfde voor alle mogelijke rijen van lengte $n$, 
$C(n) = n(n-1)/2$. Het aantal verwisselingen $S(n)$ hangt af van de inputrij, en kan variëren van $S_{b}(n) = 0$ in het beste geval tot $S_{s}(n) = C(n)$ in het slechtste geval. De totale complexiteit is dus $T(n) = O(n²)$ 
