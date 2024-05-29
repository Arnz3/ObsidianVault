## Definities
Als A een $(m \times n)$-matrix is, dan ontstaat er een $(n \times m)$-matrix door de rijen van $A$ als kolommen naast elkaar te schrijven, met andere woorden door te spiegelen rond de hoofddiagonaal. Deze $(n \times m)$-matrix noemen we de __getransponeerde matrix__.

### eigenschappen
1. Een vierkante matrix $A$ waarvoor $A^{T} = A$ noemt men een __symmetrische matrix__.
2. Een vierkante matrix $A$ waarvoor $A^{T} = -A$ noemt men een __scheefsymmetrische matrix__
3. Een vierkante matrix $A$ is een diagonaal matrix als enkel op de diagonaal elementen verschillend van nul staan.

Veronderstel dat $A,B,C \in \mathbb{R}^{m \times n}$ en $\lambda, \mu \in \mathbb{R}$. Dan:
1. $(A+B)+C = A+(B+C)$ 
2. $A+O = A = O +A$ 
3. $A + (-A) = O$ 
4. $A+B = B+A$ 
5. $\lambda (A+B) = \lambda A + \lambda B$ 
6. $(\lambda + \mu)A = \lambda A + \mu A$
7. $\lambda (\mu A) = (\lambda \mu)A$ 
8. $1A=A$ 

1. $(A^{T})^{T} = A$ 
2. $(A + B)^{T} = A^{T} + B^{T}$ 
3. $(\lambda A)^{T} = \lambda A^{T}$ 


Het __spoor__ Tr($A$) van een vierkante ($n \times n$)-matrix $A$ is de som van de elementen op de hoofddiagonaal van $A$, m.a.w. Tr($A$) $= \sum_{i=1}^{n}(A)_{ii}$    

Tr($A \cdot B$) $=$ Tr($B \cdot A$) 