## Limiet
$$
\lim_{x\to a}{f(x)} = b 
$$
in python:
_vb_
$$
\lim_{x\to -1} \frac{x² -1}{x +1}
$$
```python
f = lambda x: (x*x - 1)/(x+1)
[f"{f(-1-1/h):.5f}, {f(-1+1/h):.5f}" for i in range(1, 1000, 100)]
```
## Continuiteit
=> We zeggen dat een functie $f$ continu is in het punt $a \in Dom(f)$ als $\lim_{x\to a} f$ gelijk is aan de functie waarde in voor alle $x$
## afgeleide
=> De functie $f$ is afleidbaar in $a$ als 
$$
\lim_{h \to 0} \frac{f(a+h) \cdot f(a)}{h}
$$
bestaat. In dit geval wordt deze limiet genoteerd als $f'(a)$ en noemen we deze waarde de __afgeleide__ van $f$ in $a$.

### Relu
$Relu'(x) : \mathbb{R} \to \mathbb{R} : x$
- $0$ als $x  < 0$
- $undefined$ als $x=0$
- $1$ als $x>0$

### Stapfunctie
$stap'(x): \mathbb{R} \to \mathbb{R} : x$
- $undefined$ als $x=0$
- $0$ als $x \neq 0$

### regeltjes
$(g+h)'(a) = g'(a) + h'(a)$
$(g \cdot h)'(a)= g'(a)h(a) + h'(a)g(a)$
$(g/h)'(a) = \frac{g'(a)h(a) - h'(a)g(a)}{h(a)²}$

## Ketting regel
$$
(h \circ g)'(a) = h'(g(a)) \times g'(a)
$$
## de sigmoide 
=> soort van S-vormige kromme
$$
\sigma :\mathbb{R} \to \mathbb{R}: x \to \sigma(x) = \frac{1}{1 + exp(-x)}
$$
### eigenschappen
- Het domein van $\sigma$ is $\mathbb{R}$  en het beeld is $]0,1[$
- Overal afleidbaar met als voorschrift 
$$
\sigma'(x) = \sigma (x) (1-\sigma(x))
$$
- $\sigma(0) = 1/2$
- Soms wordt de sigmoide gedefinieerd als
$$
\sigma(x) = \frac{exp(x)}{1+exp(x)}
$$

## Newton - Raphson
- Start met schatting voor een mogelijk nulpunt
- Daarna interatieve methode
- Stel de x-waarde van de huidige benadering $x_n$
- beschouw de raaklijn aan de functie $f$ in het punt $(x_n, f(x_n))$
- Indien $f'(x_n) \neq 0$, neem snijpunt van raaklijn met de x-as als volgende benadering
