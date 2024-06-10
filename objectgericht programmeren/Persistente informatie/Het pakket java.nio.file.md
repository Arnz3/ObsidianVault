`Path` is een interface en geen echte klasse, en heeft dus geen constructor nodig. Nieuwe objecten van het type `Path` moet je aan maken met `Path.of(...)` 

```java
Path path = Path.of("Windows", "Text", "text.dat");
// of
Path path = Path.of("Windows/Text/text.dat");
```

Om dit dan in te lezen in een Bufferedreader gebruiken we `newBufferedReader()`
```java
BufferedReader readers = Files.newBufferedReader(Path.of("Windows", "Text","text.dat"));
```
