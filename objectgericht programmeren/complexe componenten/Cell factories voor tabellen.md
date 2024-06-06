We kunnen op de zelfde manier als de combo box cell factories maken voor onze tabel. 
Echter kunnen we nu wel extra functionaliteit toevoegen zoals onderstaande.

## Dubbelklik
We wensen dat een dialoogvenster verschijnt wanneer we op een rij dubbelklikken. We kunnen dit doen door aan elke kolom van de tabel en cell factory te hechten waarvan de cellen op _mouseEvents_ reageren. 
```java
public class DoubleClickableTableCell<S, T>
		extends TextFieldTableCell<S, T>
		implements EventHandler<MouseEvent> {
		
	private EventHandler<ActionEvent> actionEventHandler;
	
	public DoubleClickableTableCell(EventHandler<ActionEvent> handler) {
		this.actionEventHandler = handler;
		setOnMouseClicked(this);
	}
	
	@Override
	public void handle(MouseEvent t) {
		if ( t .getClickCount() > 1) { // check alst dubbel click is
			ActionEvent ae = new ActionEvent(this, null);
			actionEventHandler.handle(ae);
		}
	}
}
```

De parameter `handler` in de constructor is het object dat dubbelklik moet verwerken.
```java
public void handle(ActionEvent t){
	TableCell tc = (TableCell)t.getSource();
	int rijIndex  = tc.getIndex();
	// doe iets met de rij index
}
```

### RowFactory
Een andere manier is door een `RowFactory`.  We kunnen een implementatie bijna identiek aan `DoubleClickableTableCell` toepassen. Maar om het op een ander manier te doen kunnen we het ook met een _lambda_ doen, zo hoeven we geen nieuwe klasse te schrijven. 
```java
tableView.setRowFactory(table -> {
	TableRow<TimeSlot> row = new TableRow<>();
	row.setOnMouseClicked(
		ev -> {
			if(ev.getClickCount() > 1){
				handle(row.getIndex());
			}	
		}
	);
	return row;
});
```
