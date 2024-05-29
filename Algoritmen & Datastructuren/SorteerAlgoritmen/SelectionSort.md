Het grootste element in de rij wordt bepaald en achteraan in de rij geplaatst. Vervolgens het 2 de grootste, etc... . Dit proces wordt herhaalt op steeds kortere deelrijen, totdat de deelrij uiteindelijk maar één element meer bevat. 

## pseudocode

 ```
 INPUT: een rij(a1, ..., an)
 OUTPUT: de rij in stijgende volgorde
 for i from n to 2 do
	 M <- grootste element van deelrij(a1, ai)
	 verwissel M met ai
```

## complexiteit

 _SelectionSort heeft een tijdscomplexiteit $T(n) = \Theta(n²)$ 

Het aantal vergelijkingen is $C(n) = n(n - 1)/2$, want in elke stap van de dubbele for-lus gebeurt een vergelijking. Het aantal verwisselingen is hoogstens $S_{s}(n) = n - 1$ , want die verwissel operatie staat in de buitenste lus. Het kan dat er geen enkele verwissel operatie nodig is, dan $S_{b}(n) = 0$. De totale tijdscomplexiteit is dus $T(n) = \Theta(n²)$
