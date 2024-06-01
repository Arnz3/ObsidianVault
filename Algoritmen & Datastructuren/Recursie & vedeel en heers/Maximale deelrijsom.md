bepaal deelrij $a_{i}, ... , a_{j}$ waarvoor deelrijsom $a_{i} + ... + a_{j}$ maximaal is.

## brute force algortimen
```
INPUT: rij van n getallen(a0, ..., an-1)
OUTPUT: waarde van maximale deelrijsom
m <- 0 
for i from 0 to n-1 do
	for j from i to n-1 do
		s <- 0
		for k from i to j do
			s <- s + ak
		if s > m then 
			 m -> s
return m
```
__Complexiteit:__ $\Theta(n³)$ 

```
INPUT: rij van n getallen(a0, ..., an-1)
OUTPUT: waarde van maximale deelrijsom
m <- 0 
for i from 0 to n-1 do
	s <- 0
	for j from i to n-1 do
		s <- s + aj
		if s > m then
			m <- s
return m
```
__Complexiteit:__ $\Theta(n²)$ 

## lineair algoritme
``` 
INPUT: rij van n getallen(a0, ..., an-1)
OUTPUT: waarde van maximale deelrijsom
m <- 0 
s <- 0
for j from 0 to n-1 do
	 s <- s + aj
	 if s > m then
		 m <- s
	else if s < 0 then
		s <- 0
return m
```
__Complexiteit:__ $\Theta(n)$ 

Dit algoritme steunt op enkele eigenschappen:
- Wanneer een deelrij met $0 \leq i \leq j \leq n-1$, een negatieve som heeft, dan kan de maximale deelrij niet van de vorm $(a_{i}, ..., a_{j}, ..., a_{k})$, met $0 \leq i \leq j < k \leq n-1$ zijn.
- Voor willekeurige $i \leq 0$ als $a_{i}, ... , a_{j}$ de eerste deelrij is waarvoor de som negatief wordt, dan is voor elke $i \leq p \leq j$ en elke $q \geq p$, de deelrij $a_{p}, ... , a_{q}$ ofwel geen maximale deelrij, ofwel een reeds gezien maximale deelrij