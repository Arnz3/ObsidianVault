## Notatie
### gesloten vorm
$a_{j} = j$,       $j= 1,3,5$     --> foute notatie
$a_{j} = 2j + 1$,     $j = 0,1,2$ --> correct

Ook wel
	$\{2j+1\}_{j=0}^{\infty}$
Deze notatie noemt *gesloten vorm* , bepaal de waarde van elk element aan de hand van de index

### recursieve formules
Bij een recursieve formule wordt een element voorgesteld aan de hand van zijn vorige element.

**voorbeeld**
Een spaarboek met jaarlijks 5% intrest
$b_{m} = (1.05)b_{m-1}$

Wel niet simpel om de honderdste term te berekenen. Hiervoor kunnen we gebruik maken van het sommatie teken. Stel de recursieve definitie:
$S_{0} = 1$
$S_{n+1} = Sn+ \frac{1}{2^{n+1}}$ ,    $n= 0,1, \dots$

We kunnen dit ook schrijven als 
$\sum_{i=0}^{\infty} \frac{1}{2^{i}}$

Dit worden ook wel reeksen genoemd dit is de som van alle elementen in een rij. 
In feite hebben we te maken met 2 rijen. De eerste een oneindige lijst met de termen die worden opgeteld. De tweede met de *partieel sommen* $S_{n}$. 
