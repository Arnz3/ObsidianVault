## Lengte
Zij $(\mathbb{R}, V, + , \langle \cdot, \cdot \rangle)$ een inproductruimte. Dan definiëren we, voor elke vector $v\in V$, de __lengte__ van $v$ (of de __norm__), $\|v\|$ genoteerd, als $\| v \| = \sqrt{\langle v, v \rangle}$. Wanneer voor een vector $v$ geldt dat $\|v\| = 1$ , dan noemen we $v$ __genormeerd__ of een __eenheidsvector__. 

## eigenschappen
Zij $V$ een inproductruimte met bijhorende norm
	$\|.\| : V \to \mathbb{R} : v \mapsto \|v\| = \sqrt{\langle v, v \rangle}$ 
Dan geldt
1. voor alle $\lambda \in \mathbb{R}$ en $v \in V$ dat $\|\lambda v\| = |\lambda| . \|v\|$;
2. voor alle $v \in V : \|v\| \geq 0$ en $(\|v\| = 0 \Leftrightarrow v =0)$ 

## Afstand
Zij $V$ een inproductruimte. Voor willekeurige vectoren $v,w \in V$ definiëren we $d(v,w) = \|v - w \|$ als de __afstand__ tussen $v$ en $w$ 

Zij $V$ een inproductruimte
1. voor alle vectoren $v,w \in V$ geldt dat
		$| \langle v, w \rangle | \leq \|v\| . \|w\|$ 
2. Deze ongelijkheid is een gelijkheid als en slechts als de vectoren $v$ en $w$ lineair afhankelijk zijn.

## Hoek
Zij $V$ een inproductruimte en zij $v \neq 0$ en $w \neq 0$ elementen van $V$. De __hoek__ tussen $v$ en $w$ is de unieke hoek $\theta \in [0, \pi]$ waarvoor
$\cos \theta = \frac{\langle v, w \rangle}{\|v\| \cdot \|w\|}$ 

Willekeurige vectoren $v$ en $w$ noemen we __orthogonaal__ of __loodrecht__ op elkaar als $\langle v, w \rangle = 0$; we schrijven hiervoor $v \bot w$.

## eigenschappen
Zij $V$ een inproductruimte met bijhorende norm $\|\cdot\|$ . Dan geldt voor alle $v,w \in V$ dat
$\| v + w\| \leq \|v\| + \|w\|$ (de driehoeksongelijkheid)

Een eindig dimensionale inproductruimte noemen we een __Euclidische ruimte__.