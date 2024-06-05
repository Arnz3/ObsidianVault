Java heeft met de JDBC-library het heel wat gemakkelijker gemaakt om met een database te verbinden. Om een databaseverbinding te maken heb je wel een _driver_ nodig (`jar`-bestand). Om daarna een verbinding te maken heb je "URL" nodig die er als volgt uitziet: `(protocol):(subprotocol):(locatie)` bijvoorbeeld voor een `sqlite` database: `JDBC:SQLITE:databank.db` 

## Opdrachten
Opdrachten naar de databank sturen gebeurt met een `PreparedStatement`, hierin kan men een query aanmaken, die automatisch beveiligd wordt teen bijvoorbeeld `SQL-injection`. Indien je gewoon een query `opdracht` wil uitvoeren, die niets teruggeeft, doe je dit als volgt:
```java
try(Connection conn = DriverManager.getConnection(url, USER_ID, PASSWD);
   PreparedStatement stmt = conn.prepareStatement(opdracht)) {
		stmt.excuteUpdate();   
   } catch (SQLException err) {
	   // Handel err af
   }
```

Indien we gegevens willen opvragen, moeten we in plaats van `executeUpdate()` de methode `executeQuery()` gebruiken. 
```java
try (Connection conn = DriverManager.getConnection(url);
     PreparedStatement stmt = conn.prepareStatement(opdracht)) {
         ResultSet resultaat = stmt.executeQuery();
         while(resultaat.next()) {
             // Haal nu met resultaat.getInt, getString,
             // get...(kolomNaam) de waarden op.
         }
     } catch (SQLException err) {
         // Handel err af
     }
```

### ResultSet
De methode `executeQuery()` geeft een `ResultSet` terug. Dit heeft een pointer waarmee je het resultaat rij na rij kan aflopen.  
De Interface `ResultSet` biedt verschillende methodes aan om data op te vragen:
```java
boolean getBoolean(String columnName);
double getDouble(String columnName);
int getInt(String columnName);
String getString(String columnName);
Date getDate(String columnName);
Time getTime(String columnName);
...
```

### Parameters
Wanneer we en `WHERE` keyword gebruiken in SQL moeten we dit een parameter meegeven. Dit kan je door 2 strings te concateneren maar dit behandeld niet te speciale gevallen (zoals aanhalingstekens) en is niet veilig tegen SQL injection. Daar voor kunnen we de methode `setXxx()` gebruiken.
```java
public void setXxx (int indexParameter, xxx waardeParameter)
```
Hieronder een voorbeeld.
```java
PreparedStatement stmt = conn.prepareStatemen(
	"SELECT name FROM town WHERE zip = ?"
);
stmt.setString(1, zip)
```