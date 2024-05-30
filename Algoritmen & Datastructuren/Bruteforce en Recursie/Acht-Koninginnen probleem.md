8 koninginnen op schaakbord plaatsen, zo dat geen enkele koningin een andere bedreigt

## idee
- kolom per kolom (of rij per rij) koningin proberen te plaatsen
- wanneer geen mogelijke plaats meer:
	- terugkeren op stappen en andere mogelijkheden proberen (backtracking)


## implementatie
### plaatsen koningin k
```
if k > 8 then
	alle koninginnen geplaatst, oplossing
else
	while niet gelukt and wel nog posities do
		if volgende positie (r, k) veilig then
			plaats koningin k op positie (r,k)
			probeer koningin k + 1 te plaatsen
			if niet gelukt then
				verwijder koningin k van positie (r, k)
```

### genereren van alle oplossingen
```
if k > 8 then
	een nieuwe oplossing
else
	for alle rijen r do
		if volgende positie (r, k) veilig then
			plaats koningin k op positie (r, k)
			probeer koningin k+1 te plaatsen
			verwijder koningin k van positie (r, k)
```
