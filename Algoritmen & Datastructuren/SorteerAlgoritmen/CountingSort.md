Dit is niet op vergelijken gebaseerd, maar om specifieke kennis omtrent de input.

Het kan worden gebruikt om een rij $(a_{1}, ..., a_{n})$ te sorteren waarbij de sleutels $a_{i}$ gehele getallen zijn uit het interval $[0,k]$, voor een niet te grote waarde van $k$.
#### hoe?
- tellen van frequentie van elke sleutel
- Hieruit berekenen hoeveel elementen kleiner of gelijk zijn aan $i$
- Dit zijn de eindposities van de sleutels +1

## pseudocode

```
INPUT: rij (a1, ..., an) met alle ai in [0,k]
OUTPUT: gesorteerde rij (b1, ..., bn)
for j from 0 to max do
      c[j] = 0
   for i from 1 to n do
      c[a[i]] = c[a[i]] + 1
   for j from 1 to max do
      c[j] = c[j] + c[j-1]
   for i from n to 1 do
      b[c[a[i]]] = a[i]
      c[a[i]] = c[a[i]] - 1
```

## complexiteit

Elke lus in het algoritme is ofwel $\Theta(n)$ ofwel $\Theta(k)$. De uitvoeringstijd van het algoritme is dus $T(n) = \Theta(n + k)$. Wanneer $k <= n$  of meer algemeen, wanneer $k$ een functie van $n$ is waarvoor $k = \Theta(n)$, dan wordt $k$ verwaarloosbaar tegenover $n$, dus $T(n) = \Theta(n)$

