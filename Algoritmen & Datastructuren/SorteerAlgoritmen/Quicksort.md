We kiezen en willekeurig element in de rij, de spil. De rest partitioneren we op volgende manier: - L: elementen <= spil
- R: elementen > spil
Vervolgens sorteren we L & R recursief, waardoor de gesorteerde rij bestaat uit, gesorteerde L, spil, gesorteerde R

## pseudocode

```
INPUT: een rij (a0, ..., an)
OUTPUT: de rij in stijgende volgorde
kies spil
paritioneer in L (< spil) en r (> spil)
sorteer L en R (recursief)
```

## complexiteit
#### beste geval
De rij wordt telkens gehalveerd, $T_{b}(n) = 2T_{b}(n/2) + O(n)$ dus $T(n) = O(n logn)$

#### slechtste geval
L of R zijn telkens leeg, $T_{s}(n) = T_{s}(n-1) + O(n)$ dus $T(n) = O(n²)$ 

#### gemiddelde geval
$T_{g}(n) = O(nlogn)$ 

### Belangrijk bij implementatie
- vermijden van slechtste geval
- voor random rij ligt tijd dichtbij gemiddelde
- opletten voor speciale input
	- reeds gesorteerde rijen
	- rijen van gelijke elementen
- keuze van de spil
- hoe precies partitioneren


## Keuze van de spil
#### eerste laatste element uit de rij
problemen bij reeds gesorteerde input

#### middelste element uit de rij
goed voor reeds gesorteerde input

#### mediaan van drie
mediaan van eerste, laatste en middelste element van de rij. Dit is de meest gebruikte strategie, want actief proberen om goede spil te kiezen.


## Partitionering

__Belangrijk aspect__ is geen extra geheugen gebruiken.

#### Basisstrategie
- spil $s$ achteraan plaatsen door verwisseling
- partitioneren zelf (herhaal): 
	- L voorwaarts doorlopen tot $L_{l} > s$
	- R achterwaarts doorlopen tot $R_{l} < s$
	- als $l < r$, dan $L_{l}$ en $R_{l}$ verwisselen, anders lus beëindigen
- spil $s$ verwisselen met eerste element van R

#### Mediaan-van-drie-partitionering
zelfde strategie als basis maar vereenvoudigt, spil op laatste plaats, kleinste op eerste en grootste op laatste.

- L doorlopen , beginnend bij tweede element
- R doorlopen, beginnend bij derde laatste element
