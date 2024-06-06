In een tabel kunnen we gegevens van allerhande types weergeven (teksten, afbeeldingen, check boxes, ...). Een tabelcomponent kan zodanig ingesteld worden dat de gebruiker de gegevens kan aanpassen.

`TableView<>` moet altijd een typeparameter hebben die aangeeft met welke klasse de getoonde inhoud overeenkomt, een rij stelt steeds een object voor. 

## MVC patroon
JavaFX gebruikt bij tabellen ook het MVC patroon, waarvan `TableView` een view is. Er komt ook en model aan te pas, de `ObservableList` die houdt de view op de hoogte wanneer er iets veranderd in de lijst.

_Opmerking_:
`ObservableList` kan niet weten wanneer iets veranderd aan de objecten binnen in de lijst. 

__Voorbeeld__
```java
public TableView<ZipInfo> tableView; //aangemaakt door FXMLLoader

public void doSearch(){
	ObservableList<ZipInfo> model = FXCollections.observableArrayList();
	for(ZipInfo zipInfo : zipSearcher.find(searchField.getText())){
		model.add(zipInfo);
	}
	tableView.setItems(model);
}
```

### View
Naast `TableView` bestaan er ook andere klassen die een rol spelen bij een tabel. De kolommen van de tabel moeten zelf toegevoegd worden, deze zijn van het type `TableColumn` . De kolommen maken gelukkig zelf cellen aan van het type `TableCell`. 
Beide hebben op hun beurt weer type parameters. 

__Voorbeeld__ (verder op vb hierboven)
```java
public TableColumn<ZipInfo, String> zipColumn;

public TableColumn<ZipInfo, String> nameColumn;
``` 

Je moet bij elke dergelijke kolom wel een factory registreren. Voor het eenvoudige geval waarbij enkel een _getter_ moet worden opgeropen is er de `PropertyValueFactory`. 
```java
zipColumn.setCellValueFactory(new PropertyValueFactory<>("zip"));
nameColumn.setCellValueFactory(new PropertyValueFactory<>("name"));
```
