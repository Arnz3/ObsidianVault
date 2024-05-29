__Boom__ is een samenhangende graaf die geen cykels bevat.
__gewortelde boom__ is een gerichte boom die een speciale top bevat $r$, de wortel van $T$ genoemd, zodanig dat voor elke top $v$ een $r-v$ pad bestaat.

Een top zonder kinderen is een __blad__

een __k-aire boom__ is een gewortelde boom waarin elke top ten hoogste k kinderen heeft

Een __binaire boom__ is een 2-aire boom waarin 1 kind het linkerkind is en de andere het rechterkind

Een __complete binaire__ boom heeft elke top ofwel 2 of geen kinderen

## Stellingen
Zij $G$ een graaf met $n$ toppen, dan zijn volgende uitspraken equivalent
- $G$ is een boom
- $G$ heeft geen cykels en bevat $n-1$ bogen
- $G$ is samenhangend en bevat $n-1$ bogen
- $G$ is samenhangend en elke boog is een brug
- Elke 2 toppen van $G$ zijn door precies 1 pad verbonden
- $G$ bevat geen cykels en voor elke nieuwe boog $e$ bevat $G + e$ precies 1 cykel

Zij $T$ een binaire boom van hoogte $h$ met $n$ toppen
- $T$ bevat ten hoogste $2^{i}$ toppen van niveau $i (i \geq 0)$ 
- $n \leq 2^{h+1} -1$ 
- $h \geq \lceil log_{2}(\frac{n+1}{2}) \rceil$  

Voor een binaire boom $T$ van hoogte $h$ met $b$ bladeren is $h \geq log_{2}b$ 

Voor een ternaire boom $T$ van hoogte $h$ met $b$ bladeren is  $h \geq log_{3}b$


## Recursieve verwerking van bomen

#### Aantal toppen in binaire boom
```
INPUT: binaire boom T met wortel w
OUTPUT: aantal toppen G(T) in T
if w = null then
	return 0
else
	return 1 + G(w.links) + G(w.rechts)
```

#### Hoogte binaire boom
```
INPUT: binaire boom T met wortel w
OUPUT: hoogte H(T) van T
if w = null then
	return -1
else
	return 1+max(H(w.links), H(r.rechts))
```

#### preorde doorlopen
```
INPUT: binaire boom T met wortel w
behandel component w
if w.links != null then
	doorloop w.links in preorde
if w.rechts != null then
	doorloop w.rechts in preorde
```

#### postorde doorlopen
```
INPUT: binaire boom T met wortel w
if w.links != null then
	doorloop w.links in postorde
if w.rechts != null then
	doorloop w.rechts in postorde
behandel comoponent w
```

#### inorde doolopen
```
INPUT: binaire boom T met wortel w
if w.links != null then
	doorloop w.links in inorde
behandel component w
if w.rechts != null then
	doorloop w.rechts in inorde
```


Zij $T$ een boom met $n$ toppen. Dan gebeurt zowel doorlopen in preorde, postorde en inorde in tijd $O(n)$ 