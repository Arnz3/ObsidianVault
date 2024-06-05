Dergelijke eigenschappen worden ook _gebonden_ eigenschappen genoemd. Elke element heeft een aantal properties. Een pane heeft bijvoorbeeld en `HeightProperty` of een slider bijvoorbeeld een `valueProperty` . 

![[Pasted image 20240605112216.png]]

De interface `Observable` kennen we reeds, de interface `ObservableValue<T>` voegt daar nog enkele methodes aan toe: 
```java
public interface ObservableValue<T> extends Observable{
	T getValue();
	void addListener(ChangeListener<T> cl);
	void removeListener(ChangeListener<T> cl);
}
```

Een `ObservableValue` kan je beschouwen als een model die slechts 1 waarde bijhoudt. 

Je kan ook een ander type luisteraar hechten namelijk een `ChangeListener`. Deze zal steeds op de hoogte gebracht worden van alle veranderingen in de waarde van het model.
```java
public interface ChangeListener<T>{
	void changed(ObservableValue<T> source, T oldVal, T newVal);
}
```

## eigenschappen verbinden
Het is niet altijd nodig om een MVC-patroon te gebruiken, voor kleine dingen. Hiervoor kunnen we soms _eigenschappen verbinden_. 
```java
foto.heightProperty().bind(slider.valueProperty());
```

