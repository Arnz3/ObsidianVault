In veel gevallen kunnen we een meervoudige selectie vervangen door een array.

```java
public String werkdagNaamFout(int dagnummer) {
    if(dagnummer == 0) {
        return "Maandag";
    } else if(dagnummer == 1) {
        return "Dinsdag";
    } else if(dagnummer == 2) {
        return "Woensdag";
    } else if(dagnummer == 3) {
        return "Donderdag";
    } else if(dagnummer == 4) {
        return "Vrijdag";
    }
    return "WEEKEND!"
}

// Kan vereenvoudigd worden tot

private String[] werkdagen = [
        "Maandag",
        "Dinsdag",
        "Woensdag",
        "Donderdag",
        "Vrijdag"
    ];

public String werkdagNaam(int dagnummer) {
    if (dagnummer > 4) {
        return "WEEKEND!"
    }
    return werkdagen[dagnummer];
}
```

Je hebt nog wel een `if` nodig om te kijken of de dagnummer wel een juiste waarde heeft, maar dit maakt het veel gemakkelijker om dingen aan te passen.

Het is ook mogelijk om op deze manier functie-aanroepen te doen afhankelijk van een input:

```java
public interface DingDoener {
    public void doeIets();
}

// ...

HashMap<String, DingDoener> acties = new HashMap<>();
acties.put("vooruit", new DingDoener(){
    public void doeIets() {
        System.out.println("Ik ga vooruit");
    }
});
// of
acties.put("achteruit", () ->
                System.out.println("Ik ga achteruit")
            );

String actienaam = vooruitOfAchteruit();
acties.get(actienaam).doeIets();
```