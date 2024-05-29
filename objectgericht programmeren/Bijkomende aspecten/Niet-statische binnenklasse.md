Een niet-statische binnenklasse kan enkel worden aangemaakt met behulp van een instantie van de Buitenklasse.

Het voordeel hiervan is dat de binnenklasse nu toegang heeft tot alle velden van de buitenklasse (ook private)

```java
public class Buitenklasse{
	...
	public class Binnenklasse{
		...
	}
	...
}
```