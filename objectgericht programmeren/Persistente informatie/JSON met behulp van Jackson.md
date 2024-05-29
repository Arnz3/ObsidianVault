Naast XML wordt tegenwoordig ook vaak JSON gebruikt om informatie uit te wisselen tussen verschillende programma's.
```json
{
	"version": "2.0.5",
	"sysAdminEmail": "admin.sys@yourcompany.com"
}
```

We maken gebruik van een externe bibliotheek, _Jackson_ genaamd.

We gebruiken Jacksons `ObjectMapper`  om de JSON-string om te zetten naar een object van de klasse `ApplicationConfig`.
```java
public record ApplicationConfig(String version, String sysAdminEmail){}
```

```java
ObjectMapper mapper = new ObjectMapper();
ApplicationConfig appConfig = 
			mapper.readValue(getClass().getResource("appconf.json"),
								ApplicationConfig.class);
```

De methode `readValue` bestaat in verschillende versies, telkens met een ander type voor het eerste argument. In dit voorbeeld is dit een _URL_-object. Het kan ook een `InputStream` zijn, of een `Reader` of een `String`. Het tweede argument is de naam van de klasse die bij de omzetting gebruikt moet worden. Een record-klasse is hier het meest eenvoudig om mee te werken, maar het kan ook een klasse zijn met gepaste getters en setters.

## lijst inlezen
Hieronder wordt een _reader_ aan die lijsten kan inlezen van elementen en daarop `readValue` op roepen. Er zijn ook dergelijke readers voor arrays en maps. 

```java
ObjectMapper mapper = new ObjectMapper();
List<Grade> list = mapper.readerForListOf(Grade.class)
					.readValue(getClass().getResource("grades.json"))
```

## Schrijven
```java
ObjectMapper mapper = new ObjectMapper();
mapper.configure(SerializationFeature.INDENT_OUTPUT, true);
System.out.println(
	mapper.writeValueAsString(listOfGrades)
);
```


