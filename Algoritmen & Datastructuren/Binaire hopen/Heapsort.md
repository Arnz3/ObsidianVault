## idee
Binaire hoop gebruiken om $n$ elementen te sorteren als volgt:
1. Voeg elk element toe aan een binaire hoop
2. Verwijder één voor één de elementen door een oproep van $removeMin$
Het resultaat is gesorteerd. Steunend op resultaat van vorige paragraaf, kan dit efficiënter geïmplementeerd worden:
1. Voeg de elementen toe aan de binaire hoop door het oproepen van de toss-bewerking;
2. Roep de bewerking $fixHeap$ op;
3. Doe $n$ oproepen van $removeMin$, hetgeen de elementen in gesorteerde volgorde geeft.

Stappen 1 en 2 van dit algoritme vragen elk lineaire uitvoeringstijd. In stap 3 vereist elke oproep van $removeMin$ $O(logn)$ tijd, zodat $n$ oproepen $O(nlogn)$ tijd vereisen. Dit betekent dat we een sorteeralgoritme met $O(nlogn)$ slechtst mogelijke uitvoeringstijd hebben bekomen. Dit algoritme wordt het __heapsort-algoritme__ genoemd