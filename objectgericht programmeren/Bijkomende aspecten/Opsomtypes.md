### Opsomtypes of enumeration types

Als men een klasse heeft waarvan de objecten reeds op compile time bekend zijn, kan men een _enum_ type gebruiken. Bijvoorbeeld als men de windrichtingen wil weergeven, moest men dit vroeger als volgt doen:

```java
// Declareer de richtingen
public static final int NOORD = 0;
public static final int OOST = 1;
public static final int ZUID = 2;
public static final int WEST = 3;

// ...

// Gebruik de richtingen
int richting = ZUID;
```

Dit brengt veel nadelen met zich mee, zo is het bijvoorbeeld mogelijk om eender welk getal aan `richting` toe te kennen. Het maakt het uitprinten van een richting ook minder intuïtief. Richting bevat een getal, dus als je na het vorige voorbeeld `richting` print, zou je `2` terug krijgen, en dat is niet overzichtelijk.

Daarvoor zijn _enum_ types toegevoegd, het vorige voorbeeld zou er dan als volgt uitzien:

```java
// Declareer de richtingen
public enum Windrichting {
    NOORD,
    OOST,
    ZUID,
    WEST
}

// ...

// Gebruik de richtingen
Windrichting richting = Windrichting.ZUID

// ...

// Als we willen weten welke richting we aan het uitgaan zijn.
if (richting == Windrichting.NOORD) {
    // Doe iets
}
```

We kunnen ook een weergavenaam toevoegen aan onze windrichtingen, maar daarvoor moeten we ook tegen `Windrichting` zeggen hoe hij dit moet opslaan:

```java
public enum Windrichting {
    // Declareer de richtingen en geef de weergavenaam mee als argument
    NOORD("Noord"),
    OOST("Oost"),
    ZUID("Zuid"),
    WEST("West"); // ! let op de ;

    // Het veld waarin we de weergavenaam gaan opslaan
    private final String weergavenaam;

    // De constructor
    private Windrichting(String weergavenaam) {
        this.weergavenaam = weergavenaam;
    }

    public String getWeergaveNaam() {
        return this.weergavenaam;
    }
}

// ...

// Gebruik de windrichting
Windrichting richting = Windrichting.ZUID;
System.out.println("De huidige richting is: " + richting.getWeergaveNaam());
```

Dit gaat (als alles goed gaat) `De huidige richting is: Zuid` printen.