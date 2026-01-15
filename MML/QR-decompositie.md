-> maakt gebruik van de Gram-Schmidt procedure

De vectoren $q_i$ vormen een orthonormale basis voor de ruimte opgespannen door vectoren $a_j$, deze kunnen geschreven worden een als lineaire combinatie met vectoren $q_i$, en coordinaten de inwendige producten 
$$
a_j = (q_1 \cdot a_j)q_1 + (q_2 \cdot a_j)q_2 + \dots + (q_j \cdot a_j)q_j
$$
in matrix vorm
- rechterlid: lineaire combinatie van vectoren $q_i$
- een matrix construeren met de $q_i$ als kolommen, dan is het een matrix vectorproduct
$$
\begin{bmatrix}
\vert & \vert & & \vert \\\
a_1 & a_2 & \dots & a_m \\\
\vert & \vert & & \vert 
\end{bmatrix}
=
\begin{bmatrix}
\vert & \vert & & \vert \\\
q_1 & q_2 & \dots & q_m \\\
\vert & \vert & & \vert 
\end{bmatrix}
\begin{bmatrix}
q_1 \cdot a_1 & q_1 \cdot a_2 & q_1 \cdot a_3 & \dots & q_1 \cdot a_m \\\
0 & q_2 \cdot a_2 & q_2 \cdot a_3 & \dots & q_2 \cdot a_m \\\
0 & 0 & q_3 \cdot a_3 & \dots & q_3 \cdot a_m \\\
\vdots & \vdots & \vdots &\vdots &\vdots & \\\
0 & 0 & 0 & \dots & q_m \cdot a_m 
\end{bmatrix}
$$
De laatste matrix $R$ is steed een bovendriehoeksmatrix

### eigenschap
Als $A$ een matrix is met lineair onafhankelijke kolommen, dan kan $A$ steeds geschreven worden als het product van een matrix $Q$ met orthonormale kolommen en een bovendriehoeksmatrix $R$
$$
A_{n \times m } = Q_{n \times m} R_{m \times m}
$$
## lineaire stelsels en QR
Als de coëfficiënten matrix $A$ van het stelsel
$$ 
Ax = b
$$
onafhankelijke kolommen heeft, dan kunnen we $A$ schrijven als $QR$, zodat het stelsel geschreven wordt als 
$$
QRx = b
$$
als we beide leden vermenigvuldigen met $Q^\intercal$ en gebruik maken van $Q^\intercal Q = I$ vinden we dat
$$
Rx = Q^\intercal b
$$
Omdat $R$ een bovendriehoeksmatrix is kunnen we dit eenvoudig oplossen met behulp van achterwaartse substitutie

### strijdige stelsels
-> Als het stelsel strijdig is vinden we opnieuw dezelfde benaderende oplossing
$$ 
x = (A^\intercal A)^{-1} A^\intercal b
$$

