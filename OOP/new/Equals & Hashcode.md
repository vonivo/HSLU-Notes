Die Equals und Hashcode Methoden bestimmen wann ein Objekt als das gleiche wie ein anderes Objekt angesehen werden kann. 
# Arten von Gleicheit
In absteigender Strenge: 

## 1. Identität (Entity Types)
- Identisches, selbes Objekt
- Gleichheit ist nur dann gegeben wenn die Referenz identisch ist

### Beispiel
point1 und point2 beziehen sich auf dasselbe Point Objekt und sind somit gleich
```java
Point point1 = new Point(1,1);
Point point2 = point1;
```

## 2. Wertegleichheit (Value Types)
-  Objekt mit Attributen welchen den gleichen Wert haben
	- Gleichheit ist gegeben wenn ausgewählte Attribute übereinstimmen

### Beispiel
point1 und point2 sind zwei verschiedene Objekte, sie beziehen sich aber auf den gleichen Punkt (x und y Koordinate sind gleich)
```java
Point point1 = new Point(1,1);
Point point2 = new Point(1,1);
```
## 3. Typgleichheit (Class Types)
- Objekt von der gleichen Klassen
- Gleichheit ist dann gegeben wenn es sich um den gleichen Typ handelt
### Beispiel
point1 und point2 sind verschieden Objekte mit unterschiedlichen Werten aber sie sind beide vom dynamischen Typ Point. 
```java
Point point1 = new Point(1,1);
Point point2 = new Point(3,1);
```

# equals
Die Equals [[Methode]] entscheidet wie “gleich” zwei Objekte sein müssen das sie als gleich angeschaut werden können. (Welchen Grad von Gleichheit sie erfüllen müssen)

**equals ist eine [[Methode]] auf dem Objekt welche überschrieben werden sollte**
- Die Standard Equals [[Methode]] prüft nur auf Identität

Equals wird von vielen Klassen (vor allem [[Datenstruktur|Collections]]) verwendet welche sich darauf verlassen das sie richtig implementiert ist

Nur [[Datentyp#Elementare Datentypen|elementare Datentypen]] sollten mit [[Operatoren|==]] verglichen werden. Objekte sollten man mit equals vergleichen. (Das gilt auch für **String**)

## equals Contract

- **Reflexivität** beim Vergleich mit sich selbst
	- `x.equals(x)`  liefert immer true
-  **Symmetrie** 
	- `x.equals(y)` und `y.equals(x)` liefern das gleiche Resultat
- **Transitivität**
	- falls `x.equals(y) == true` und `y.equals(z) == true` dann soll auch `x.equals(z) == true` 
- **Konsistenz** bei wiederholtem Vergleichen
	- Bei unveränderten Objekten gibt es immer das gleiche Resultat
- **Vergleich mit null**
	- `x.equals(null)` liefert `false`, **keine** NullPointerException

**Ideal ist es wenn `equals()` nur von [[OOP/Schlüsselwörter|finalen]] Attributne abhängig ist, welche niemals `null` sein dürfen**
## Implementationsschema für value Types

1. Test auf Identität mit `==`  → true
	- Gibt ein schnelles `true` bei Identität
2. Test auf `null` 
	- Gibt ein schnelles `false` falls das Objekt `null` ist 
3. Test auf Typen Gleichheit
	- Gibt ein `false` wenn anderer Typ
4. Vergleich aller Relevanten [[Attribut|Attribute]]
	- [[Datentyp#Elementare Datentypen|Elementare Datentypen]]: Vergleich mit `==`
	- Objekte: Vergleich an equals() delegieren!

### Beispiel 

```java
// Equals Methode welche auf Werte Gleichheit bei einer Temperatru prüft
@Override
    public final boolean equals(final Object object) {
        if (object == this) {
            return true;
        }

        return (object instanceof Temperatur temperatur)
                && Float.compare(this.temperaturCelcius, temperatur.temperaturCelcius) == 0;
    }

// Equals Methode welche auf Werte Gleichheit bei einem Punkt prüft (x und y Koordinate)
@Override
public final boolean equals(final Object object) {
    if (object == this) {
         return true;
    }
        
   return (object instanceof Point point) 
        && point.xCoordinate == this.xCoordinate
        && point.yCoordinate == this.yCoordinate;
    }

// Equals Methode welche darauf vergleicht das die Elemente der selben Klassen angehören (Chemische Elemente)
@Override
public final boolean equals(final Object object) {
    if (object == this) {
        return true;
    }

    return (object == null ? false : object.getClass().equals(this.getClass()));

}

```

# Hashcode
Die Hashcode Funktion bildet eine Grosse Datenmenge in einem kleinen Hashwert ab. 
- Einn Hahscode [[Methode]] sollte bei unterschieldichen EIngabedaten in der Regel unterschiedliche Hashwerte liefen (Kollisionen kann es aber immer geben)

**Wenn die Equals [[Methode]] überschrieben wird muss immer auch die Hashcode [[Methode]] überschrieben werden.**
- Sie sollte dabei die gleichen Kriterien für Gleichheit anwenden

## Hashcode Contract
- Sind zwei Objekte im Sinne von equals() gleich, **müssen** ihre Hashwerte **identisch** sein. 
- Sind zwei Objekte im Sinne von equals() ungleich, sollten sie idealerweise verschiedenen Rückgabewerte liefern
- Konsistenz: Wird das Objekt nicht verändert darf sich auch das Ergebnis der hashcode [[Methode]] nicht ändern

## Schema für Implementation
- [[Datentyp#Elementare Datentypen|Elementare Datentypen]]
	- Alle Klassen der elementaren Datentypen (Integer, Float, Long, etc.) verfügen über eine statische Hilfsmethode um Hash werte zu generieren
```java
Boolean.hashCode(true);
Integer.hashCode(5436);
Double.hashCode(2.73);
```

- Klassentypen
	- Entweder man delegiert die Hashcode [[Methode]] weiter oder man verwendet `Objects.hashCode()`

- Mehrere Attribute
	- [[Methode]] `Objects.hash()` nimmt eine beliebige Anzahl Attribute zusammen und berechnet daraus einen Gesamthash

### Beispiele
Die Beispiele stimmen mit den Equals Beispielen von oben überein:
```java
// Hashcode Methode welche ein Hashcode aus dem Celcius Wert einer Temperatur generiert
@Override
public final int hashCode() {
    return Objects.hash(this.temperaturCelcius);
}

// Hashcode Methode welche ein Hashcode aus den x und y Koordinaten eins Punktes generiert
@Override
public final int hashCode(){
	return Objects.hash(this.xCoordinate, this.yCoordinate);
    
}

// Hashcode Methode welche darauf vergleicht das die Elemente der selben Klassen angehören (Chemische Elemente)
@Override
public final int hashCode() {
	return Objects.hash(this.getClass());
}
```

# Testen von Equals & Hashcode
Siehe [[Unit Testing#Equals & Hashcode testen|Unit Testing]] 