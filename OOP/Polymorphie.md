Fähigkeiten der Polymorphie:
- Methoden verhalten sich abhängig vom Parametertyp unterschiedlich
- Objekte von unterschiedlicher Typen verhalten isch bei gleicher Behandlung anders
- Gleicher [[Klasse]] kann für unterschiedliche Typen parameterisiert werden

# Überladen von [[Methode|Methoden]]
- Eine [[Klasse]] kann mehrere [[Methode|Methoden]] mit dem gleichen Namen haben solange sich die [[Parameter]] unterscheiden
- So kann man die gleiche Funktionalitäten für unterschiedliche Typen haben

## Best Practices
- Zu ähnliche [[Datentyp|Datentypen]] sollten vermieden werden 
	- z.B. int und long
- Möglichst klar unterscheidbare, eindeutige Signaturen wählen
	- Unterschiedlicher Parameteranzahl
	- Eindeutig, nicht vertauschbare Typenreihenfolge
	- Nicht zu viele [[Parameter]]
## Beispiel 
Die [[Methode]] max hat einen anderen Return wenn der Typ des [[Parameter]] float ist. Die float max [[Methode]] kann auch eine andere Implementierung als die int max [[Methode]]. 
```java
public int max(int a, int b) {...}
public float max(float a, float b){...}
```

# Überladen von [[Konstruktor|Konstruktoren]]
- Funktioniert fast identisch zum Überladen von Methoden

- Der Aufruf eines überladenen Konstruktors aus einem anderem [[Konstruktor]] (derselben [[Klasse]]) erfolgt mit dem Schlüsselwort `this`

- Die Implementation des Konstruktors wir in dem [[Konstruktor]] mit den meisten [[Parameter|Parametern]] gemacht.
	- Die anderen Konstruktoren rufen diesen [[Konstruktor]] mit `this()` auf
	- So vermeidet man redundante Implementationen

## Beispiel
Der [[Konstruktor]] `Person(final int id)` ruft in seiner Implementation den [[Konstruktor]] `Person(final int id, final String name)` auf mit them Schlüsselwort `this`

```java
public Person(final int id, final String name) {  
	...  
}  
public Person(final int id) {  
	this(id, "unbekannt");  
}
```

# Überschreiben von Methoden
Das Überschreiben Methoden wird im Rahmen von [[Interface|Interfaces]] und [[Vererbung]] gebraucht. 

Eine [[Methode]] kann in einer Unterklasse überschrieben werden mit exakt der selben Signatur, abe reiner spezifischen Implementation
- Das funktioniert nur wenn in der Oberklasse die [[Methode]] nicht als `final` markiert wurde

Eine Unterklasse kann per `super.methode(...)` auf die Implementation der Oberklasse zugreifen
- Sofern diese sichtbar ist

Interfaces und Abstrakte Klassen erzwingen das Überschreiben

Das Überschrieben wird mit der Annotation `@Override` gekennzeichnet

[[Konstruktor|Konstruktoren]] können nicht überschrieben werden!

## Beispiel
Die [[toString]] [[Methode]] wird von jedem Objekt geerbt von der Oberklasse Object. Diese sollte wenn möglich mit einer sinnvollen Spezialisierung überschrieben werden. 
```java
@Override
public String toString() {
	return "Temperature is " + this.temperatureCelcius + " C" 

}

```

# [[Subtyping und Casting]]
Sie [[Subtyping und Casting]]

# Parametrisierte Klassen (Generics)
Generics erlauben uns konkrete Klassen zu schreiben deren exakt verwendete Type parametrisiert werden können.
- Auf Deutsch: wir geben an welche Art von Objekten die [[Klasse]] verwenden soll
- Beispiel eine Datenspeicher für verschiedene Temperaturen, kann dann auch für Kreise un Rechtecke verwendet werden man muss einfach angegeben ob man jetzt Temperaturen, Kreise oder Rechtecke speicher möchte
### Beispiel

#### Implementierung
Bei der Implementierung repräsentiert T irgendein Objekt (so als Platzhalter)
```java
public final class StoreGeneric<T> {  
	private T store;  
	
	public void save(final T object) {  
		this.store = object;  
	}  
	
	public T get() {  
	return this.store;  
	
	}    
}
```
#### Verwendung
Die Klassen StoreGeneric kann man  für jede Art von Objekt benutzen solange man die Art des Objektes in <> angibt. 

```java
// Speicher für Temperatur
StoreGeneric<Temperatur> tempStore = new StoreGeneric<>();

// Speicher für Circle
StoreGeneric<Circle> circleStore = new StoreGeneric<>();

// Speicher für Rectangle
StoreGeneric<Rectangle> rectangleStore = new StoreGeneric<>();
```
