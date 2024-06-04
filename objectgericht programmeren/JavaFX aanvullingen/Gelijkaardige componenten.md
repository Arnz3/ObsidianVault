JavaFX laat toe om bij een component een object te registreren als zogenaamde _'user data'_. Op die manier kunnen we gelijkaardige componenten maken met verschillende functionaliteit. 
Dit doe je met `setUserData`:
```java
public void initialize() {
	...
	plus1.setUserData(1);
	plus10.setUserData(10);
	minus1.setUserData(-1);
	minus10.setUserData(-10);
}
```

We kunnen dit dan opvragen in een handler function:

```java
public void doButton(ActionEvent event){
	Button sourceButton = (Button)event.getSource();
	int increment = (Integer)sourceButton.getUserData();
	adjBlzLabel(increment);
}
```

Het retourtype van `getUserObject` is `Object`. We hebben dus een cast nodig naar `Integer` 

## Initialisatie in FXML
je kan de initialisatie van de _user data_ ook in het FXML-bestand opnemen in plaats van in de `initialize` 
```xml
<Button userData="-10" fx:id="minus10" ... text="Min 10" />
<Button userData="-1"  fx:id="minus1"  ... text="Min 1" />
<Button userData="1"   fx:id="plus1"   ... text="Plus 1" />
<Button userData="10"  fx:id="plus10"  ... text="Plus 10" />
```
JavaFX denkt nu echter dat de _user data_ van het type `String` is en moet dus eerst van `Object` naar `String` gecast worden en daarna omgezet naar een `Integer`.

Als je de _user data_ wil initialiseren met het juiste type kan dit op volgende manier.
```xml
<Button fx:id="minus10" ... text="Min 10">
	<userData>
		<Integer fx:value="-10"/>
	</userData>
</Button>
...
```
