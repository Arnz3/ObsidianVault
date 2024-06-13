## Accumulatie punt
Een punt $x_{0} \in \mathbb{R}$ is een **accumulatie punt** van de verzameling $X \subset \mathbb{R}$ als het limiet van de rij in $X \setminus \{x_{0}\}$ 

Stel $f$ is een functie , $y  \in \mathbb{R}$ en $x_{0}$ is een accumulatie punt van $dom(f)$ . We zeggen dat $f(x)$ convergeert naar $y$ als $x$ nadert naar $x_{0}$, en schrijven $y = \displaystyle \lim_{x \to x_{0}} f(x)$ 
Als elke rij $\{x_{k}\}$ in $dom(f) \setminus \{x_{0}\}$ die convergeert naar $x_{0}$   $x_{k} \to x_{0}$ 
voldoet aan $f(x_{k}) \to y$

### eigenschap
Als een functie $f$ continu is over een open interval dan geldt, $\displaystyle \lim_{x \to x_{0}} f(x) = f(x_{0})$ voor elk punt $x_{0}$ in dat interval

## Bewerkingen met limieten van functies
Stel $f$ en $g$ zijn functies, $a$ is een accumulatie punt van $dom(f) \cap dom(g)$ en, 
$\displaystyle \lim_{x \to a} f(x) = L_{f}$, $\displaystyle \lim_{x \to a} g(x) = L_{g}$ 
Dan 
1. $\lim_{x \to a} (f(x) \pm g(x)) = L_{f} \pm L_{g}$ ;
2. $\lim_{x \to a} f(x)g(x) = L_{f}L_{g}$ ;
3. $\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{L_{f}}{L_{g}}$, gegeven $L_{g} \neq 0$ ; 
4. $\lim_{x \to a} \sqrt[n]{f(x)} = \sqrt[n]{L_{f}}$, gegeven $L_{f} > 0$

## Tussenliggende waarde stelling voor functies
Set $f$, $g$ en $h$ zijn functies en $x_{0}$ is een accumulatie punt van een verzameling $D$ die het domein van $h$ bevat bij $x = a$, en waar $f$ en $g$ gedefinieerd zijn. Dan Stel
1. $f(x) \le h(x) \le g(x)$ voor alle $x \in D$
2. $\lim_{x \to a} f(x) = \lim_{x \to a} g(x) = L$
Dan geldt ook  $L = \lim_{x \to a} h(x)$. 

## Linker en rechter limiet
De eenzijdige limieten van een functie $f$ zijn:
1. **rechterlimiet**  $L_{+} = \lim_{x \to a^{+}} f(x)$ als $f(x_{k}) \to L_{+}$ voor elke rij $x_{k} \to a$, $x_{k} \neq a$ met $x_{k} > a$ voor alle k
2. **linkerlimiet** $L_{-} = \lim_{x \to a^{-}} f(x)$ als $f(x_{k}) \to L_{-}$ voor elke rij $x_{k} \to a$, $x_{k} \neq a$ met   $x_{k} < a$ voor alle k

### lemma
$\lim_{\theta \to 0} \frac{\sin \theta}{\theta} = 1$ **!! met $\theta$ in radialen !!** 
