## De functie $\varphi_{b}$  
Voor elke $b > 0$, de functie $\varphi_{b}$ is gedefinieerd als:
$\varphi_{b}(x) := \frac{b^{x} - 1}{x}$ 

### eigenschappen
- De functie $\varphi_{b}$ is positief als $b > 1$ en negatief als $0 < b < 1$ 
- Voor $b > 1$ en $n$ niet nul
	$\frac{b^{n+1} - 1}{b^{n} -1} \geq \frac{n+1}{n}$ 
- Voor elke positieve $b \neq 1$, is $\varphi_{b}$ strikt stijgend over zijn domein $(-\infty, 0) \cup (0, \infty)$ 
- Voor elke $b > 0$ het limiet $\psi(b) := \frac{db^{x}}{dx} _{x=0} = \lim_{x\to0}\varphi_{b}(x)$ bestaat, en $f(x) = b^{x}$ is overal afleidbaar met afgeleide bij $x =a$ gegeven door $\frac{d}{dx}[b^{x}] = \psi(b) \cdot b^{x}$ 

## De functie $\psi(b)$ en het getal $e$ 
1. Voor $b > 1$, $\psi(b) > 0$ en $0 < b < 1 , \psi(b) < 0$ 
2. Voor elke $b > 0$ en $r \in \mathbb{R}, \psi(b^{r}) = r\psi(b)$ , bestaat er een waarde $b$ waarvoor $\psi(b) = 1$ 

$e$ is het unieke getal waarvoor 
	$\lim_{h\to0}\frac{e^{h} -1}{h} = 1$ 
Met deze definitie, kunnen we de afgeleide formule bepalen
	$\frac{de^{x}}{dx} = e^{x}$ 

## Natuurlijke logaritmes
$\ln x = \log_{e} x$ 

$\log_{b}x = \frac{\ln x}{\ln b}$

$b^{x} = e^{x \ln b}$ 

$\frac{d}{dx}[b^{x}] = (\ln b)(b^{x})$ 