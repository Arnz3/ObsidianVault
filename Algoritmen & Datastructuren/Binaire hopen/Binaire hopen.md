De __binaire hoop__ is een specifieke datastructuur die veel gebruikt wordt als voorstelling van het _ADT priorityQueue_. Het is een binaire boom die voldoet aan volgende structuureigenschap en ordeningseigenschap.
## Structuureigenschap
### links-complete binaire boom
Een __links-complete binaire boom__ is een binaire boom waarvan alle niveau's volledig gevuld zijn, behalve het eventueel het laatste, dat van links naar rechts gevuld is.
##### stellingen
Een links-complete binaire boom heeft een __impliciete representatie__ aan de hand van een array

Een links-complete binaire boom met $n$ toppen heeft hoogte $\lfloor log_{2}n  \rfloor$ 

## ordeningseigenschap
### prioriteitsboom
Voor elke top $x$ en zijn ouder $p$: sleutel in $x$ is groter dan sleutel in $p$

## basisbewerkingen
### toevoegen van een element
__Waar toevoegen?__ 
- aanvullen diepste niveau / achteraan in array
__Wat als conflict met ordening?__
- nieuwe sleutel en zijn ouder omwisselen
#### opwaartse percolatie
- bij conflict met ordening
- herhaaldelijk sleutel met ouder omwisselen
- totdat conflict is opgelost
#### complexiteit
- diepte van binaire hoop is $O(log n)$ 
- complexiteit in slechtste geval $O(log n)$ 

### verwijderen kleinste element
__Waar verwijderen?__
- kleinste zit in wortel van boom / vooraan in array
- laatste plaats in boom / array niet meer beschikbaar
__werking__
- verwijder kleinste uit wortel
- plaats laatste element in wortel
- laat neerwaarts percoleren
#### complexiteit
 slechtste geval $O(logn)$ 

## opbouwen in lineaire tijd
het toevoegen en verwijderen is in slechtste geval steeds $O(log n)$ 
We kunnen de hoop opbouwen in lineaire tijd door het gebruik van __Lui toevoegen__

#### lui toevoegen
Bij het toevoegen zullen we niet telkens de ordening herstellen. We zullen __lui toevoegen__, we voegen toe op de laatste plaats in boom/array (toss)
Vooraleer we het kleinste element op vragen of verwijderen herstellen we de ordening aan de hand van __fixheap__

## fixheap
Wanneer beide takken van top $x$ voldoen aan ordeningseigenschap, dan volstaat neerwaartse percolatie van $x$ om deelboom $x$ in orde te brengen

__Recursieve formulering__ 
- doe fixHeap van linkertak
- doe fixHeap van rechtertak
- doe neerwaartse percolatie van wortel
__Achterliggend idee__
- toppen per niveau doorlopen, in omgekeerde volgorde
- hiervoor telkens neerwaartse percolatie doen
- dan zijn beide takken van top $i$ in orde, wanneer top $i$ verwerkt wordt

### complexiteit
fixHeap kost $O(n)$ in het slechtste geval
__bewijs__
- $\forall$ top $i$: kost van neerwaartse percolatie ~ diepte van deelboom met wortel $i$
- totale kost ~ som van dieptes van deelbomen
- er geldt: deze som $\leq n$ 
	- via markeren van bogen
