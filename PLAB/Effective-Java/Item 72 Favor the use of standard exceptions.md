Wenn [[Exceptionhandling|Exceptions]] wiederverwendet werden, erspart dies einerseits Programmieraufwand und bietet folgende Vorteile:
- **Macht die API einfach zu erlernen**, da die Benutzer die Fehlermeldungen schon kennen
- **Macht die API lesbarer,** da sie nicht mit unbekannten Fehlermeldungen gespickt ist
- **Weniger Speicher intensiv** und weniger Zeit für Classloading

## Standard-Exceptions

| Exception | Wann wird sie benutzt |
| ---- | ---- |
| `IllegalArgumentException` | Für "nicht-null" [[Parameter]] welche ungültig sind. |
| `IllegalStateException` | Wenn der State des Objekts ungültig für einen Methoden Aufruf ist. |
| `NullPointerException` | [[Parameter]]wert ist `null` wo ein "nicht-null" [[Parameter]] gefordert ist. |
| `IndexOutOfBoundsException` | Der [[Parameter\|Indexparameter]] ist ausserhalb des zulässigen Bereiches |
| `ConcurrentModificationException` | Gleichzeitige Modifikation eines Objekts wurde bemerkt, obwohl dies verboten ist. |
| `UnsupportedOperationException` | Das Objekt unterstütz diese [[Methode]] nicht. |
Es gibt den Streitfall zwischen einer `IllegalStateException` und der `IllegalArgumentException`. 
Beispiel:
Es gibt eine [[Methode]], welche eine Anzahl Karten auf von einem Stapel in die Hand des Benutzers gibt, basierend auf der Handgrösse.
Nun kann es sein, dass zu wenig Karten im Stapel verblieben sind. Jetzt könnte einerseits der Stapel in einem illegalen Zustand sein oder der Parameter könnte illegal sein.

In diesem Fall wirft man einen `IllegalStateException`, wenn keine Argumentwert funktioniert hätte, ansonsten eine `IllegalArgumentException`.