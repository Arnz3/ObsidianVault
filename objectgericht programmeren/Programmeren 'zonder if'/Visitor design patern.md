1. We hebben een 'visitor'-interface met een specifieke visit-methode voor elke klasse in de hiërarchie.
```java 
    public interface Visitor<R> {
      R visitX (X x);
      R visitY (Y y);
      R visitZ (Z z);
    }
```
2. Vervolgens hebben we een 2de interface, met minstens een methode accept die een dergelijke visitor als argument neemt.
```java
public interface Ding {
  //...
  <R> R accept (Visitor<R> visitor);
}
```
	De <R> moet erbij staan aangezien de methode generiek is, maar de klasse niet

3.  Deze 2de interface wordt dan in iedere klasse in de hiërarchie uitgebuit, zodanig dat ze naar de corresponderende visit-methode delegeert.
```java
    public class X extends Ding {
      //...
      public <R> R accept (Visitor<R> visitor) {
        return visitor.visitX(this);
      }
    }
```

	Om de notatie te vereenvoudigen, kan je de klassemethode of toevoegen aan een specifieke visitor. Zo ga ja van ding.accept(new SpecificVisitor()) naar SpecificVisitor.of(ding).
```java
    public static [type] of(Ding ding) {
      return ding.accept(new SpecificVisitor());
    }
```
#### Void

Met het returntype Void kan je aangeven dat de visit-methode niets teruggeeft, Void is dus de generieke versie van void.

Voorbeeld:
```java 
public Void visitDwarf(Dwarf dwarf) {
  System.out.println("Hiho!");
  return null;
}
```
