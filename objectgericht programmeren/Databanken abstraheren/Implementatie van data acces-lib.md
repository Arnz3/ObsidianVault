Alle voorgaande interfaces worden nu geimplementeerd door klassen `JDBCDataAccesProvider` , enz... De user zou enkel gebruik maken van de interfaces en ziet niet dat de klasse JDBC... bestaat. Dit is zodat men makkelijk kan veranderen van database zonder dat bijvoorbeeld front-end code moet worden aangepast. Of als men overgaat van een test database naar een production database. 

