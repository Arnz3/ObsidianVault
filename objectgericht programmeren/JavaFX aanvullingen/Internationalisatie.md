Met de klasse `ResourceBundle` (gelijkaardig aan `Properties`) kunnen we gemakkelijk vertalingen maken in ons programma.

```java
// Laat het systeem kiezen welke taal te gebruiken
ResourceBundle bundle = ResourceBundle.getBundle("/languages");

// Beslis zelf welke taal te gebruiken
Locale locale = new Locale("nl", "BE");
ResourceBundle bundle = ResourceBundle.getBundle("/languages", locale);
```

Het is ook mogelijk dit in de FXML te steken: door bijvoorbeeld `<Button text="%knopTekst">` te gebruiken en `Parent root = FXMLLoader.load(fxmlFile, ResourceBundle.getBundle("/languages"))`

Het is ook mogelijk om berichten te formatteren. Zo kan een foutmelding bijvoorbeeld zijn `"Kon {0} niet openen omdat {1}"`. Dit bericht kan dan getoond worden met `Message.format()`.