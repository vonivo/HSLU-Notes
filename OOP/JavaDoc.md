Dokumentationssystem von Java

War soll dokumentiert werden:
- Kundenorientiert Dokumentieren → für die Nutzenden 
- [[Interface|Interfaces]] und deren [[Methode|Methoden]] sind **zwingend** zu dokumentieren
- Öffentliche [[Methode|Methoden]] und [[Klasse|Klassen]] sollten ebenfalls dokumentiert werden

## Best Practices
- Alles dokumentieren was man selbst zum schnelleren Verständnis von Code lesen möchte 
- Kurze prägnante Kommentare
- Erster Satz und Punkt Regel (Kurzbeschreibung)
- Auf HTML Fragmente verzichten

## Beispiel: 
JavaDoc einer [[Klasse]]:
```java
/**
 * Temperatur Class to record the Temperature on earth
 *
 * @author Hannah Schelbert
 * @version 1.2
 */
```

JavaDoc einer [[Methode]]:
```java
/**
 * Creates a new Temperatur Object with the temperature in Celcius
 *
 * @param celcius
 * @return Temperatur Object
 */
```