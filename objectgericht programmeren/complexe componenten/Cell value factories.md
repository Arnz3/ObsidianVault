In veel gevallen kun je `PropertyValueFactory` als cell value factory gebruiken. Dit lukt enkel maar als de waarde overeen komt met een eigenschap van het rij-object. 

Vaak gebruikt men echter records voor de rijen. Je zou denken dat je dit met een lambda kan doen maar dit werkt niet want die geeft het verkeerde type terug. De factory maakt gebruik van een `ObservableValue` zodat veranderingen in de waarde onmiddellijk kunnen worden doorgegeven. 
```java
nameColumn.setCellValueFactory(
	features -> new SimpleStringProperty(features.getValue().name())
);
```

Men kan ook `SimpleObjectProperty<String>` gebruiken hiervoor of voor andere types. 

Deze implementatie voldoet aan de juiste interface, maar niet aan het corresponderende _contract_: wanneer het Record een andere naam krijgt zal deze verandering niet zichtbaar worden in de tabel. 

Wanneer we zelf een klasse maken die `ObservableValue` implementeert kan dit wel. Hiervoor moeten we een _setter_ introduceren die zegt wanneer de waarde veranderd. 
In de praktijk lost men dit op door bij de rij-elementen geen gewone velden te definiëren, maar velden met JavaFX-eigenschappen. 

```java
public class Row {
	private StringProperty name = SimpleStringProperty();

	public StringProperty nameProperty(){
		return name;
	}

	public String getName(){
		return name.get();
	}

	public void setName(String name){
		this.name.set(name)
	}
}
```