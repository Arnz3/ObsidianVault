XML is een manier om geneste data op te slaan, elk beetje data wordt in een "tag" opgeslagen. Hieronder een voorbeeld:
```xml
<universiteit naam="UGent">
    <richting naam="Informatica">
        <jaar weergaveNaam="Eerste" inschrijfjaar="2017-2018">
            <leerling voornaam="Piet" achternaam="Peters" />
            <leerling voornaam="Jan" achternaam="Janssens" />
            ...
        </jaar>
    </richting>
</universiteit>
```

Om hier nu in Java data uit te halen, gebruiken we  `JDOM` als volgt:
```java
Document document = new SAXBuilder().build(padNaarBestand);

// nu vragen we het "root" element op (universiteit)
Element root = document.getRootElement();

// Vraag de naam van de universiteit op
String universiteit = root.getAttribute("naam");

// Vraag alle richtingen op 
ArrayList<Element> richtingen = universiteit.getChildren("richting");
```
