# Final
Final signalisert allgemein das etwas “unveränderbar” ist

Der Einsatz von final ist ein essentieller Desingentscheid

**Besser zu viel Finalisieren als zu wenig**

Das Schlüsselwort Final kann eingesetzt werden bei:

- [[Lokale Variable|Lokalen Variablen]] 
	- Wert kann nur einmal zugewiesen und danach nicht mehr verändert werden
	- Signalisiert das der Wert nach der initialen Zuweisung **konstant** bleibt
- [[Parameter#Formale Parameter|Formalen Parametern]] 
	- Der Wert kann innerhalb der [[Methode]] nicht mehr verändert werden
- [[Attribut|Attributen]] 
	- Finalen Attributen kann nur einmal ein Wert zugewiesen werden
		- Entweder bei Deklaration (seltener)
		- Einmalig innerhalb eines [[Konstruktor|Konstruktors]] (seltener)
	- Grundlage für immutable Klassen
	- Beispiel: UID welche nicht mehr angepasst werden darf
- [[Methode|Methoden]]
	- Finalisierte Methoden können bei einer [[Vererbung|Spezialisierung]] nicht überschrieben werden
	- Einfache [[Methode#Getter und Setter|Getter und Setter]] können finalisiert werden
	- [[Equals & Hashcode|Equals und Hashcode]] Methoden sollten finalisiert werden
- [[Klasse|Klassen]]
	- Finale Klassen können nicht mehr [[Vererbung|spezialisiert]] werden
	- Verhindert [[Vererbung]] wenn Klassen nicht dafür vorgesehen sind
- Bei [[Datenstruktur|Datenstrukturen]] bezieht sich das Schlüsselwort final nicht auf den Inhalt, sondern auf das Objekt
# Static
Statische Elemente können direkt über die [[Klasse]] referenziert werden, es muss dafür kein Objekt existieren 

Statische Elemente existieren pro [[Klasse]] nur einmal

## Statische Attribute
Statische Attribute gibt es nur einmal pro [[Klasse]] und nicht n-Mal pro Objekt. Sie können direkt auf der [[Klasse]] aufgerufen werden 

### Beispiel
Deklaration:
```java
private static int count = 21;
```
Aufrufen (innerhalb der [[Klasse]]):
```java
int newId = Person.counter++;
```

### Konstanten
Konstanten sind der häufigste Anwendungsfall von statischen [[Attribut|Attributen]].
Sie sind gleichzeitig statisch und finalisiert.
- Wert kann nicht mehr verändert werden

Konstante werden mit GROSSEN_BUCHSTABEN bezeichnet

#### Beispiele
Deklaration:
```java
public static final float KELVIN_OFFSET = 273.15;
```
Verwendung:
```java
float kelvin = celcius + Temperatur.KELVIN_OFFSET; 
```

## Statische [[Methode|Methoden]]
Eine statische [[Methode]] kann direkt auf einer [[Klasse]] aufgerufen werden, ohne dass ein Objekt existiert.

Eine Spezielle Statische [[Methode]] ist die [[Main Methode]]
### Beispiel 
Deklaration
```java
public static float convertCelciusToKelvin(float temperatureCelcius) {
        return (temperatureCelcius + KELVIN_OFFSET);
}
```
Verwendung
```java
float Kelvin = Temperatur.convertCelciusToKelvin(20.0f)
```