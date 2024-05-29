## lineaire (on)afhankelijkheid

We noemen $S$ __lineair afhankelijk__ of __niet vrij__ als er een $v \in S$ bestaat die kan geschreven worden als een lineaire combinatie van andere elementen van $S$.
Anders noemen we deelverzameling __lineair onafhankelijk__ of __vrij__
## Basis dimensie en coördinaten
#### voortbrengendheid 
Voor een gegeven vectorruimte $(\mathbb{R}, V , +)$ noemen we een deelverzameling $D$ van $V$ __voortbrengend__ als $vct(D) = V$.
#### basis
In een vectorruimte $(\mathbb{R}, V , +)$ is een deelverzameling $\beta$ een __basis__ (van $V$) als $\beta$ voortbrengend en vrij is.

#### Lemma van Steinitz
Zij $(\mathbb{R}, V , +)$ een vectorruimte. Dan geldt:
1. als er een voortbrengend deel bestaat voor $V$ met $m$ elementen, dan is elke deelverzameling van $V$ met meer dan $m$ elementen lineair afhankelijk
2. als er in $V$ een vrij deel bestaat met $n$ elementen, dan is elke deelverzameling van $V$ met minder dan $n$ elementen niet voortbrengend voor $V$. 

_Anders:_
Als er in een vectorruimte $(\mathbb{R}, V , +)$ een voortbrengend deel is voor $V$ met $m$ elementen en een vrije deelverzameling met $n$ elementen, dan is $n \leq m$;

Als $(\mathbb{R}, V , +)$ een vectorruimte is die een basis heeft met $n$ vectoren, dan heeft elke andere basis van $V$ ook $n$ vectoren.

#### dimensie
Als $V$ een eindige basis heeft noemt men het aantal elementen van die basis de __dimensie__ van $V$.

Veronderstel dat $(\mathbb{R}, V , +)$ een vectorruimte is van dimensie $n$. Dan geldt:
1. elke vrije verzameling van $V$ kan uitgebreid worden tot een basis van $V$
2. elke eindige voortbrengende verzameling van $V$ kan (door het schrappen van vectoren) gereduceerd worden tot een basis van $V$.

Zij een eindigdimensionale vectorruimte en $U$ een deelruimte van $V$. Dan geldt:
1. $U$ is eindig voortgebracht en $dim U \leq dim V$ 
2. $dim U = dim V \Leftrightarrow U = V$ 

### coördinaatafbeelding
Zij $(\mathbb{R}, V , +)$ een vectorruimte en veronderstel dat $\beta = \{e_{1}, ..., e_{n}\}$ een basis is van $V$. Dan kan elke vector $v$ op een _unieke_ manier als lineaire combinatie van de basisvectoren uitgedrukt worden. Er ontstaat derhalve een bijectieve afbeelding
$co_{\beta} : V \to \mathbb{R}^{n} : v \mapsto co_{\beta}(v)$ 
die $v$ afbeeldt op het stel coëfficiënten dat correspondeert met $v$ ten opzichte van de basis $\beta$ Deze afbeelding noemen we de __coördinaatafbeelding bepaald door__ $\beta$ 

### directe som
Als de vectorruimte $V$ eindigdimensionaal is, dan geldt voor willekeurige deelruimten $U$ en $W$ van $V$ dat 
$dim(U + W) + dim(U \cap W) = dim U + dim W$ 

In een vectorruimte $(\mathbb{R}, V , +)$ is een deelruimte $W$ een __complementaire deelruimte__ van de deelruimte $U$ als $V = U \oplus W$ 

Als de vectorruimte $(\mathbb{R}, V , +)$ eindigdimensionaal is, dan heeft elke deelruimte van $V$ een complementaire deelruimte.





