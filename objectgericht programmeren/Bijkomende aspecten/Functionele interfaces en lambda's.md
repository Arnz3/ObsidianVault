Een functionele interface is een interface die maar één functie bevat, bijvoorbeeld:
```java
public interface Naam{
	public String getNaam(Persoon p);
}
```
Nu kunnen we een nieuwe `Naam` aanmaken als volgt:
```java
//Ergens anders is de functie verwerkNaam(Naam n) gedefinieerd
verwerknaam(new Naam(){
	public String getNaam(Persoon p){
		return p.getVoornaam() + " " + p.getAchternaam();
	}
});
```

Merk wel dat `Naam` een interface is en geen klasse, Java gaat nu automatisch veel voor ons doen, we moeten dus niet meer een aparte klasse die `Naam` implementeert aanmaken en die dan aanroepen.

Aangezien `Naam` een functionele interface is en dus maar een functie heeft, kunnen we het nog verder verkorten als volgt:

```java
verwerkNaam(p -> p.getVoornaam() + " " + p.getAchternaam())
```

De compiler gaat hier zelf uitzoeken welk type hij nodig heeft, en de juiste instantie aanmaken.

Een plaats waar dit nuttig is is bijvoorbeeld in `list.sort()` als we op een andere manier gaan sorteren:

```java
// Maak de lijst
ArrayList<Persoon> personen = new ArrayList<>();

// ... Vul de lijst

// Sorteer de lijst met behulp van een statische functie
// in Persoon en een lambda-expressie
personen.sort((p1, p2) -> Persoon.sorteerOpNaam(p1, p2));

// Dit kunnen we *nog* verder verkorten met een method
// reference of methodereferentie
personen.sort(Persoon::sorteerOpNaam);

// Als we bijvoorbeeld op een id willen sorteren, kan de
// Comparable.comparing automatisch hierop sorteren.
personen.sort(Comparable.comparing(Persoon::getId));
```

### Lambda's in de collectiebibliotheek

Java 8 heeft een paar nuttige functies toegevoegd aan de bibliotheek, enkele voorbeelden:

```java
// Maak een lijst
ArrayList<Integer> lijst = new ArrayList<>();

// Verwijder alle getallen kleiner dan 0
list.removeIf(i -> i < 0);

// Print alle getallen uit
list.forEach(System.out::println);

// Tel bij elk getal 1 op
list.replaceAll(i -> i + 1);
```

Deze functies maken het bewerken van lijsten veel korter en overzichtelijker. Er zijn ook gelijkaardige functies voor een Map:

```java
// Maak een nieuw scorebord aan
Map<String, Integer> scorebord = new HashMap<>();

// ... Voeg scores toe

// Print de score van alle deelnemers
scorebord.forEach((naam, score) -> System.out.println(naam + ": " + score));

// We willen de score van een willekeurig persoon opvragen,
// maar als die nog niet op het scorebord staat, geven we
// hem een score van gelijk aan de lengte zijn naam.
String persoon = willekeurigeNaam();
int score = scorebord.computeIfAbsent(persoon, naam -> naam.length);
```