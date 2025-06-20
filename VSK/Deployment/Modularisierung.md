Mit Java 9 wurde eine technische Möglichkeit zur echten Modularisierung mit Java implementiert.

**Ziele**
- **Reliable Configuration**: Fehleranfälligen Classpath durch den auf Modul-Abhängigkeiten basierende Modul-Path ablösen.
- **Strong Encapsulation**: Ein Modul definiert explizit seine öffentliche APIs. Auf allle restlichen Klassen ist kein Zugriff mehr möglich.
- **Scalable Platform**: Die Java Plattform selber wurde modulaarisiert, so dass für Anwender individuell angepasste schlankere Runtime-Images gebaut werden können.

**Umsetzung**
- Packages können nun in Modulen zusammengefasst werden.
	- Optionale zusätzliche Strukturebene in der Dateiablage.
	- Eindeutige Namesgebung notwendig.
- Pro Modul wird ein `module-info.java` definiert. Darin sind epxlizit die Imports, Exports und Abhängigkeiten defineirt.
	- Designverifikation zur Compile-Time möglich.
- Beim Start der Appliaktion wird eine Laufzeitprüfung durchgeführt, ob alle notwendigen Komponenten vorhanden sind.
	- `ClassNotFoundException` sollte nicht mehr Auftreten.
- Ende von JAR-Hell durch `jmod`

## Beispiel
```java
module ch.hslu.sort.quicksort {
	exports ch.hslu.sort.quicksort.impl;
	requires ch.hslu.sort.api;
}
```
