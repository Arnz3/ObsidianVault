Veel dingen kunnen opgeslagen worden in een zogenaamde "boom-structuur", hierbij hebben alle elementen nul of meer "kinderen", die op hun beurt dan ook weer kinderen kunnen hebben. In JavaFX is er een component dat zo'n structuren weergeeft, namelijk de `TreeView<T>`, hieronder een voorbeeld:

```java
// Eerst maken we een boomstructuur, wetende dat Persoon en
// .toString() heeft die de naam van de persoon weergeeft.
// valerie, inguar en dorus zijn drie instanties van Persoon
TreeItem<Persoon> root = new TreeItem<Persoon>(valerie);
root.getChildren().addAll(
  new TreeItem<Persoon>(inguar),
  new TreeItem<Persoon>(dorus)
);

TreeView<Persoon> treeview = new TreeView<Persoon>(root);

// ... gebruik nu de treeview
```
