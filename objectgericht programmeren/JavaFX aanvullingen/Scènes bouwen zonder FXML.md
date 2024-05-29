Stel dat we een Scene willen aanmaken zonder hiervoor een FXML te gebruiken, kunnen we dit doen door instanties van een klasse te maken en deze als kinderen toe te voegen met `addAll()`, een voorbeeld:

```java
SplitPane splitPane = new SplitPane();
Button knop = new Button("Klik hier");
Label tekst = new Label("voor plezier!");

// Voeg nu de knop en het label toe aan de splitPane
splitPane.addAll(knop, tekst);

Scene scene = new Scene(splitpane);
```

Lettertypes, spatiëring, marges, centrering en achtergrond worden bepaal door een _stylesheet_ in CSS die we aan het paneel hechten:
```java
splitPane.getStylesheets().add("path/to/stylsheet.css");
```

## eventHandlers
We moeten zorgen dat het programma passend reageert op bijvoorbeeld indrukken van een knop. We kunnen dit doen aan de hand van _eventHandlers_.

Hiervoor hebben we een object nodig die de interface `EventHandler<ActionEvent>` implementeert.
De interface bezit slechts 1 methode: 
```java
public void handle(ActionEvent e)
```

__Voorbeeld__
```java
private static class ButtonEventHandler implements EventHandler<ActionEvent>{
	//...
	@Override
	public void handle(ActionEvent event){
		//...
	}
}
```

Opdat JavaFX zou weten welke gebeurtenis er door welk object moet worden verwerkt, moet je de verwerker registreren.
```java
button.setOnAction(new ButtonEventHandler(...))
```

