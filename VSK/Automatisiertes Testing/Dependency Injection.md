Oft stellen Entwickler nach der Implementation fest, dass eine Klasse schlecht mithilfe von [[Unit Tests]] getestet werden kann.
- Oft wird der Test einfach weggelassen
- Der Test wird zum [[Integrationtests mit JUnit|Integationtest]]

Oft liegt dies daran, dass die [[VSK/Modularisierung/Kopplung|Kopplung]] der zu testenden Klasse zu hoch ist.
Damit ist die Ursache: **schlechtes Design**.

Die Lösung für viele solcher Probleme ist **Dependency Injection**.

## Beispiel
**Schlecht**
```java
public final class PersonPersistor {
	private final StringPersistorFile persistor = new StringPersistorImpl();
}
```
Dies ist in der Realisierung sehr einfach, erzeugt aber:
- hohe Kopplung von `PersonPersistor` und `StringPersistorImpl`
- Typen und Implementation sind fest verdrahtet
- Wie testen man nun `PersonPersistor` als Unit-Test?

Wenn `PersonPersistor` getestet wird, wird implizit auch `StringPersistorImpl` getestet was wir vermeiden wollen.

**Besser**
```java
public final class PersonPersistor {
	private final StringPersistor persistor;

	public PersonPersistor() {
		this.persistor = new StringPersistorImpl();
	}

	PersonPersistor(StringPersistor persistor) {
		this.persistor = persistor
	}
	
}
```
Durch Dependecy-Injection können wird den `StringPersistor` nun von aussen mitgben.
Wir **entkoppeln** die **Erzeugung** der Depency von der benutzenden Klasse.

**Änderungen**
1. Nutze das Interface `StringPersistor`, um [[Kopplung]] zu reduzieren.
	1. Dependency Inversion -> Separation of Concerns.
2. Erstelle im Default-Konstruktor eine neue Instanz von `StringPersistorImpl`
3. Erstelle package-private Konstruktor, welcher `StringPersisotr` entgegennimmt.

Durch die package-private Methode kann nun der `PersonPersistor`-Unittest ein [[Testdouble]] mitgeben und die Selektivität des Tests extrem verbessert, aus dem [[Integrationtests]] wird nun wieder ein Unit-Test.


