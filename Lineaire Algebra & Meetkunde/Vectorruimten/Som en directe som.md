Een somruimte $\sum_{j=1}^{k}U_{j}$ noemen we een __directe som__ als elk element van $\sum_{j=1}^{k}U_{j}$ op precies één manier te schrijven valt als som van vectoren uit elk van de deelruimten.
Dit wil zeggen dat er voor alle $v \in \sum_{j=1}^{k}U_{j}$ _unieke vectoren_ $u_{1} \in U_{1}, ..., u_{k} \in U_{k}$ bestaan zo dat
$v = u_{1} + u_{2} + ... + u_{k}$ 

we noteren $\bigoplus_{j=1}^{k} U_{j} = U_{1} \oplus U_{2} \oplus ... \oplus U_{k}$ 

#### propositie
Gegeven is een vectorruimte $(\mathbb{R}, V , +)$ 
1. Zij $U_{1}$ en $U_{2}$ deelruimten van $V$. Dan geldt dat $W = U_{1} \oplus U_{2}$ als en slechts als
	- $W = U_{1} + U_{2}$ 
	- $U_{1} \cap U_{2}  = \{0\}$
2. Algemener, zij $U_{1}, U_{2}, ... , U_{k}$ deelruimten van $V$. Dan is 
		$W  = U_{1} \oplus U_{2} \oplus ... \oplus U_{k}$
	als en slechts als
	- $W = U_{1} + U_{2} + ... + U_{k}$
	- voor alle $i = 1,... , k$ geldt dat
			$U_{i} \cap (U_{1} + ... + U_{i-1} + U_{i+1} + ... + U_{k}) = \{0\}$ 

