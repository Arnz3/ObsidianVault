## Tussenliggende waarde stelling
Stel $f$ is continu over het gesloten interval $[a,b]$ en $C$ is een waarde tussen $f(a)$ en $f(b)$. Dan bestaat er minstens één punt $t \in [a,b]$ met $f(t) = C$.

## Monotone functies
Stel $S \subset \mathbb{R}$ is een deelverzameling van het domein van $f$. We zeggen dat $f$
- **strikt stijgend** is over $S$ als voor punten $x,y \in S$, $x < y$ garandeert $f(x) < f(y)$
- **strikt dalend** is over $S$ als voor punten $x,y \in S$ , $x < y$ garandeert $f(x) > f(y)$
$f$ is **strikt monotoon** als het één van bovenstaande eigenschappen bevat.

### eigenschappen
Als $f$ strikt monotoon is over $S \in \mathbb{R}$, voor een waarde $C$ , dan kan de vergelijking $f(x) = C$ geen 2 verschillende oplossingen hebben die tot $S$ behoren.


## Inverse Functies
Stel $f(x)$ is continu en strikt stijgend over het gesloten interval $[a,b]$, dan kan de inverse functie $g = f^{-1}$ gedefinieerd over $[A,B]$, met $A = f(a)$ en $B = f(b)$, door $y = g(x) (x \in [A,B]) \Leftrightarrow y \in [a,b]$ en $f(y) = x$ 
Onder deze omstandigheden is $f^{-1}$ is continu en strikt stijgend over $[A,B]$.
*Analoog voor strikt dalende functie.* 

### Inverse van goniometrische functies
Voor $x \in [1,-1]$ , de **inverse sinus** (**arcsinus**) of x is gedefinieerd door
$\theta = arcsin x \Leftrightarrow - \frac{\pi}{2} \le \theta \le \frac{\pi}{2}$ en  $sin \theta = x$

*Opm: arcsin is strikt stijgend en continu over het interval [-1, 1]*

Voor $x \in [1,-1]$ , de **inverse cosinus** (**arccosinus**) of x is gedefinieerd door
$\theta = arccos x \Leftrightarrow 0 \le \theta \le \pi$ en  $cos \theta = x$

*Opm: arccos is strikt monotoon over het interval [-1, 1]*

Voor elke $x \in \mathbb{R}$ , **arctangens** is gedefinieerd door
$\theta = arctan x \Leftrightarrow x = tan \theta$ en $-\frac{\pi}{2} < \theta < \frac{\pi}{2}$
