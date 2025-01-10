# Definitie
Een verzameling $F$ waarop twee binaire operatoren, $+$ en $.$ gedefinieerd zijn en waartoe zeker 2 constante elementen 0 en 1, behoren is een veld wanneer volgende eigenschappen gelden.

## Eigenschapppen
Stel $a,b,c \in F$

- $F$ is gesloten voor $+$ en $.$ : $a + b \in F$ en $a . b \in F$
- commutatief: $a + b = b + a$ en $a.b = b.a$
- associatief: $(a+b)+c = a+(b+c)$ en $(a.b).c = a.(b.c)$
- distributief: $a.(b+c) = a.b + a.c$
- neutraal element: $a + 0 = a$ en $a.1 = a$
- invers element voor $+$: er bestaat een element $-a \in F$ zodat $a +(-a) = 0$
- invers element voor $\cdot$ : $\forall a \in F$, met $a \neq 0$ bestaat er een element $a{-1}$ zodat $a . a^{-1} = 1$

Voor een willekeurig veld $F$ met $a,b \in F$ geldt
- het element $0$ is het opslorpend element voor de vermenigvuldiging: $a.0 = 0$
- het veld $F$ heeft geen nuldelers: als $a.b =0$ dan geld $a=0$ of $b=0$

# Eindig veld
Een eindig veld is een veld waarvoor de verzameling van elementen eindig is. Het aantal elementen van deze verzameling is de orde van het veld.

Er bestaat een veld van de orde $q$ als en slechts als $q$ de macht van een priemgetal $p$ is
$$
p \text{ is } (q = p^{h}, \text{ met } h \in \mathbb{N}_{0})
$$

Twee velden van de orde $q$ met $q = p^{h}$ zijn isomorf

Een veld van de orde $q$ noemen we een Galois veld van de orde $q$, $GF(q)$

## Het eindig veld $\mathbb{Z}_{p}$
De verzamemling $\mathbb{Z}_{m}$, met $m \in \mathbb{N}_{0}$, stelt de verzameling voor met als elementen de eerste $m$ natuurlijke getallen
$$
\mathbb{Z}_{m} = \{ 0,1, \dots, m-1\}
$$
$\mathbb{Z}_{m}$ is dus een eindige verzameling met $m$ elementen

## Modulo
Stel $a,b \in \mathbb{Z}$. Dan is $a$ congruent met $b \pmod m$ als en slechts als de deling van $a$ en $b$ door $m$ dezelfde rest oplevert.
$$
a \equiv b \pmod m, \text{ met } a \pmod m =  \text{ de positieve rest na deling door } m
$$

### Eigenschappen
Stel $a \equiv a' \pmod m$ en $b \equiv b' \pmod m$, dan geldt
- $a + b \equiv a' + b' \pmod m$
- $a . b \equiv a' . b' \pmod m$

Stel $a,b \in \mathbb{Z}_{m}$. In $\mathbb{Z}_{m}$ worden de bewerkingen $+$ en $.$ als volgt gedefinieerd
- $a + b \equiv a + b \pmod m$
- $a . b \equiv a . b \pmod m$


$\mathbb{Z}_{p},+,\cdot$ is een veld als en slechts als $p$ een priemgetal is.
