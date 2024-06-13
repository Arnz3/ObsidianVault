## Limieten en bewerkingen
Stel $x_{k} \to x$ en $y_{k} \to y$ in $\mathbb{R}$ dan,
1. $x_{k} + y_{k} \to x + y$
2. $x_{k} - y_{k} \to x - y$
3. $x_{k}y_{k} \to xy$
4. Als $y \neq 0$, $\frac{x_{k}}{y_{k}} \to \frac{x}{y}$
5. Als $x > 0$, dan geldt voor elk positief getal $n$ , $\sqrt[n]{x_{k}} \to \sqrt[n]{x}$ 

## meetkundige reeksen
Een reeks $\sum_{i=0}^{\infty} a_{i}$ is een **meetkundige reeks** met **ratio** $r$ als alle termen niet 0 zijn en $\frac{a_{i}+1}{a_{i}} = r$       voor $i = 0,1,\dots$ 

### convergeren en divergeren van MR
Als $\sum_{i=0}^{\infty} a_{i}$ een meetkundige reeks is met ratio $r$ dan geldt:
- Als $|r| \ge 1$ , divergeert de reeks
- Als $|r| < 1$, convergeert de reeks, en $\sum_{i=0}^{\infty}a_{i} = \frac{a_{0}}{1- r}$ 

## Sandwich theorie
Stel $\{a_{k}\}$, $\{b_{k}\}$ en $\{c_{k}\}$ zijn reële rijen zodat:
1. uiteindelijk $a_{k} \le c_{k} \le b_{k}$
2. $\{a_{k}\}$ en $\{b_{k}\}$ beiden convergeren naar hetzelfde limiet  $\lim a_{k} = L = \lim b_{k}$ 
Dan      $c_{k} \to L$ 

## Alternerende reeksen
Stel een reeks $\sum_{i=0}^{\infty} a_{i}$ van termen die geen nul zijn voldoet aan
- voor $i=0,1,\dots$         $-1 < \frac{a_{i+1}}{a_{i}} < 0$
- $|a_{i}| \to 0$
Dan convergeert de reeks