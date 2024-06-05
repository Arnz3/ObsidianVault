Wanneer één prepared statement herhaaldelijk moet worden uitgevoerd, maar telkens met andere argumenten dan kunnen we gebruik maken van _Batch-bewerkingen_. Alle opdrachten worden verzameld met `addBatch()` en dan in één enkele lading doorgestuurd met `executeBatch()`.

```java
try (PreparedStatement stat = conn.prepareStatement(
	"UPDATE prefs SET checked = ? WHERE name = ?"
)) {
	for (Preference pref : prefs) {
		stat.setBoolean(1, pref.checked());
		stat.setString(2, pref.name());
		stat.addBatch();
	}
	stat .executeBatch();
} catch (SQLException ex) {
...
}
``` 