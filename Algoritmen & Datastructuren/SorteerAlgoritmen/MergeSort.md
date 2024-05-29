De te sorteren rij wordt opgesplitst in twee deelrijen die half zo lang zijn. Deze worden recursief gesorteerd en vervolgens samengevoegd tot één enkele rij (mergen).

## pseudocode

```
INPUT: een rij (a0, ..., an)
OUPUT: de rij in stijgende volgorde
mergesort deelrij
mergesort deelrij
merge de twee gesorteerde deelrijen tot 1
```

## mergen

Beide rijen doorlopen, herhaaldelijk kleinste van 2 elementen nemen


```
INPUT: 2 gesorteerde rijen a en b
OUPUT: een gesorteerde rij c met de elementen a en b
i <- 0; j <- 0; k <- 0
while elementen over in a en b do
	if ai < bj then
		ck <- ai; i++; k++
	else
		ck <- bj; j++; k++
kopieer rest van a resp. b naar c
```


## complexiteit
De overhead van opsplitsen en _merge_ is $f(n) = \Theta(n)$. De tijdscomplexiteit wordt dus beschreven door de recurrente betrekking $T(n) = 2T(n/2) + \Theta(n)$. $T(n) = \Theta(n log n)$ 

Dit is zowel slechtste- als beste- en gemiddelde-geval-uitvoeringstijd, omdat het mergen altijd lineaire tijd kost.
