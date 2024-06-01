Zij $C(n)$ het aantal vergelijking nodig voor het opzoeken van een sleutel in een rij van lengte n met een zoek algoritme gebaseerd op vergelijken. Dan is $C(n) = \Omega(\log{n})$  

De slechts mogelijke uitvoeringstijd van een zoekalgoritme gebaseerd op vergelijkingen is $\Omega(\log n)$ 

Zij $C(n)$ het aantal vergelijkingen nodig om n elementen te sorteren met een sorteeralgoritme gebaseerd op vergelijkingen. Dan is $C(n) = \Omega(n \log n)$ 

__Bewijs__
Men kan voor de vergelijkingen die moeten worden gemaakt in een sorteeralgoritme een beslissingsboom $T$ maken. Aangezien $n$ verschillende elementen op $n!$ verschillende manieren kunnen worden gerangschikt, moet $T$ minsten $n!$ bladeren hebben. Wegens stelling _7.5.3_ heeft een binaire boom met $m$ bladeren minstens een hoogte $\log_{2} m$ dus, 
	$h \geq \log_{2}(n!)$
Wegens Stelling _2.2.8_ is 
	$\log_{2}(n!) = \Omega(n \log{n})$ 
en krijgen we dat
	$C(n) = h \geq \log_{2}(n!) = \Omega(n \log{n})$
Hieruit volgt dat
	$C(n) = \Omega(n \log n)$ 

Hieruit volgt onmiddellijk de stelling

De slechtst mogelijk uitvoeringstijd van een sorteeralgoritme gebaseerd op vergelijkingen is $\Omega(n \log n)$ 