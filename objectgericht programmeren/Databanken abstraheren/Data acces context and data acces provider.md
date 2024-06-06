Als we in een programme en DAO willen gebruiken, moeten we op één of andere manier een DAO-object zien te bekomen. Aangezien DAO enkel interface gespecificeerd zijn kunnen we niet zomaar __new__ doen. 
Hiervoor gebruiken we een _data acces context_
```java
public interface DataAccesContext extends Autoclosable {
	PersonDAO getPersonDAO();
	ContactDAO getContactDAO();
	ContactTypeDAO getContactTypeDAO();
	void close() throws DataAccesException;
}
```

wil je een DAO dan vraag je dit aan een DAC
```java
try(DataAccesContext dac = ...){
	PersonDAO pdao = dac.getPersonDAO();
	...
}
```

Een data acces context is een abstractie van een databankconnectie. Daarom moeten een DAC na gebruik worden gesloten. 


## Data acces provider
Een DAC is natuurlijk ook een interface dus deze kan je ook niet zomaar opvragen. Daarom vraag je een DAC aan een data acces provider DAP.
```java
public interface DataAccesProvider {
	public DataAccesContext getDataAccesContext() throws DataAccesException;
}
```

Dit alles is ter voordele van abstractie en zodat de gebruiker van de lib niet in aanraking hoeft te komen met de databank. Dit zorgt er ook voor dat alles veel veiliger is. Veel yappin voor fkn 3 interfaces daj nu nog altijd nie kan aanmaken met __new__. En hoe tf daj dan deftig aan je data kan wordt blijkbaar pas uitgelegd in het vollegende hoofdstuk FK ME. 
