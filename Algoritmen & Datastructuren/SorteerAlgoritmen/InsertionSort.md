De basisbewerking van het algoritme is het rangschikken van de elementen op de posities 1 t.e.m. $i$ , waarbij $i$ een waarde is tussen 2 en $n$. Men verondersteld dat de elementen voor $i$ reeds gesorteerd zijn, dan wordt het element op positie $i$ tussengevoegd op de juiste plaats. 

## pseudocode

```
INPUT: een rij (a1, ..., an)
OUPUT: de rij in stijgende volgorde
for i from 2 to n do
	bepaal j <= i zodat aj-1 < ai < aj
	voeg ai tussen op pos j, door de elementen aj, ..., ai-1 op te schuiven
```


## complexiteit

_InsertionSort heeft een slechtste-geval-uitvoertijd_  $T_{s}(n) = \Theta(n²)$ _en een beste-geval-uitvoeringstijd van_ $T_{b}(n) = \Theta(n)$. 

In het slechtste geval is het aantal stappen uitgevoerd $n(n-1)/2$. Elke stap komt overeen met een vergelijking en een verwisseling, dus $T_{s}(n) = \Theta(n²)$ 
Als de rij bij het begin van het algoritme reeds gesorteerd is, hoeft men niet te verwisselen en is $T_{b}(n) = \Theta(n)$ .

### gemiddelde uitvoeringstijd

Een __inversie__ van een rij is elk paar $(i,j)$ waarvoor geldt dat $i<j$ maar $a_{i} > a_{j}$ .
De rij (8,5,9,2,6,3) heeft 10 inversies. 
(8,5), (8,2), (8,6), (8,3), (5,2), (5,3), (9,2), (9,6), (9,3), (6,3)

Het verwisselen van 2 adjacente elementen die niet in goede volgorde staan, vermindert het aantal inversies met precies één. 

_Het gemiddelde aantal inversies in een rij van n verschillende getallen is gegeven door $n(n-1)/4$_

Beschouw 2 willekeurige getallen $(x,y)$ in de rij waarvoor $y>x$. Dit paar correspondeert met een inversie in $A$ ofwel $A_{r}$(omgekeerd). Het totale aantal dergelijke paren voor een rij $A$ is gegeven door $n(n-1)/2$. Het aantal inversies is dus de helft hiervan.


_InsertionSort heeft gemiddelde uitvoeringstijd_ $T_{g}(n) = \Theta(n²)$ 

Het aantal inversies is precies gelijk aan het aantal keer dat in het algoritme de opdracht voor het verwisselen van $a_{j}$ en $a_{j-1}$ uitgevoerd wordt. Dus als er $k$ inversies zijn bij de start, dan moeten er $k$ verwisselingen gebeuren. Verder gebeurt enkel nog $\Theta(n)$ werk. Dus de totale tijd komt neer op $\Theta(k + n)$. Met $k$ het aantal inversies. 
Dus uit vorige stelling $T_{g}(n) = \Theta(n²)$.