Dit zijn binaire zoekbomen met een bijkomende __balanceringsvoorwaarde__.
## Balansvoorwaarde voor AVL-bomen
- zij $h(v.l)$ diepte van linkertak van top $v$, $h(v.r)$ diepte van rechtertak van top $v$
- voor elke top $v$, vereiste: $|h(v.l) - h(v.r)| \leq 1$ 

De diepte van een AVL-boom met $n$ toppen is $O(log n)$ 
__Bewijs__
- zij $n_{h}$ = # toppen in kleinste AVL-boom van diepte $h$ 
- speciale gevallen: $n_{0} =1, n_{1}=2$ 
- algemeen: $n_{h} = n_{h-1} + n_{h-2} +1$ 
- hieruit: $n_{h} = F_{h+3} -1$ 
- nu: $F_{h+3} \sim \phi^{h+3} / \sqrt{5}$, met $\phi = (1+\sqrt{5})/2$ 
- m.a.w. # toppen is exponentieel in diepte
- m.a.w. diepte is logaritmisch in # toppen

## bewerkingen op AVL-bomen
### opzoeken
- zoals in gewone binaire zoekboom
- gegarandeerd in $\Theta(\log n)$ 
### toevoegen 
- toevoegen kan balans verstoren 
- -> balans te herstellen
- -> boom herstructureren via rotatie
![[Pasted image 20240530201045.png]]
Soms lost één rotatie het probleem niet op dan moeten we een dubbele rotatie doen.
![[Pasted image 20240530201146.png]]