Veronderstel dat $A \in \mathbb{R}^{m \times n}$. Een matrix $B$ wordt een __links inverse__ van $A$ genoemd als $B \cdot A = \mathbb{I}_{n}$. Een matrix $B$ wordt een __rechts inverse__ van $A$ genoemd als $A \cdot B = \mathbb{I}_{m}$.

Als een vierkante matrix $A$ een links inverse $B$ en een rechts inverse $C$ heeft, dan geldt dat $B = C$.
_Bewijs_
$B = B \cdot \mathbb{I}_{n}  = B \cdot (A \cdot C) = (B \cdot A) \cdot C = \mathbb{I}_{n} \cdot C = C$ 

Als een matrix __niet-inverteerbaar__ is noemen we die __singulier__ 

#### eigenschap 
Als $A$ en $B$ inverteerbare matrices zijn, dan is ook hun product $A \cdot B$ inverteerbaar en bovendien geldt dat
$(A \cdot B)^{-1} = B^{-1} \cdot A^{-1}$ 