Eine Class-based API wird über $1\dots n$ Interfaces und Klassen realisiert:
- Diese sind typischerweise in einem Package bzw. Modul abgeschlossen.
- Vollständige und saubere Dokumentation (JavaDoc)

>[!error]
>Klassen und Interfaces, welche als formale Parameter oder Return genutzt werdne, werden automatisch Teil der API. Sie verhalten sich gleich wie mitgelieferte Klassen.


>[!Info]
>In der [[Schichtenbildung]] entsteht häuffig ein API-Layer, nämmlich den Service-Layer.

Wichtig ist, dass zwischen den Schichte die Abhängigkeiten über eigene Value-Objects oder DTOs geborchen werden, ansosten existieret eine Kopllung zwischen APIs.

## Best Practices
- Möglichst kurze, einfache Parameterlisten
	- Overloads zur Vereinfachung
- Für Rückgabetypen wenn möglich immer Interfaces nutzen.
- Ab drei Parameter ein Builder-Pattern verwenden.
- API-Stil an die Bedürfnisse/Sprache/Situation anpassen
	- Usage First - API aus der Perspektive des Nutzenden schreiben.
	- [[Test First]] hilft hier extrem.
- Eventuell Fluent-API verwenden.


## Beispiel
```java
public interface StudentService {
	Student getById(long id);
	List<Student> findByLastName(String lastName);
	List<Student> getAll();
	Student create(Student student);
	boolean update(long id, Student student);
	boolean delete(long id);
}
```
- Beispiel 1: `Student getById(long id)`
	- Wenn die ID der «PrimaryKey» ist, und dieser somit vorliegt, muss die Methode den Studenten (eigentlich) finden!
	- null (oder eine Exception) ist im Fehlerfall absolut legitim!
	- Auf keinen Fall Optional verwenden!

- Beispiel 2: `List<Student> findByLastName(String lastName)`
	- Hier wiederum sind «keine Daten» ein absoluter Normalfall.
	- Eine leere Liste (empty-list) ist die richtige Wahl.
	- Auf keinen Fall null oder eine Exception!