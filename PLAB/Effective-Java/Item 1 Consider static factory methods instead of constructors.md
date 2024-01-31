Eine Instanz einer [[Klasse]] kann auch über eine `static factory Method` erstellt werden.
**Beispiel**
```java
public static Boolean valueOf(boolean b) {
    return b ? Boolean.TRUE : Boolean.FALSE;
}
```

## Vorteile
- Static-Factory-[[Methode|Methoden]] haben im Gegensatz zu [[Konstruktor|Konstruktoren]] einen Namen, welche das den Client lesbarer macht. Zudem können auch dieselbe Parametersignatur mit einem anderen Methodennamen verwendet werden.
- Static-Factory-[[Methode|Methoden]] müssen kein neues Objekt erstellen. (Erlaubt Caching) -> ermöglicht Instanzkontrolle
- Können einen beliebigen Subtypen zurückgeben und so die Implementation austauschen.([[Interface]]-Based-Framework, hält API klein)
- Die [[Klasse]] des zurückgegebenen Objekts kann von Aufruf zu Aufruf unterschiedlich sein. -> Grosse Flexibilität (z. B. `EnumSet` mit den Implementation `RegularEnumSet` und `JumboEnumSet`)
- Die [[Klasse]] welche zurückgegeben wird, muss nicht zwingend existieren, wenn die Factory-[[Methode]] geschrieben wird (Service-Provider)

## Nachteile
- Klassen ohne `public` oder `protected` [[Konstruktor]] kann nicht [[Vererbung|vererbt]] werden.
- Factory-Methoden sind für den Benutzer schwierig zu finden.


## Namenskonvention
| Name | Bedeutung |
| ---- | ---- |
| from | Typkonversion. Nimmt ein Objekt entegen und wandelt es um<br>`Date d = Date.from(instant)` |
| of | Aggregationsmethode. Nimmt mehrere Objekte und erstellt daraus eines<br>`Set<Rank> faceCards = EnumSet.Of(JACK, QUEEN, KING)` |
| valueOf | Ausführlicherer Version von `of` und `from`<br>`BigInteger prime = BigInteger.valueOf(Integer.MAX_VALUE);` |
| instance oder getInstance | Gibt eine Instanz zurück welche durch ihre [[Parameter]] beschrieben werden.<br>`StackWalker luke = StackWalker.getInstance(options);` |
| create oder newInstance | Wie `instance` mit dem Unterschied dass immer ein neues Objekt erzeugt wird.<br>`Object newArray = Array.newInstance(classObject, arrayLen);` |
| get' Type' | Wie `getInstance`, wird in Factory-Methoden verwendet, die in einer anderen [[Klasse]] sind.<br>`FileStore fs = Files.getFileStore(path)` |
| new'Type' | Wie `newInstance`, wird in Factory-Methoden verwendet, die in einer anderen [[Klasse]] sind.<br>`BufferedReader br = Files.newBufferedReader(path);` |
| 'type' | Alternative zu `get'Type'` oder `new'Type'`<br>`List<Complaint> litany = Collections.list(legacyLitany);` |
