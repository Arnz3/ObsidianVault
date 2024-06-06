Data acces objects zijn objecten waarin de data wordt opgeslagen.
Met elke DAO laten we een interface overeen komen om te beslissen welke bewerkingen er mogelijk zijn voor dit object.

```java
public interface PersonDAO{
	int createPerson(String name, String firstName)
											 throws DataAccesException;
	void updateperson(int id, String name, String firstName)
											 throws DataAccesException;
}
```

