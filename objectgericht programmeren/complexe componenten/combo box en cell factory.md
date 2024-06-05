Een Combo Box is een component dat de gebruiker toelaat uit een _dropdown_ een optie te kiezen. Dit component heeft in JavaFX 3 belangrijke eigenschappen: 
1. `items` (de waarden waaruit men kan kiezen)
2. `value` (de geselecteerde waarde)
3. `editable` (of de gebruiker de waarde nog mag aanpassen)

Let op, als de waarde `editable` verandert, wordt de waarde van `value` ook leeg gemaakt. Je kan dus beter eerst `editable` instellen. 

## cell factories
Als we onze cellen er anders willen laten uit zien dan gewoon een saai Label, kunnen we een zogenaamde `Cell Factorie` gebruiken. 

Een cell factory moet voldoen aan de interface `CallBack<ListView<T>, ListCell<T>>`
```java
public interface Callback<P,R> {
	R call (P param);
}
```

Ze wordt op verschillende plaatsen gebruikt om een klasse aan te duiden met een methode die 1 parameter neemt van het type P en returneerwaarde heeft van het type R. 

Gelukkig kunnen we dit veréénvoudigen met een simpele lambda:
```java
comboBox.setCellFactory(list -> new ComboCell());
```

Hieronder een voorbeeld van een custom `ListCell<T>`
```java
public class ComboCell extends ListCell<Persoon> {
	public ComboCell() {}

	@Override
	protected void updateItem(Persoon persoon, boolean empty) {
		// Belangrijk die hier super() wordt aangeropen
		super.updateItem(persoon, empty);

		// We geven de Persoon-instantie weer als zijn/haar naam
	    setText(persoon.getVoornaam() + " " + persoon.getAchternaam());
	
	    // We kunnen de tekstkleur nog aanpassen
	    // afhankelijk van het geslacht.
	    setTextFill(persoon.isVrouw ? Color.BLUE : Color.YELLOW);
	}
}
```

