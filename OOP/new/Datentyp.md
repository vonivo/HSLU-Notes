# Elementare Datentypen

^49d081

Elementate Datentypen legen den Wertebereich, die Genauigkeit und die möglichen Operationen einer Variablen fest

- Elementare Datentypen sind keine Objekte sie enthalten jeweils nur einen einzigen Wert
- Elementare Datentypen sind speichereffizient
- Elementare Datentypen haben eine Wertebereich und eine Genaugikeit
- Operationen sind bereits definiert 
- Elementare Datentypen beginnen immer mit einem Kleinbuchstaben

## Einsatzbereiche
- [[Lokale Variable|Lokale Variablen]]
- [[Parameter]] von [[Methode|Methoden]] und [[Konstruktor|Konstruktoren]]
- [[Methode#Rückgabewerte|Rückgabewerten]] von [[Methode|Methoden]]
- [[Attribut|Attribute]] von [[Klasse|Klassen]]

## Auflistung
### Ganzzahlen
| Typ | Speicherbedarf | Wertebereich(inklusive) |
| ---- | ---------------- | ---------------------- |
| **byte** | 1 byte = 8 bits| -128 bis 127 |
| **short**| 2 bytes = 16 bits | -32’768 bis 32’767|
| ***int*** | 4 bytes = 32 bits|-2’147’483’648 bis 2’147’483’647|
|**long** | 8 bytes = 64 bits | -9'‘223’372’036’854’775’808 bis 9’223’372’036’854’775’807 |
- Ganzzahlen sind immer zu 100% präzise und können jede Zahl im Wertebereich genau abbilden
### Fliesskommazahlen
| Typ | Speicherbedarf | Wertebereich(inklusive) | Genauigkeit |
| ---- | ---- | ---- | ---- |
| ***float*** | 4 byte = 32 bits | $\pm$ 3.40282347E+38 | ~ 7 relevante Stellen |
| **double** | 8 bytes = 64 bits | $\pm$ 1.79769313486231570E+308 | ~ 14 relevante Stellen |

- Fliesskommazahlen haben einen grösseren Wertebereich, können aber nicht alle Zahlen genau abbilden (Beispiel: 2’000’000.05 wird 2’000'000.05)
### Andere
| Typ | Speicherbedarf | Wertebereich(inklusive) |
| ---- | ---- | ---- |
| **boolean** | 1 byte = 8 bits | *true* , *false* |
| **char** | 2 bytes = 16 bits | UTF-16 Unicode Zeichen |

- Booleans brauchen relativ viel Speicherplatz zugunsten von Performance
- Char ist ein einzelnes Zeichen (z.B. ‘A‘)

# Klassen Datentypen
- Klassen Datentypen beginnen immer mit einem Grossbuchstaben
- Für jeden der elementaren Datentype gibt es ein Klassendatentyp (int zu Integer float zu Float, etc.)
	- Diese werden von Java automatisch konvertiert (AutoBoxing & AutoUnboxing)
- Klassen Datentypen enthalten Attribute und Methoden (siehe [[Klasse]])
- 