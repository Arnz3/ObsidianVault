## Definitie
=> Een reële functie in meerdere veranderlijken is een afbeedling die met tupels in haar in domein een tupel associeert.
$$
f : \mathbb{R}^m \to \mathbb{R}^n : (x_1,\dots,x_m) \to (f(x_1,\dots,x_m), \dots, f_n(x_1, \dots, x_m))
$$
## Partiële afgeleiden
=> grote verschil: meerdere richtingen mogelijk, niet enkel volgens de x-as
- kies een richting evenwijdig met 1 van de assen (_bvb evenwijdig met x-as_)
- Dus $y$ constant, beschouw $(a,b)$, en limiet waarbij $h \to 0$
$$
\lim_{h\to0} \frac{f(a+h, b) - f(a,b)}{h}
$$
- Als deze limiet bestaat, noemen we dit de __partiële afgeleide__ naar $x$ van $f$ in punt $(a,b)$
$$
\frac{\partial f}{\partial x} (a,b) = \lim_{h\to 0}\frac{f(a+h, b) - f(a,b)}{h}
$$
op voorwaarde dat deze limiet bestaat
### eigenschap
- Stel dat $f$ een reële functie is van $\mathbb{R}^n$ naar $\mathbb{R}$: de partiële afgeleide van $f$ naar $x_i$ kan berekend worden als de afgeleide van een functie $g(x_i)$ die hetzelfde functie voorschrift heeft als $f$ maar waarbij alle andere variabelen geinterpreteerd worden als contstanten

## De gradiënt
=> Wanneer men alle partiële afgeleiden verzamelt in een kolom vector, dan noemen we deze kolomvector de __gradiënt__ van de functie in dat punt

### eigenschap
Als $f:\mathbb{R}^n \to \mathbb{R}$ een functie is zodat de gradiënt van $f$ bestaat, dan wijst de gradiënt in elk punt de richting $g$ aan waarin de fucntie $f$ het sterkst stijgt. Hoe groter deze stijging, hoe groter de norm van de gradiënt

### Belang van gradiënt 
- _minimum_: is waar gradiënt nul is
- ook maximum of zadelpunt

## Gradient descent
=> zoekt in elke stap de richting van de sterkste daling en zet zeer kleine stapjes in die richting

- Er is een functie gegeven waarvan we veronderstellen dat de gradiënt overal bestaat $\nabla f$
- We starten op $x_0 \in \mathbb{R}^n$ en verbeteren de positie iteratief
- update:
$$
x_{n+1} = x_n - \alpha \nabla f(x_n)
$$
- $\alpha$ is de stapgrootte of de learning rate

## Kettingregel in meerdere verandelijke
=> om te berekenen wat de afgeleide is van $f$ naar $t$, bekijk je elk pad van $t$ naar $f$ en je vermenigvuldigt alle (partiële afgeleiden) langs dit pad. Tenslotte tel je al deze producten op.

// TODO ADD FOTO

__Kettingregel:__
$$
\frac{df}{dt} = \frac{\partial f}{\partial{x}} \frac{dx}{dt}
+ \frac{\partial f}{\partial y} \frac{dy}{dt}
$$

