Die [[Datentyp|Datentype]] `float` und `double` sollten nie für Berechnungen genutzt werden, welche genau sein müssen.

`float` und `double` können eine Zahl nur auf 7 respektive 14 stellen genau anzeigen. Dies führt teilweise zu grossen Fehlern:
```java
System.out.println(1.00 - 9 * 0.10);
```
Dies ergibt eigentlich `0.1`, die Ausgabe des Programms ist jedoch `0.0999999998`.

Sind genaue Resultate nötig, sollte `BigDecimal` verwendet werden. `BigDecimal` ist jedoch etwas komplizierter zu nutzen und auch langsamer, stellt jedoch auch schon Funktionen um zu runden zur Verfügung.

Alternativ kann auch die Zahl als `int` oder `long` gespeichert werden, dabei muss man einfach selbst die Übersicht über den Dezimalpunkt halten.