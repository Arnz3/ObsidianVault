## bewerkingen
De __som__ van 2 vectoren $v$ en $w$ van $\mathbb{R}^{n}$ wordt gedefinieerd als:
$\begin{bmatrix} v_{1} \\\ v_{2} \\\ \vdots \\\ v_{n} \end{bmatrix} + \begin{bmatrix} w_{1} \\\ w_{2} \\\ \vdots \\\ w_{n} \end{bmatrix} = \begin{bmatrix} v_{1} + w_{1} \\\ v_{2} + w_{2} \\\ \vdots \\\ v_{n} + w_{n} \end{bmatrix}$

Het scalair product van een reëel getal $\alpha$ en een vector $v$ wordt als volgt gedefinieerd:
$\alpha \begin{bmatrix} v_{1} \\\ v_{2} \\\ \vdots \\\ v_{n} \end{bmatrix} = \begin{bmatrix} \alpha v_{1} \\\ \alpha v_{2} \\\ \vdots \\\ \alpha v_{n} \end{bmatrix}$
## Linearie combinaties
Een lineaire combinatie van $m$ vectoren $v_{1}$ tem $v_{m}$ is een som van de vorm
$\alpha_{1}v_{1} + \alpha_{2}v_{2} + \dots + \alpha_{m}v_{m}$  
met $\alpha_{1} \dots \alpha_{m}$ reële getallen.

De verzameling van alle lineaire combinaties van vectoren $v_{1}$ tem $v_{m}$ wordt hun omhulsel genoemd
$span\{v_{1}, v_{2}, \dots, v_{m}\} =$ omhulsel van $\{v_{1}, v_{2}, \dots, v_{m}\}$
## Lineaire onafhankelijkheid
Een verzameling vectoren $v_{1}, v_{2}, \dots, v_{m}$ is __Lineair onafhankelijk__ als en slechts als de enige manier om de nulvector te bekomen erin bestaat om een lineaire combinatie te nemen waarin alle coëfficiënten gelijk zijn aan nul.
$\alpha_{1}v_{1} + \alpha_{2}v_{2} + \dots + \alpha_{m}v_{m} = 0 \iff \alpha_{1}=\alpha_{2}=\dots=\alpha_{m}=0$

## Lineaire deelruimte
Een lineaire deelruimte $V$ van $\mathbb{R}^{n}$ is een verzameling vectoren zodanig dat elke lineaire combinatie van 2 vectoren uit $V$ opnieuw tot $V$ behoort
$v \in V$ en $w \in V \Rightarrow \alpha v + \beta w \in V$       $\forall \alpha , \beta$   

### basis
Een basis voor een lineaire deelruimte $V$ bestaat ui teen verzameling vectoren $v_{1}$ tem $v_{m}$ van $V$ die
- lineair onafhankelijk zijn en
- elke vector uit $V$ kan geschreven worden als een lineaire combinatie van $v_{1}$ tem $v_{m}$
### eigenschap
Als $v_{1}$ tem $v_{m}$ een basis is voor $V$, dan kan elke vector $v$ op een unieke manier geschreven worden als combinatie van $v_{1}$ tem $v_{m}$
- dit zijn de coordinaten tov deze basis
- aantal elementen in een basis is de dimensie
## Lengte van vector
$\left\lVert \begin{bmatrix} v_{1} \\\ v_{2} \\\ \vdots \\\ v_{n} \end{bmatrix} \right\rVert = \sqrt{v_{1}^{2} + v_{2}^{2} + \dots + v_{n}^{2}}$ 

## Inwendig product
$v \cdot w = v_{1}w_{1} + v_{2}w_{2} + \dots + v_{n}w_{n}$
of
$v \cdot w = || v || \cdot || w || \cdot \cos{\theta}$ 

### eigenschappen
- Het inwendig product is commutatief: $v \cdot w = w \cdot v$        $\forall v, w$
- Het inwendig product is lineair in de tweede component
	$u \cdot (\alpha v + \beta w) = \alpha (u \cdot v) + \beta (u \cdot w)$ 
Het inwendig product is niet associatief

## Projectie op een vector
De loodrechte projectie van $b$ op $a$ wordt weergegeven door de vector
$p \cdot a$ 
$p = \frac{a \cdot b}{a \cdot a}$ 
