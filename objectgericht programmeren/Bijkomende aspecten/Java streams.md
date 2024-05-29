We beginnen met een voorbeeld:

```java
// Bereken de som van de faculteiten van de eerste 10 getallen
// als het laatste getal van de faculteit groter is dan 5
int resultaat  = IntStream.range(1,11)
                          .map(i -> faculteit(i))
                          .filter(i -> (i % 10) > 5)
                          .sum();
```

Dit is een voorbeeld van een _stream_, of meer specifiek: _pijplijn_ (cfr. | in UNIX) en bestaat uit drie delen:

- De bron (`IntStream`)
- Mogelijk een paar bewerkingen (`map(), sum()`)
- Het einde, dit is wat er overblijft na de laatste bewerking en wat in `resultaat` opgeslagen zal worden.

Een stream-functie gaat elke keer een nieuwe stream teruggeven, zodat er daarna weer een stream-functie op toegepast kan worden.

Er zijn veel manieren om een stream-bron aan te maken, hier enkele voorbeelden:

```java
lijst.stream()          // Stream van de List lijst
Arrays.stream(array)    // Stream van de Array array
Stream.of(array)        // idem
IntStream.range(i, j)   // Een nieuwe stream van integers van
                        // i (inclusief) tot j (exclusief)
Random.ints()           // Een stream van willekeurige integers
```

De drie belangrijkste bewerkingen van steams zijn:

- Map: voert een bewerking uit op elk element in de stream en slaat dit op op die plaats (`.map(i -> faculteit(i)`)
- Reduce: reduceert de stream naar een ander type (`.sum()`)
- Filter: filtert de elementen uit een stream afhankelijk van een test (`.filter(i -> (i % 10) > 5)`)

Let op! Java maakt onderscheid tussen een stream van Objecten (implementeren de interface `Stream`) en die van primitieve types (implementeren bijvoorbeeld de interface `IntStream`). Met `.mapToObj()` kan je omzetten naar een object-stream.