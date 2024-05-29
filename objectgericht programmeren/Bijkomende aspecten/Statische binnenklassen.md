Statische binnenklassen worden meestal gebruikt wanneer de objecten van die klasse hoofdzakelijk betekenis hebben in de context van hun buitenklasse, maar niet daarbuiten.
Een typisch voorbeeld hiervan zijn _data transfer objects (DTO's)_ 

```java
public class Buiten{
	...
	public static class Binnen{
		...
	}
	...
}
```

## voorbeeld
DTO's worden vaak gebruikt voor het groeperen van parameters of om meerdere waarden terug te geven uit een functie.

In volgende functie kijken we als twee gebieden overlappen
```java
public class MijnKlasse{
	public boolean overlappen(int rij1, int kolom1, int hoogte1, int breedte1,
							 int rij2, int kolom2, int hoogte2, int breedte2)
}
```

Echter 8 parameters is nogal zwaar op de hand, daarom is een DTO hier een goed alternatief:
```java
public class MijnKlasse{
	public record Gebied(int rij, int kolom, int hoogte, int breedte){
	}
	
	public boolean overlappen(Gebied gebied1, Gebied gebied2){
	}
}
```