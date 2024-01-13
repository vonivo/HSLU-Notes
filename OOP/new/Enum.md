Mit einer Enumeration wird ein eigener Typ mit fix hinterlegten Werten deklariert

Enumerationen können wie jede andere [[Klasse]] als Typ verwendet werden

Enums sind normale Klassen mit vier Ausnahmen:
- Sie werden mit dem Schlüsselwort `enum` deklariert
- Sie sind implizit finalisiert und können nicht vererbt werden
- Enthalten die Enumwerte als [[Schlüsselwörter|finale und statische]] Klassenattribute
- Enumwerte werden automatisch instanziiert

## Best Practices
- [[toString]] [[Methode]] sollte überschrieben werden und eine String Repräsentation liefern
- valueOf() soll zu einer String Räpresentation ein passenden Enumerationswert liefern

## Beispiele
Enum der die Werte von Temperatur Masseinheiten enthält
```java
public enum TemperatureMeasurement {
    CELCIUS,KELVIN,FAHRENHEIT;
    
}
```
Aufruf eines Enum Values: 
```java
TemperatureMeasurement.CELCIUS
```


Enum der die Aggregatzustände enthält mit ihrer deutschen Bezeichnung:
```java
public enum AggregateState {
    SOLID("fest"), LIQUID("flüssig"), GAS("gasförmig");

    public final String deutscheBezeichnung;

    private AggregateState(String deutscheBezeichnung) {
        this.deutscheBezeichnung = deutscheBezeichnung;
    }
    
    public String toString() {
       return this.deutscheBezeichnung;
    }

}
```