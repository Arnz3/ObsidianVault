Beheer van meerdere processen
__Multiprogramming__
 - beheer meerder processen in een systeem met 1 processor

__Multiprocessing__
- beheer van meerdere processen in systeem met meerdere processoren

__Gedistribueerde verwerking__
- beheer meerdere processen uitgevoerd op aantal verspreide systemen

## Concurrency
- multiprocessor is systeem met 2 of meer CPUs
- dergelijke systemen kunnen meerdere taken gelijktijdig = concurrency
- verhoogt productiviteit, maar ook uitdagingen
	- communicatie tussen processen
	- delen van en vechten om bronnen.
	- synchronisatie van meerdere procesactiviteiten
	- verdelen processortijd
### gelijktijdige uitvoering
- Toepassing boekt vooruitgang op meer dan 1 taak (schijnbaar) gelijktijdig
### Concurrency in de praktijk
verschillende situaties
- __meerdere toepassing__: dynamisch verdelen van processortijd over aantal actieve toepassingen
- __gestructureerde toepassing__: toepassingen geprogrammeerd als verzameling gelijktijdige processen
- __structuur van OS__: geïmplementeerd als verzameling processen
## Wederzijdse uitsluiting
- soms worden bronnen gedeeld over meerder processen
- code die gebruikt wordt voor het aanspreken van gedeelde bronnen noemen we een __kritieke sectie__
- belangrijk dat op elk moment max 1 proces in kritieke sectie zit
	- nood aan wederzijdse uitsluiting (mutual exclusion)

### bij multiprocessing
- niet alleen processen, maar ook activiteiten binnen 1 proces kunnen parallel worden uitgevoerd
- moeilijkheid ontstaat wanneer processen gemeenschappelijk geheugen aanspreken
### Afdwingen
2 mogelijkheden
- Algoritme van Dekker
- wederzijds uitsluitings algortime van Peterson

Alternatieven:
- via semaforen (Dijkstra) of monitoren

Taak van OS om mutual exclusion te garanderen

## Synchronisatie
=> proces, of resultaat van iets gelijktijdig maken 
- opleggen van een dwingende volgorde aan events

## Bestandssynchronisatie
2 of meer identieke kopieën van bestand
- vroeger vaak manueel (USB-stick)
- Nu: automatisch (netwerk, OneDrive)
### soorten
__Synchronisatie__: inhoud van bron en doelmap gelijkhouden, alle wijzigingen altijd zichtbaar
__Echo__: Synchronisatie enkel in 1 richting
__Contributie__: gelijkaardig aan Echo, maar verwijderde bestanden in bronmap worden niet verwijderd in doelmap

## Deadlocks
### bij processen
=> Twee of meer processen wachten op elkaar, cyclus zit vast
Hoe behandelen
1. Gebruik protocol om deadlock te voorkomen
2. detecteren en daarna herstellen

### Voorwaarden
- Bronnen met wederzijdse uitsluiting (Mutual exclusion)
- Proces zal bron bezet houden en wachten (Hold and wait)
- Er is geen voortijdig ontnemen (No preemption)
- Processen wachten in een kring (Circular wait)
### voorkomen
=> zorgen dat minstens 1 voorwaarde optreedt
- mutual exclusion sws noodzakelijk
- OS beperkt gebruik van gemeenschappelijke bronnen
### vermijden
=> we laten alle voorwaarden toe, maar weigeren aanvragen die tot deadlock kunnen leiden
- omgeving blijft veilig
- moeilijk te implementeren
- hoe aanvraag beoordelen
### signaleren
- processen in BLOCKED toestand, permanent?

opsporen via Resource Allocation Graph (RAG)
- Deadlock = cyclus in RAG
### herstellen
deadlock gevonden?
1. proces stoppen via `KILL`
	- bronnen vrijgeven
2. Doe rollback op proces
	- deel van werk ongedaan maken en bronnen vrijgeven
	- terugkeren naar starttoestand of checkpoint
