De inhoud van een eigenschapsbestand kan worden ingeladen als object van het type `Properties`. Aan dit object kan je gemakkelijk de waarde van een bepaalde sleutel opvragen.

__Properties bestand__
```
#myapps.properties

sysadmin.email = sys.admin@mycompany.net
version = 1.0-2
```

__java code__
```java
Properties properties = new Properteis();
properties.load(
	About.class.getResourceAsStream("myapp.properties")
);
version.setText("Versie " + properties.getProperty("version"));
email.setText(properties.getProperty("sysadmin.email"));
```
