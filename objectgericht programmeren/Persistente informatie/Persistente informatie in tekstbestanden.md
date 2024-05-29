Voor veel toepassingen willen we gegevens kunnen opslaan en deze later terug inlezen, dit noemt men __persistente informatie__. Voorbeelden hiervan zijn configuratiebestanden en foto's. 

Vroeger gebruikte men `File`uit `java.io` om naar bestanden te schrijven, nu is het beter om daarvoor `Path` uit `java.nio.file` te gebruiken

## BufferedReader
1. Je hebt een object nodig van `BufferedReader` nodig om de lijnen van een bestand te lezen. 
2. De methode `readLine` van `BufferedReader` leest telkens een volledige lijn van de invoerstroom en geeft die terug als string. De waarde van `readLine` is `null` aan het einde van de invoerstream. 
3. Na afloop moet je een open bestand steeds sluiten. 
4. Er kan heel wat fout gaan bij het lezen van een bestand. Daarom bevindt het ganse fragment zich binnen een __try-catch__ blok. 
__Voorbeeld__

```java
try{
	double totaal = 0.0;
	BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
	String line = reader.readLine();
	while(line != null){
		totaal += Double.parseDouble(line);
		line = reader.readLine();
	}
	reader.close();
	System.out.println("Som = " + totaal);
} catch(Exception ex){
	// Er is iets mis gegaan
}
```

## PrintWriter
Om lijnen uit te schrijven naar een bestand(of andere uitvoerstroom), gebruik je `PrintWriter`. Je kan een dergelijke `printWriter` aanmaken met één van de volgende constructoren.
```java
public PrintWriter(Writer w);
public PrintWriter(OutputStream out);
```
__Voorbeeld__
```java
PrintWriter writer = new PrintWriter(padnaam);
```

De basismethodes van `PrintWriter` heten `print`en `println` en laten toe om getallen, lettertekens en in principe alle objecten in tekstvorm uit te schrijven.

## try with resources
```java
try (PrintWriter writer = new PrintWriter("bestand.txt")) {
    // ... doe dingen met writer
} catch (IOException ex) {
    // ... vang de Exception op
}
// Writer wordt automatisch gesloten
// als deze de interface AutoClosable implementeert
```

## bestand lezen uit class path
Je kan elke klasse vragen om voor jou een bepaalde bron op te sporen. In de praktijk betekent dit meestal dat de bron wordt gezocht op dezelfde plaats waar ook het .class-bestand van die klasse is gevonden. 

Hier een voorbeeld voor een klasse genaamd `ISOCodes` :
```java
ISOCodes.class.getResourceAsStream("isocodes.txt");
```

