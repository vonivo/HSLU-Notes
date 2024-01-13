Mit dem Comparable [[Interface]] wird festgelgt was ein Objekt grösser bzw. kleiner zu einem anderen Objekt desselber Typs macht.

Das ist vor allem nützlich bei der Sortierung von Datenstrukturen


# compareTo ([[Interface]] Comparable)
Das Comparable [[Interface]] wir implementiert um die natürliche Ordnung eine Objekts festzulegen. 
### Vertrag
- `this < other` liefert einen negative Wert (typisch -1)
- `this == other` liefert 0
- `this > other` liefert einen positiven Wert (typisch +1)
- Analog zu [[Equals & Hashcode]] wird hier Symmetrie und Trasitivität verlangt

**compareTo() und equals() sollten Gleichheit möglichst analog behandeln**

### Implementationsschema
1. Test auf Identität
	- Liefert 0 als Ergebnise
2. Schrittweiser Vergleich aller relevanten [[Attribut|Attribute]]
	- [[Datentyp#Elementare Datentypen|Elementare Datentypen]] Vergleich mit [[Operatoren]] möglich aber besser mit `Wrapper.compare()` (z.B. `Float.compare()`,`Integer.compare()`)
	- [[Datentyp#Klassen Datentypen|Klassentypen]] Vergleich jeweils an deren eigenen compareTo() weiter delegieren

- Beim Vergleich mehrere Attribute ist die Reihenfolge relevant
- Bei Klassentypen müssen mögliche null Werte beachtet werden

### Beispiele
Vergleicht die Celciustemperatur zweier Temperaturen
```java
@Override
public final int compareTo(Temperatur other) {
    if (this == other) {
        return 0;
    }
        
    return Float.compare(this.temperaturCelcius, other.temperaturCelcius);

}

```
Vergleicht die Personalnummer zweier Personen 
```java
    @Override
    public final int compareTo(Person other) {
        if (this == other) {
            return 0;
        }
        return Long.compare(this.idnumber, other.idnumber);

    }
```
# Comparator
Das [[Interface]] Comparator wird dazu verwendet Objekte nach verschiedenen Kriterien zu sortieren. Somit definiert man über den Comparator die spezielle Ordnung. 
Dafür wird eine eigene kleine [[Klasse]] geschrieben welche das [[Interface]] implementiert. 

Der Comparator kann auch mit [[Lamdas]] implementiert werden siehe: [[Lamdas#Beispiel compareTo & Comparable Comparator Comparator mit Lamdas|Comparator mit Lamdas]]

Der Comparator definiert zwei [[Methode|Methoden]]:
- `int compare (T o1, To2)`
	- Vergleicht zwei Objekte ähnlich wie Comparable
- `boolean equals (Object obj)`
	- Ermöglicht das herauszufinden ob zwei Comparatoren mit gleicher Sortierlogik auch  gleich sind
	- Hashcode sollte ebenfalls implementiert werden

## Beispiel
```java
public class PersonNameComparator implements Comparator<Person> {
    
    @Override
    public int compare(Person person1, Person person2) {
        int compare = person1.getLastname().compareTo(person2.getLastname());
        if (compare == 0) {
            compare = person1.getFirstname().compareTo(person2.getFirstname());
        
        }
        return compare;
        
    }
}
```
``
## Testing
Siehe [[Unit Testing#compareTo & Comparable Testen|Unit Testing CompareTo & Comparable Testen]]
