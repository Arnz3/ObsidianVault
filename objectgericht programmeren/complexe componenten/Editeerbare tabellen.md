Om een `TableView` aanpasbaar te maken, moet je haar _editable_-eigenschap instellen
```java
tableView.setEditable(true);
```
Ook de afzonderlijke kolommen hebben een _editable_-eigenschap.

Het grote werk gebeurt echter door de tabelcellen. Een standaardtabelcel is _niet_ editeerbaar. Daarom kiezen we voor een ander type cel. We moeten weer gebruik maken van JavaFX-eigenschapppen, anders is de data niet persistent en zal deze verdwijnen bij het opnieuw opbouwen van de cel. 

```java
marksColumn.setCellValueFactory(new PropertyValueFactory<>("marks"));
marksColumn.setCellFactory(
	column -> new TextFieldTableCell<>(new IntegerStringConverter())
);
marksColumn.setEditable(true);
```
Als parameter moet een converter worden meegeven. Dit kan bijvoorbeeld ook een `IntegerStringConverter()` zijn. 

## De edit-commit gebeurtenis
Je kan een tabel ook editeerbaar maken zonder JavaFX-eigenschappen. Dit doe je door zogenaamde cell _edit_-gebeurtenissen op te vangen. We vangen de `setOnEditCommit` event op.
```java
kolom.setOnEditCommit(evt -> {
  evt.getRowValue().setValue(evt.getNewValue());
}
```
