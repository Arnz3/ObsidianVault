Zij $L: V \to V$ een lineaire transformatie van de reële vectorruimte $V$. Het __spectrum__ van $L$ is de verzameling van de eigenwaarden van $L$ en is dus een deelverzameling van $\mathbb{R}$. We noteren $Spec(L)$ voor het spectrum van $L$.

## eigenruimten
De __algebraïsche mulitpliciteit__ van een eigenwaarde $\lambda$ van een lineaire transformatie $L$ van een eindigdimensionale vectorruimte is de multipliciteit van $\lambda$ als nulpunt van de karakteristieke veelterm $\varphi_{L}(X)$. We noteren $m(\lambda)$ voor deze algebraïsche multipliciteit.

Zij $L: V \to V$ een lineaire transformatie en zij $\lambda \in Spec(L)$. Dan is de verzameling $\{v \in V | L(v) = \lambda v\}$ een deelruimte van $V$, die we de __eigenruimte__ van de eigenwaarde $\lambda$ noemen. We noteren $E_{\lambda}$ voor de eigenruimte van de eigen waarde $\lambda$. Als $E_{\lambda}$ eindigdimensionaal is noemen we de $dim_{\mathbb{R}}E_{\lambda}$ de __meetkundige multipliciteit__ van de eigenwaarde $\lambda.  We noteren $d(\lambda)$ voor deze meetkundige multipliciteit.

### eigenschappen
Veronderstel dat $L: V \to V$ een lineaire transformatie is van de eindigdimensionale vectorruimte $V$, met spectrum $Spec(L) = \{\lambda_{1}, ... , \lambda_{k}\}.$ Dan geldt, voor elke eigenwaarde $\lambda_{i}$ 
	1. $m(\lambda_{i}) \geq 1$ 
	2. $d(\lambda_{i}) \geq 1$ 
	3. $d(\lambda_{i}) \leq m(\lambda_{i})$ 
