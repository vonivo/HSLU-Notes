# Vererbung von [[Klasse|Klassen]]
Wenn eine [[Klasse]] von einer anderen [[Klasse]] erbt:
- Erbt sie **alle** [[Attribut|Attribute]]
- Erbt sie **alle** [[Methode|Methoden]] (inkl. [[Konstruktor|Konstruktoren]])

- Eine [[Klasse]] kann nur von **einer** Oberklasse erben (keine Mehrfavererbung)
- Jede [[Klasse]] erbt implizit von der [[Klasse]] “Object”
- Die Subklasse ist gleichzeitig auch vom Typ des Basisklasse → [[Polymorphie]]


Bei einer guten Vererbung stimmt die folgende Aussage:
- Ein Objekt der Unterklasse **ist** auch **ein** Objekte der Oberklasse (is - a)
	- Ein Apfel ist ein Obst


**Vererbung ist die stärkste Art der [[Kopplung]] innerhalb der Objektorientierung**
- Eine lose [[Kopplung]] ist aber das Ziel
- [[Designprinzipien|Designprinzip]]: Favor Composition over Inheritance (FCoI)


Es ist möglich über mehrere Stufen zu vererben

Wenn eine [[Klasse]] nicht vererbt werden soll kann man die Vererbung mit dem [[OOP/Schlüsselwörter|Schlüsselwort]] `final` unterbinden

Schlüsselwort: `extends`
- `public class Rectangle extends Shape`

Wording: 
Einer Unterklasse:
- **erbt** von ihrer Oberklasse
- **erweitert** die Oberklasse
- ist eine **Ableitung** der Oberklasse 
- **spezialisiert** die Oberklasse

Eine Oberklasse: 
- **vererbt** ihre Eigenschaften 
- **generalisiert** die Unterklasse

## Best Practices
- Vererbung selten einsetzen und nur wenn es wirklich Sinn machen
- Die Spezialisierung sollte immer und überall den Platz der Basisklasse einnehmen können
- Favour Composition over Inheritance
- Vererbung von Klassen und Methoden aktiv mit `final` unterbinden
- Methoden die in der Spezialisierung implementiert werden, sollten in der Basisklasse leer oder abstrakt sein

### Hinweise auf “falsches” Design
- Spezialisierung erweitert oder verändert Vollständig Methoden der Basisklasse
- Spezialisierung verbietet die Aufrufe von ausgewählten Methoden der Basisklasse
- Spezialisierung implementiert Methoden in Abhängigkeit vom effektiven Laufzeittyp des Objekts

## Zugriff
Ein Subklasse hat je nach [[Zugriffsmodifizierer]] anderen Zugriff auf die [[Attribut|Attribute]]/[[Methode|Methoden]] einer [[Klasse]]. 

Die [[Attribut|Attribute]] und [[Methode|Methoden]] sind immer vorhanden, jedoch hat eine Unterklasse keinen direkten Zugriff auf eine privates [[Attribut]]. 
- Dieses ist dann zum Beispiel über eine Public [[Methode]] der Oberklasse erreichbar. 

### [[Konstruktor|Konstruktoren]]
- [[Konstruktor|Konstruktoren]] einer Oberklasse werden ebenfalls vererbt
- Sobald eine [[Klasse]] einen eigenen [[Konstruktor]] implementiert verdeckt diese sämtliche Konstruktoren von Oberklassen. 

- Konstruktoren einer Oberklasse können mit der Schlüsselwort `super()` aufgerufen werden
- `super()` muss zwingend das erste Statement im [[Konstruktor]] sein!
#### Beispiel
Das Rechteck erbt von Shape welches einen [[Konstruktor]] hat wo man die Position der Form mit x und y Koordinaten angeben kann. 
Beim Rectangle kommen zusätzlich noch die Breite und Höhe hinzu. So setzt der [[Konstruktor]] die [[Attribut|Attribute]] der Oberklasse sowie die Attribute der [[Attribut|Attribute]]: 

```java
public Rectangle(final int x, final int y, final float width, final float height) {
        super(x, y);
        this.width = width;
        this.height = height;
    }
```


## Beispiel
Die Unter[[klasse]] Rectangle erbt von Shape. [[Konstruktor]] wie oben beschrieben.

```java
public class Rectangle extends Shape {

	private float width;
    private float height;

	public Rectangle(final int x, final int y, final float width, final float height) {
        super(x, y);
        this.width = width;
        this.height = height;
    }

}

```

Als Ergänzung ein kleiner Auszug der [[Klasse]] Shape: 
```java
public abstract class Shape {

    private int x;
    private int y;

    protected Shape(final int x, final int y) {
        this.x = x;
        this.y = y;
    }
}
```

# Vererbung von [[Interface|Interfaces]]
Wenn eine [[Interface]] von einem anderen [[Interface]] erbt dann:
- Erbt es alle abstrakten Methoden 

 Das Subinterface ist gleichzeitig auch vom Typ des Basisinterface → [[Polymorphie]]

**Ein [[Interface]] kann von mehreren Interfaces erben**
- Die Signaturen von Methoden müssen einzigartig sein
- Mehrere Basisinterfaces können per Komma separiert angegeben werden

## Beispiel
Das [[Interface]] Counting Switchable erbt vom [[Interface]] Switchable

```java
public interface CountingSwitchable extends Switchable {
    
    long getSwitchCount();
}

```