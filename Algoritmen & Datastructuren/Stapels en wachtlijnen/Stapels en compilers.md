Stapels worden extensief gebruikt bij het ontwerpen en implementeren van compilers, zoals het controleren van gebalanceerde symbolen. 

__Voorbeelden__:
- balanceren van haakjes
- conversie infix- naar postfix-uitdrukking
- evaluatie postfix-uitdrukkingen
- oproepen van methodes (callstack)
## controleren van haakjes
### pseudocode
```
INPUT: inputrij met haakjes
OUTPUT: true als goed gebalanceerd, false anders
S <- null
for all x uit inputrui do 
	if x is open haakje then
		S.push(x)
	else if x is gesloten haakje then
		if S == null then 
			return false
		else
			y <- S.pop()
			if x !~ y then
				return false
	else negeer het symbool
 if S != null then 
	 return false
 else
	 return true
 ```
 $T(n) = O(n)$
 
